# SSO_PROTOS for nergous.ru

Прото-файлы, созданные для SSO-приложения на Golang для комплекса веб-приложений [nergous.ru](https://nergous.ru).

Пакет содержит gRPC-контракты и сгенерированный Go-код для взаимодействия с сервисом единой аутентификации (SSO).

## Установка

```bash
go get github.com/Nergous/sso_protos
```

Импорт сгенерированного пакета:

```go
import ssov2 "github.com/Nergous/sso_protos/gen/go/sso"
```

## Структура

```
proto/sso/
├── auth.proto   — аутентификация (регистрация, логин, токены)
├── user.proto   — управление пользователями
└── app.proto    — управление приложениями и правами администраторов
```

Сгенерированный Go-код находится в [gen/go/sso/](gen/go/sso/).

## Генерация кода

Используется [Task](https://taskfile.dev):

```bash
task gen
```

Эквивалентная команда:

```bash
protoc -I proto proto/sso/*.proto \
  --go_out=./gen/go/ --go_opt=paths=source_relative \
  --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
```

## Сервисы

Все сервисы объявлены в пакете `auth` с `go_package = "nergous.sso.v2;ssov2"`.

---

### Auth ([auth.proto](proto/sso/auth.proto))

Сервис аутентификации и работы с токенами.

| RPC | Описание |
|---|---|
| `Register(RegisterRequest) → RegisterResponse` | Регистрация нового пользователя. Возвращает `user_id`. |
| `Login(LoginRequest) → LoginResponse` | Вход по email/паролю в контексте `app_id`. Возвращает пару access/refresh токенов. |
| `Logout(LogoutRequest) → LogoutResponse` | Выход, инвалидирует токен. |
| `Refresh(RefreshRequest) → LoginResponse` | Обновление токенов по refresh-токену. |
| `ValidateToken(ValidateTokenRequest) → ValidateTokenResponse` | Проверка валидности токена, возвращает `user_id` и флаг `valid`. |

**Ключевые сообщения:**

```proto
message RegisterRequest {
    string email = 1;
    string password = 2;
    string steam_url = 3;
    string path_to_photo = 4;
}

message LoginRequest {
    string email = 1;
    string password = 2;
    uint32 app_id = 3;
}

message LoginResponse {
    string access_token = 1;
    string refresh_token = 2;
}
```

---

### User ([user.proto](proto/sso/user.proto))

Управление учётными записями пользователей.

| RPC | Описание |
|---|---|
| `UserInfo(UserInfoRequest) → UserInfoResponse` | Получение профиля пользователя по `user_id`. |
| `GetAllUsers(GetAllUsersRequest) → GetAllUsersResponse` | Список всех пользователей. |
| `UpdateUser(UpdateUserRequest) → UpdateUserResponse` | Обновление данных пользователя. |
| `DeleteUser(DeleteUserRequest) → DeleteUserResponse` | Удаление пользователя. |

**Ключевые сообщения:**

```proto
message UserModel {
    uint32 id = 1;
    string email = 2;
    string steam_url = 3;
    string path_to_photo = 4;
}

message UpdateUserRequest {
    uint32 id = 1;
    string email = 2;
    string password = 3;
    string steam_url = 4;
    string path_to_photo = 5;
}
```

---

### App ([app.proto](proto/sso/app.proto))

Управление приложениями, входящими в экосистему SSO, и правами администраторов.

| RPC | Описание |
|---|---|
| `GetApp(GetAppRequest) → GetAppResponse` | Получение приложения по `id`. |
| `GetAllApps(GetAllAppsRequest) → GetAllAppsResponse` | Список всех приложений. |
| `CreateApp(CreateAppRequest) → CreateAppResponse` | Создание приложения (`name`, `link`). |
| `UpdateApp(UpdateAppRequest) → UpdateAppResponse` | Обновление приложения. |
| `DeleteApp(DeleteAppRequest) → DeleteAppResponse` | Удаление приложения. |
| `ChangeStatusApp(ChangeStatusAppRequest) → ChangeStatusAppResponse` | Переключение флага `isenabled`. |
| `IsAdmin(IsAdminRequest) → IsAdminResponse` | Проверка, является ли пользователь администратором приложения. |
| `AddAdmin(AddAdminRequest) → AddAdminResponse` | Назначение администратора. |
| `RemoveAdmin(RemoveAdminRequest) → RemoveAdminResponse` | Снятие прав администратора. |
| `GetAllUsersForApp(GetAllUsersForAppRequest) → GetAllUsersForAppResponse` | Список пользователей приложения с пометкой `is_admin`. |

**Ключевые сообщения:**

```proto
message AppModel {
    uint32 id = 1;
    string name = 2;
    string link = 3;
    bool isenabled = 4;
}

message AppUser {
    uint32 id = 1;
    string email = 2;
    string steam_url = 3;
    string path_to_photo = 4;
    bool is_admin = 5;
}
```

## Требования

- Go 1.23.4+
- `protoc` с плагинами `protoc-gen-go` и `protoc-gen-go-grpc`
- google.golang.org/grpc v1.73.0
- google.golang.org/protobuf v1.36.10
