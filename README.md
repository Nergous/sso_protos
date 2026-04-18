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
proto/sso/auth/v2/
├── auth.proto   — аутентификация (регистрация, логин, токены)
├── user.proto   — управление пользователями
└── app.proto    — управление приложениями и правами администраторов
```

Все файлы объявлены в пакете `sso.auth.v2` (buf-style layout). Следующее
мажорное изменение контракта переедет в `sso/auth/v3/` без влияния на
существующих клиентов v2.

Сгенерированный Go-код находится в [gen/go/sso/](gen/go/sso/).

## Генерация кода

Используется [Task](https://taskfile.dev):

```bash
task gen
```

Эквивалентная команда:

```bash
protoc -I proto proto/sso/auth/v2/*.proto \
  --go_out=./gen/go/ --go_opt=paths=source_relative \
  --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
```

## Сервисы

Все сервисы объявлены в пакете `sso.auth.v2` с `go_package = "nergous.sso.v2;ssov2"`.

---

### Auth ([auth.proto](proto/sso/auth/v2/auth.proto))

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

### User ([user.proto](proto/sso/auth/v2/user.proto))

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

### App ([app.proto](proto/sso/auth/v2/app.proto))

Управление приложениями, входящими в экосистему SSO, и правами администраторов.

| RPC | Описание |
|---|---|
| `GetApp(GetAppRequest) → GetAppResponse` | Получение приложения по `id`. |
| `GetAllApps(GetAllAppsRequest) → GetAllAppsResponse` | Список всех приложений. |
| `CreateApp(CreateAppRequest) → CreateAppResponse` | Создание приложения (`name`, `link`). |
| `UpdateApp(UpdateAppRequest) → UpdateAppResponse` | Обновление приложения. |
| `DeleteApp(DeleteAppRequest) → DeleteAppResponse` | Удаление приложения. |
| `ChangeStatusApp(ChangeStatusAppRequest) → ChangeStatusAppResponse` | Переключение флага `is_enabled`. |
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
    bool is_enabled = 4;
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
- `protoc` с плагинами `protoc-gen-go` и `protoc-gen-go-grpc`, либо
  [`buf`](https://buf.build/docs/installation) (предпочтительно — см.
  `Taskfile.yaml`)
- google.golang.org/grpc v1.73.0
- google.golang.org/protobuf v1.36.10

## Таблица совместимости версий

Матрица «версия proto-контракта × версия gRPC-библиотеки × минимально
поддерживаемая версия Go и сервера SSO». Клиентам рекомендуется подбирать
строку, соответствующую используемому тегу `sso_protos`.

| Тег `sso_protos` | Proto-пакет    | gRPC (Go) | `google.golang.org/protobuf` | Go       | SSO-сервер |
|------------------|----------------|-----------|------------------------------|----------|------------|
| v2.x (current)   | `sso.auth.v2`  | ≥ 1.73.0  | ≥ 1.36.10                    | ≥ 1.23.4 | ≥ 2.0.0    |
| v1.x (legacy)    | `auth`         | ≥ 1.60.0  | ≥ 1.33.0                     | ≥ 1.21   | 1.x        |

Правила совместимости:

- В рамках одной мажорной версии (`v2.x`) изменения контракта строго
  обратно совместимы — добавляются только новые поля/RPC, типы и номера
  существующих полей не меняются. Это гарантируется `buf breaking` в CI.
- Мажорное изменение контракта (например, `v3`) переедет в
  `proto/sso/auth/v3/` и получит свой `go_package`, не ломая клиентов
  предыдущей версии.
