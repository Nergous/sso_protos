# SSO_PROTOS for nergous.ru

Прото-контракты SSO-сервиса для комплекса веб-приложений [nergous.ru](https://nergous.ru).

Пакет содержит gRPC-API для единой аутентификации, управления
пользователями, приложениями, ролями и авторизационными решениями.

## Установка

```bash
go get github.com/Nergous/sso_protos
```

Импорт сгенерированных Go-пакетов (один на домен):

```go
import (
    ssoauthv1           "github.com/Nergous/sso_protos/gen/go/sso/auth/v1"
    ssoidentityv1       "github.com/Nergous/sso_protos/gen/go/sso/identity/v1"
    ssoappv1            "github.com/Nergous/sso_protos/gen/go/sso/app/v1"
    ssorolesv1          "github.com/Nergous/sso_protos/gen/go/sso/roles/v1"
    ssoaccessv1         "github.com/Nergous/sso_protos/gen/go/sso/access/v1"
    ssoserviceaccountv1 "github.com/Nergous/sso_protos/gen/go/sso/serviceaccount/v1"
    ssoauditv1          "github.com/Nergous/sso_protos/gen/go/sso/audit/v1"
    ssocommonv1         "github.com/Nergous/sso_protos/gen/go/sso/common/v1"
)
```

## Структура

```
proto/sso/
├── auth/v1/auth.proto                     — аутентификация, сессии, MFA, recovery, SA-auth
├── identity/v1/identity.proto             — каталог пользователей (CRUD, статусы)
├── app/v1/app.proto                       — каталог приложений SSO (CRUD, lifecycle)
├── roles/v1/roles.proto                   — определения ролей (permissions-bundles)
├── access/v1/access.proto                 — назначения ролей, Check/BatchCheckPermission
├── serviceaccount/v1/serviceaccount.proto — backend-to-backend identities
├── audit/v1/audit.proto                   — security-event log (read-only API)
└── common/v1/errors.proto                 — ErrorReason (машиночитаемая причина)
```

Каждый домен — отдельный proto-пакет (`sso.auth.v1`, `sso.identity.v1`, …)
и отдельный Go-пакет. Это позволяет поднимать major-версию каждого
сервиса независимо: миграция `sso.auth.v1` → `sso.auth.v2` (например, под
MFA или OIDC) не затронет клиентов IdentityService.

## Сервисы

### AuthService ([auth/v1/auth.proto](proto/sso/auth/v1/auth.proto))

Регистрация, логин, ротация и валидация токенов, управление сессиями,
смена пароля.

| RPC | Описание |
|---|---|
| `Register` | создание identity в глобальном каталоге; возвращает `sso.identity.v1.User` напрямую (AIP-133) |
| `Login` | per-app логин; принимает `app_id` / `app_slug` и `email` / `username` (oneof); возвращает **либо** `AuthTokens`, **либо** `MfaChallenge` |
| `CompleteMfaChallenge` | второй фактор — завершение MFA по `challenge_id` + code; возвращает `AuthTokens` |
| `Logout` | инвалидация текущей сессии (по `Authorization: Bearer`) |
| `Refresh` | ротация refresh-токена (RFC 6819) |
| `ValidateToken` | интроспекция access-токена; возвращает `subject_id`, `subject_type`, `session_id`, `app_id` |
| `RevokeSession` | досрочное завершение конкретной сессии |
| `RevokeToken` | отзыв refresh-токена и всей цепочки access-токенов |
| `ListSessions` | список активных сессий вызывающего (device info, last seen) |
| `RevokeAllSessions` | logout-everywhere; опциональный `except_current` для сохранения текущей |
| `ChangePassword` | смена пароля с подтверждением старого; **отзывает все сессии** и возвращает новую пару `AuthTokens` |
| `ResetPasswordWithRecoveryCode` | **публичный** (без access-token) сброс пароля по recovery-коду |
| `GenerateRecoveryCodes` | выпуск 10 одноразовых recovery-кодов (показываются один раз) |
| `EnrollTotp` / `ConfirmTotpEnrollment` / `DisableTotp` | жизненный цикл TOTP MFA (RFC 6238) |
| `AuthenticateServiceAccount` | OAuth2 client_credentials для backend-to-backend; возвращает `AuthTokens` |

### IdentityService ([identity/v1/identity.proto](proto/sso/identity/v1/identity.proto))

CRUD над пользователями (без сессий/токенов). `UpdateUser` использует
`FieldMask` (AIP-134) и требует etag (AIP-154; `"*"` — безусловная запись).

Статусы: `ACTIVE`, `BLOCKED`, `DELETED`.

### AppService ([app/v1/app.proto](proto/sso/app/v1/app.proto))

Регистрация и lifecycle приложений SSO. У каждого app есть UUID `app_id`
и URL-safe `slug` (иммутабельный, уникальный, `^[a-z][a-z0-9-]{2,63}$`).

Статусы: `ACTIVE`, `DISABLED`, `MAINTENANCE`.

### RolesService ([roles/v1/roles.proto](proto/sso/roles/v1/roles.proto))

Определения ролей в контексте одного app. Роль — это bundle прав в форме
`"resource:action"` (до 128 записей). Назначения ролей лежат в отдельном
AccessService.

Статусы: `ACTIVE`, `DISABLED`. `DISABLED` роль сохраняет назначения, но
не учитывается при CheckPermission.

### AccessService ([access/v1/access.proto](proto/sso/access/v1/access.proto))

Assign/revoke ролей, listing и authorization-запросы.

| RPC | Описание |
|---|---|
| `HasRoleInApp` | быстрая проверка, назначена ли пользователю роль |
| `ListUserRoles` | все роли пользователя в app (включая `DISABLED`) |
| `GrantRoleToUser` / `RemoveRoleFromUser` | single-role assignment |
| `BulkGrantRoles` / `BulkRemoveRoles` | до 32 ролей атомарно в одном app |
| `CheckPermission` | `(user, app, permission) → allowed + matched_role_ids` |
| `BatchCheckPermission` | до 32 permissions в одном вызове; возвращает параллельный `repeated bool allowed` (без `matched_role_ids`) |

⚠️ `CheckPermission.matched_role_ids` раскрывает RBAC-структуру app —
endpoint для service-to-service вызовов, не для end-user clients.
Ingress должен либо отсечь вызов от недоверенных клиентов, либо убрать
поле на gateway. `BatchCheckPermission` не возвращает `matched_role_ids`
специально, чтобы не множить эту поверхность.

### ServiceAccountService ([serviceaccount/v1/serviceaccount.proto](proto/sso/serviceaccount/v1/serviceaccount.proto))

Управление backend-идентичностями. Service account — это не-человек,
без пароля / MFA / recovery кодов, аутентифицируется по
`(client_id, client_secret)` через `AuthService.AuthenticateServiceAccount`.
Роли назначаются через тот же `AccessService` (service_account_id
подставляется вместо user_id).

| RPC | Описание |
|---|---|
| `GetServiceAccount` / `ListServiceAccounts` | чтение |
| `CreateServiceAccount` | создание; возвращает `ServiceAccountCredentials` с одноразовым `client_secret` |
| `UpdateServiceAccount` | FieldMask-update (name, description) |
| `RotateCredentials` | выпуск нового `client_secret`, старый инвалидируется |
| `Disable` / `Enable` | lifecycle |
| `PermanentlyDelete` | etag-protected hard delete, cascade к role-assignments |

### AuditService ([audit/v1/audit.proto](proto/sso/audit/v1/audit.proto))

**Read-only** API к security-event log. Запись событий происходит
внутри SSO как побочный эффект user-facing RPC — внешнего write-API
нет by design (append-only).

| RPC | Описание |
|---|---|
| `GetAuditEvent` | событие по UUID |
| `ListAuditEvents` | хронологическая выборка с фильтрами (`from_time`, `to_time`, `event_type`, `actor`, `subject`, `app_id`, `outcome`) |

Канонические `event_type` перечислены в комментарии к `AuditEvent` —
это открытый namespace `domain.action`, новые значения добавляются без
schema-bump'а. Порядок всегда `occurred_at DESC` с `event_id` как
tie-breaker; `order_by` намеренно отсутствует.

Доступ — узко ограниченная роль `AUDIT_READ` (security/compliance-team).

### Общие соглашения

- **IDs** — RFC 4122 UUID v4, строковые. Схема НЕ следует AIP-122
  resource-name pattern (`apps/{app}/roles/{role}`); вместо этого каждый
  ресурс адресуется плоским UUID-полем (`app_id`, `role_id`, `user_id`).
  Это осознанный отказ для упрощения клиентских SDK; следствие — мы не
  получаем «бесплатно» AIP-131 `name` поле и AIP-127 HTTP-маппинг,
  но избегаем парсинга составных имён на каждом hop.
- **Timestamps** — `google.protobuf.Timestamp`.
- **Pagination** — AIP-158: `int32 page_size ≤ 1000`, `string page_token`,
  `repeated T items`, `string next_page_token`, `optional int32 total_size`.
  Отсутствие `total_size` означает «сервер не считал тотал», `0` —
  «реально 0 совпадений». Не путайте.
- **Ordering** — каждый `List*Request` принимает типизированный `*OrderBy`
  enum (AIP-132) — `ListUsersOrderBy`, `ListAppsOrderBy`,
  `ListRolesOrderBy`, `ListUserRolesOrderBy`. `*_UNSPECIFIED` означает
  «server default». Tie-breaker по resource_id добавляется сервером
  автоматически.
- **Partial updates** — AIP-134: `FieldMask update_mask` + `string etag`
  (обязательный; `"*"` — unconditional write). Mask path для immutable
  полей (`*_id`, `status`, `etag`, timestamps, `slug`) сервер обязан
  отклонять `INVALID_ARGUMENT`. Список валидных путей задокументирован
  в комментарии к каждому `Update*Request`.
- **Create RPCs (AIP-133)** — возвращают созданный ресурс напрямую
  (`Register → User`, `CreateApp → App`, `CreateRole → Role`).
  `CreateApp` принимает `App app`; `CreateRole` принимает
  `(parent_app_id, Role role)`. Server-managed поля
  (`*_id`, `etag`, `status`, timestamps) в payload игнорируются.
- **Hard deletes** — RPC-имя `PermanentlyDelete*`; вместо `bool force`
  обязательный `string etag`, который должен совпасть с текущим
  `etag` ресурса. `"*"` (unconditional) НЕ принимается. Mismatch →
  `ABORTED` / `ERROR_REASON_ETAG_MISMATCH`. У `PermanentlyDeleteRole`
  есть отдельный `bool allow_cascade` для сноса активных назначений.
- **Idempotent lifecycle** — `Disable*`, `Enable*`, `SoftDelete*`,
  `Enter/ExitMaintenanceMode` принимают `bool allow_missing` (AIP-135):
  если `true`, отсутствие ресурса возвращает `OK` вместо `NOT_FOUND`.
- **Валидация** — runtime через [`buf.build/go/protovalidate`](https://buf.build/docs/protovalidate/overview/):

  ```go
  if err := protovalidate.Validate(req); err != nil {
      return nil, status.Error(codes.InvalidArgument, err.Error())
  }
  ```

## Потоки аутентификации

### Обычный логин

```
Client → Login(app_id/slug, email/username, password)
       ← LoginResponse { tokens: AuthTokens }
```

### Логин с MFA

```
Client → Login(..., password)
       ← LoginResponse { challenge: MfaChallenge { challenge_id, methods=[TOTP, RECOVERY_CODE], expires_at } }
Client → CompleteMfaChallenge(challenge_id, method=TOTP, code="123456")
       ← AuthTokens
```

### Сброс пароля по recovery-коду (без email)

```
[пользователь потерял пароль, у него есть один из 10 кодов]
Client → ResetPasswordWithRecoveryCode(email/username, app_id/slug, recovery_code, new_password)
       ← AuthTokens     # старые сессии все отозваны, выдана свежая
```

Recovery-коды выпускаются через `GenerateRecoveryCodes` (требует
access-token) — 10 штук за раз, показываются один раз. Выпуск новой
партии инвалидирует все предыдущие коды.

### Service account (backend-to-backend)

```
[service account создан админом через ServiceAccountService.CreateServiceAccount,
 client_id и client_secret сохранены в secret manager воркера]
Worker → AuthenticateServiceAccount(client_id, client_secret, app_id/slug)
       ← AuthTokens
Worker → IdentityService.GetUser(...)    # с access_token в Authorization
```

Ролевые назначения для service account идут через `AccessService`
(тот же `GrantRoleToUser`, user_id = service_account_id).

## Health checking

Сервер обязан зарегистрировать стандартный **gRPC Health Checking
Protocol** (`grpc.health.v1.Health`) — он не входит в эту схему, т.к.
определён gRPC-инфраструктурой. Go-импорт:

```go
import "google.golang.org/grpc/health/grpc_health_v1"
import "google.golang.org/grpc/health"

srv := grpc.NewServer()
hs := health.NewServer()
grpc_health_v1.RegisterHealthServer(srv, hs)
hs.SetServingStatus("sso.auth.v1.AuthService", grpc_health_v1.HealthCheckResponse_SERVING)
// ...
```

Kubernetes/load-balancer/probe может дёргать `Check(service="")` для
общего статуса или `Watch` для стримовых health-updates.

## Безопасность

- **TLS обязателен.** `AuthService` передаёт bearer-токены и plaintext
  пароли. Plaintext gRPC / h2c — не соответствует контракту.
- **Redaction.** Поля с секретами помечены `debug_redact = true`
  (пароли, access/refresh токены, `session_id`). Этот option — метаданные
  схемы; runtime-redaction обеспечивает клиент (логгирующий interceptor).
  Production-deployments должны отключать request/response body logging
  для AuthService.
- **Generic errors.** `INVALID_CREDENTIALS` и `INVALID_TOKEN` —
  намеренно общие (info-disclosure mitigation). `USER_ALREADY_EXISTS`
  на `Register` НЕ сообщает, какое поле (email/username) занято
  (anti-enumeration).
- **Rate limiting.** `Login` и `ChangePassword` (`PASSWORD_MISMATCH`) —
  обязательный per-user backoff на стороне сервера. См.
  `ERROR_REASON_PASSWORD_MISMATCH`.
- **Token rotation на ChangePassword.** Успешная смена пароля отзывает
  ВСЕ сессии пользователя (включая ту, что выполнила вызов) и
  возвращает новую пару `(access_token, refresh_token)` в
  `ChangePasswordResponse`. Клиент обязан заменить старые токены.
- **`CheckPermission.matched_role_ids`** раскрывает RBAC-структуру —
  только для service-to-service. См. ⚠️ выше.
- **Recovery codes** — полная альтернатива email-based password reset.
  Не требуют домена / SMTP. Коды показываются один раз; сервер хранит
  только salted hashes. Перевыпуск инвалидирует все предыдущие.
- **MFA — TOTP (RFC 6238)**, стандарт открытый. Google / Microsoft
  Authenticator / Authy / 2FAS / Aegis / Raivo — любое совместимое
  приложение. Никаких внешних зависимостей на стороне сервера.
- **Service accounts** аутентифицируются по `(client_id, client_secret)`.
  `client_secret` показывается один раз при создании / rotate; сервер
  хранит только хэш. Ротация инвалидирует старый секрет атомарно.
- **Audit log** append-only, без write-API. События пишутся как
  побочный эффект user-facing RPC; читаются через `AuditService`
  с ограниченной ролью `AUDIT_READ`.

## Ошибки

`ErrorReason` ([common/v1/errors.proto](proto/sso/common/v1/errors.proto))
— машиночитаемая причина сбоя, прикрепляется к ответу через
`google.rpc.ErrorInfo.reason`. Клиенты должны ветвиться по этому значению,
а не парсить `grpc.Status.Message`.

Значения сгруппированы по блокам:

| Диапазон | Домен |
|---|---|
| 1–19 | Authentication |
| 20–39 | Validation / concurrency |
| 40–59 | User identity |
| 60–79 | Apps |
| 80–99 | Roles |
| 100–119 | Authorization |
| 120–139 | MFA |
| 140–159 | Recovery codes |
| 160–179 | Service accounts |

## Генерация кода

```bash
task gen      # буф-генерация Go
task lint     # buf lint
task breaking # buf breaking --against '.git#branch=main'
```

## Требования

- Go ≥ 1.24
- [`buf`](https://buf.build/docs/installation) CLI
- Для runtime-валидации клиент: [`buf.build/go/protovalidate`](https://buf.build/go/protovalidate) ≥ 1.1
- google.golang.org/grpc ≥ 1.73
- google.golang.org/protobuf ≥ 1.36

## Таблица совместимости

| Тег | proto-пакеты | Go-модуль | SSO-сервер |
|---|---|---|---|
| `v1.x` (current) | `sso.{auth,identity,app,roles,access,common}.v1` | ≥ 1.0.0 | ≥ 2.0.0 |
| `v2.x` (legacy) | `sso.auth.v2` | — | — |

**Правила совместимости:**

- В рамках `v1.x` изменения строго обратно совместимы: только добавление
  новых полей/RPC, существующие номера и типы неизменны. Гарантируется
  `task breaking` в CI.
- Любой breaking change в конкретном домене переезжает в `sso/<domain>/v2/`
  и получает свой `go_package`. Другие домены остаются на v1.
- `v2.x` (`proto/sso/auth/v2/`) — более не поддерживается и удалён из
  репозитория.
