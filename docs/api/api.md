# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [sso/roles/v1/roles.proto](#sso_roles_v1_roles-proto)
    - [CreateRoleRequest](#sso-roles-v1-CreateRoleRequest)
    - [DisableRoleRequest](#sso-roles-v1-DisableRoleRequest)
    - [EnableRoleRequest](#sso-roles-v1-EnableRoleRequest)
    - [GetRoleRequest](#sso-roles-v1-GetRoleRequest)
    - [ListRolesRequest](#sso-roles-v1-ListRolesRequest)
    - [ListRolesResponse](#sso-roles-v1-ListRolesResponse)
    - [PermanentlyDeleteRoleRequest](#sso-roles-v1-PermanentlyDeleteRoleRequest)
    - [Role](#sso-roles-v1-Role)
    - [RoleFilters](#sso-roles-v1-RoleFilters)
    - [UpdateRoleRequest](#sso-roles-v1-UpdateRoleRequest)
  
    - [ListRolesOrderBy](#sso-roles-v1-ListRolesOrderBy)
    - [RoleStatus](#sso-roles-v1-RoleStatus)
  
    - [RolesService](#sso-roles-v1-RolesService)
  
- [sso/access/v1/access.proto](#sso_access_v1_access-proto)
    - [BatchCheckPermissionRequest](#sso-access-v1-BatchCheckPermissionRequest)
    - [BatchCheckPermissionResponse](#sso-access-v1-BatchCheckPermissionResponse)
    - [BulkGrantRolesRequest](#sso-access-v1-BulkGrantRolesRequest)
    - [BulkGrantRolesResponse](#sso-access-v1-BulkGrantRolesResponse)
    - [BulkRemoveRolesRequest](#sso-access-v1-BulkRemoveRolesRequest)
    - [CheckPermissionRequest](#sso-access-v1-CheckPermissionRequest)
    - [CheckPermissionResponse](#sso-access-v1-CheckPermissionResponse)
    - [GrantRoleToUserRequest](#sso-access-v1-GrantRoleToUserRequest)
    - [HasRoleInAppRequest](#sso-access-v1-HasRoleInAppRequest)
    - [HasRoleInAppResponse](#sso-access-v1-HasRoleInAppResponse)
    - [ListUserRolesRequest](#sso-access-v1-ListUserRolesRequest)
    - [ListUserRolesResponse](#sso-access-v1-ListUserRolesResponse)
    - [RemoveRoleFromUserRequest](#sso-access-v1-RemoveRoleFromUserRequest)
    - [RoleAssignment](#sso-access-v1-RoleAssignment)
  
    - [ListUserRolesOrderBy](#sso-access-v1-ListUserRolesOrderBy)
  
    - [AccessService](#sso-access-v1-AccessService)
  
- [sso/app/v1/app.proto](#sso_app_v1_app-proto)
    - [App](#sso-app-v1-App)
    - [AppFilters](#sso-app-v1-AppFilters)
    - [CreateAppRequest](#sso-app-v1-CreateAppRequest)
    - [DisableAppRequest](#sso-app-v1-DisableAppRequest)
    - [EnableAppRequest](#sso-app-v1-EnableAppRequest)
    - [EnterMaintenanceModeRequest](#sso-app-v1-EnterMaintenanceModeRequest)
    - [ExitMaintenanceModeRequest](#sso-app-v1-ExitMaintenanceModeRequest)
    - [GetAppRequest](#sso-app-v1-GetAppRequest)
    - [ListAppsRequest](#sso-app-v1-ListAppsRequest)
    - [ListAppsResponse](#sso-app-v1-ListAppsResponse)
    - [PermanentlyDeleteAppRequest](#sso-app-v1-PermanentlyDeleteAppRequest)
    - [UpdateAppRequest](#sso-app-v1-UpdateAppRequest)
  
    - [AppStatus](#sso-app-v1-AppStatus)
    - [ListAppsOrderBy](#sso-app-v1-ListAppsOrderBy)
  
    - [AppService](#sso-app-v1-AppService)
  
- [sso/audit/v1/audit.proto](#sso_audit_v1_audit-proto)
    - [Actor](#sso-audit-v1-Actor)
    - [AuditEvent](#sso-audit-v1-AuditEvent)
    - [AuditEvent.MetadataEntry](#sso-audit-v1-AuditEvent-MetadataEntry)
    - [AuditFilters](#sso-audit-v1-AuditFilters)
    - [GetAuditEventRequest](#sso-audit-v1-GetAuditEventRequest)
    - [ListAuditEventsRequest](#sso-audit-v1-ListAuditEventsRequest)
    - [ListAuditEventsResponse](#sso-audit-v1-ListAuditEventsResponse)
    - [Subject](#sso-audit-v1-Subject)
  
    - [ActorType](#sso-audit-v1-ActorType)
    - [AuditOutcome](#sso-audit-v1-AuditOutcome)
    - [SubjectType](#sso-audit-v1-SubjectType)
  
    - [AuditService](#sso-audit-v1-AuditService)
  
- [sso/identity/v1/identity.proto](#sso_identity_v1_identity-proto)
    - [DisableUserRequest](#sso-identity-v1-DisableUserRequest)
    - [EnableUserRequest](#sso-identity-v1-EnableUserRequest)
    - [GetUserRequest](#sso-identity-v1-GetUserRequest)
    - [ListUsersRequest](#sso-identity-v1-ListUsersRequest)
    - [ListUsersResponse](#sso-identity-v1-ListUsersResponse)
    - [PermanentlyDeleteUserRequest](#sso-identity-v1-PermanentlyDeleteUserRequest)
    - [SoftDeleteUserRequest](#sso-identity-v1-SoftDeleteUserRequest)
    - [UpdateUserRequest](#sso-identity-v1-UpdateUserRequest)
    - [User](#sso-identity-v1-User)
    - [UserFilters](#sso-identity-v1-UserFilters)
  
    - [ListUsersOrderBy](#sso-identity-v1-ListUsersOrderBy)
    - [UserStatus](#sso-identity-v1-UserStatus)
  
    - [IdentityService](#sso-identity-v1-IdentityService)
  
- [sso/auth/v1/auth.proto](#sso_auth_v1_auth-proto)
    - [AuthTokens](#sso-auth-v1-AuthTokens)
    - [ChangePasswordRequest](#sso-auth-v1-ChangePasswordRequest)
    - [CompleteMfaChallengeRequest](#sso-auth-v1-CompleteMfaChallengeRequest)
    - [ConfirmTotpEnrollmentRequest](#sso-auth-v1-ConfirmTotpEnrollmentRequest)
    - [DeviceInfo](#sso-auth-v1-DeviceInfo)
    - [DisableTotpRequest](#sso-auth-v1-DisableTotpRequest)
    - [ListSessionsRequest](#sso-auth-v1-ListSessionsRequest)
    - [ListSessionsResponse](#sso-auth-v1-ListSessionsResponse)
    - [LoginRequest](#sso-auth-v1-LoginRequest)
    - [LoginResponse](#sso-auth-v1-LoginResponse)
    - [MfaChallenge](#sso-auth-v1-MfaChallenge)
    - [RecoveryCodesResponse](#sso-auth-v1-RecoveryCodesResponse)
    - [RefreshRequest](#sso-auth-v1-RefreshRequest)
    - [RegisterRequest](#sso-auth-v1-RegisterRequest)
    - [ResetPasswordWithRecoveryCodeRequest](#sso-auth-v1-ResetPasswordWithRecoveryCodeRequest)
    - [RevokeAllSessionsRequest](#sso-auth-v1-RevokeAllSessionsRequest)
    - [RevokeSessionRequest](#sso-auth-v1-RevokeSessionRequest)
    - [RevokeTokenRequest](#sso-auth-v1-RevokeTokenRequest)
    - [ServiceAccountAuthRequest](#sso-auth-v1-ServiceAccountAuthRequest)
    - [SessionInfo](#sso-auth-v1-SessionInfo)
    - [TotpEnrollmentResponse](#sso-auth-v1-TotpEnrollmentResponse)
    - [ValidateTokenRequest](#sso-auth-v1-ValidateTokenRequest)
    - [ValidateTokenResponse](#sso-auth-v1-ValidateTokenResponse)
  
    - [MfaMethod](#sso-auth-v1-MfaMethod)
    - [SubjectType](#sso-auth-v1-SubjectType)
  
    - [AuthService](#sso-auth-v1-AuthService)
  
- [sso/common/v1/errors.proto](#sso_common_v1_errors-proto)
    - [ErrorReason](#sso-common-v1-ErrorReason)
  
- [sso/serviceaccount/v1/serviceaccount.proto](#sso_serviceaccount_v1_serviceaccount-proto)
    - [CreateServiceAccountRequest](#sso-serviceaccount-v1-CreateServiceAccountRequest)
    - [CreateServiceAccountResponse](#sso-serviceaccount-v1-CreateServiceAccountResponse)
    - [DisableServiceAccountRequest](#sso-serviceaccount-v1-DisableServiceAccountRequest)
    - [EnableServiceAccountRequest](#sso-serviceaccount-v1-EnableServiceAccountRequest)
    - [GetServiceAccountRequest](#sso-serviceaccount-v1-GetServiceAccountRequest)
    - [ListServiceAccountsRequest](#sso-serviceaccount-v1-ListServiceAccountsRequest)
    - [ListServiceAccountsResponse](#sso-serviceaccount-v1-ListServiceAccountsResponse)
    - [PermanentlyDeleteServiceAccountRequest](#sso-serviceaccount-v1-PermanentlyDeleteServiceAccountRequest)
    - [RotateCredentialsRequest](#sso-serviceaccount-v1-RotateCredentialsRequest)
    - [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount)
    - [ServiceAccountCredentials](#sso-serviceaccount-v1-ServiceAccountCredentials)
    - [ServiceAccountFilters](#sso-serviceaccount-v1-ServiceAccountFilters)
    - [UpdateServiceAccountRequest](#sso-serviceaccount-v1-UpdateServiceAccountRequest)
  
    - [ListServiceAccountsOrderBy](#sso-serviceaccount-v1-ListServiceAccountsOrderBy)
    - [ServiceAccountStatus](#sso-serviceaccount-v1-ServiceAccountStatus)
  
    - [ServiceAccountService](#sso-serviceaccount-v1-ServiceAccountService)
  
- [Scalar Value Types](#scalar-value-types)



<a name="sso_roles_v1_roles-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/roles/v1/roles.proto



<a name="sso-roles-v1-CreateRoleRequest"></a>

### CreateRoleRequest
============================================================================
CreateRoleRequest - AIP-133 create
============================================================================
Shape: (parent, resource). `parent` is the target app; `role` is the
resource to create. The server populates role_id, status (always
ACTIVE), etag, created_at, updated_at; any client-supplied values for
those fields in `role` are ignored.

Fields the client MUST populate in `role`:
  name, permissions
Fields the client MAY populate:
  description


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| parent_app_id | [string](#string) |  | Parent: UUID of the app to create the role in. |
| role | [Role](#sso-roles-v1-Role) |  | Role definition. Server-managed fields are ignored. |






<a name="sso-roles-v1-DisableRoleRequest"></a>

### DisableRoleRequest
============================================================================
DisableRoleRequest - transitions role to DISABLED
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_id | [string](#string) |  | UUID of the role to disable. |
| allow_missing | [bool](#bool) |  | When true, a missing role_id returns OK instead of NOT_FOUND, so retries are safe after partial-success scenarios (AIP-135). |






<a name="sso-roles-v1-EnableRoleRequest"></a>

### EnableRoleRequest
============================================================================
EnableRoleRequest - transitions role back to ACTIVE
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_id | [string](#string) |  | UUID of the role to reactivate. |
| allow_missing | [bool](#bool) |  | See DisableRoleRequest.allow_missing. |






<a name="sso-roles-v1-GetRoleRequest"></a>

### GetRoleRequest
============================================================================
GetRoleRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_id | [string](#string) |  | UUID of the role to retrieve. |






<a name="sso-roles-v1-ListRolesRequest"></a>

### ListRolesRequest
============================================================================
ListRolesRequest - paginated list of roles in an app
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  | Page size (0-1000). 0 means &#34;server default&#34;. Negative values rejected with INVALID_ARGUMENT (AIP-158). |
| page_token | [string](#string) |  | Opaque pagination token from the previous response. Empty string for the first page. |
| filters | [RoleFilters](#sso-roles-v1-RoleFilters) |  | Filters applied to the listing. app_id inside is required. |
| order_by | [ListRolesOrderBy](#sso-roles-v1-ListRolesOrderBy) |  | Typed sort order (AIP-132). UNSPECIFIED selects the server default. Tie-breaker role_id is always appended implicitly. |






<a name="sso-roles-v1-ListRolesResponse"></a>

### ListRolesResponse
============================================================================
ListRolesResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| roles | [Role](#sso-roles-v1-Role) | repeated | Roles for the current page. |
| next_page_token | [string](#string) |  | Opaque token to fetch the next page. Empty if this was the last page. |
| total_size | [int32](#int32) | optional | Total number of roles matching the filters across all pages. May be approximate. Unset =&gt; server did not compute a total; set to 0 =&gt; genuinely no matches. |






<a name="sso-roles-v1-PermanentlyDeleteRoleRequest"></a>

### PermanentlyDeleteRoleRequest
============================================================================
PermanentlyDeleteRoleRequest - permanently removes a role
============================================================================
Destructive confirmation: requires an etag matching the current server
Role.etag (stronger than a boolean; prevents accidental deletion based
on a stale read or a copy-pasted request body).

Cascade to assignments: if the role has active assignments in
AccessService, allow_cascade = true is required; otherwise the request
is rejected with FAILED_PRECONDITION. With allow_cascade = true, all
assignments of the role are removed atomically as part of the deletion.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_id | [string](#string) |  | UUID of the role to delete. |
| etag | [string](#string) |  | Current Role.etag observed by the caller. &#34;*&#34; is NOT accepted. |
| allow_cascade | [bool](#bool) |  | When true, cascades the delete to active role assignments in AccessService. Required if any assignments exist. |






<a name="sso-roles-v1-Role"></a>

### Role
============================================================================
Role - canonical role definition (response type)
============================================================================
Output-only fields (etag, timestamps) are set by the server and ignored
on input.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_id | [string](#string) |  | Role UUID (RFC 4122). |
| app_id | [string](#string) |  | UUID of the app this role belongs to. Immutable. |
| name | [string](#string) |  | Role name. Unique per app, case-sensitive (1-128 chars). |
| description | [string](#string) |  | Human-readable description (0-1024 chars). Empty if not set. |
| permissions | [string](#string) | repeated | Permissions granted by this role in &#34;resource:action&#34; form (e.g. &#34;users:read&#34;, &#34;apps:*&#34;). Interpreted by downstream apps. Up to 128 entries per role; each entry follows the canonical grammar described in the service-level comment above. The pattern mirrors AccessService.CheckPermissionRequest.permission but additionally allows `*` on the action side to express wildcards. |
| status | [RoleStatus](#sso-roles-v1-RoleStatus) |  | Current lifecycle status. |
| etag | [string](#string) |  | Opaque version token for optimistic concurrency (AIP-154). Send back in UpdateRoleRequest.etag to detect concurrent modifications. |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Role creation timestamp (output-only). |
| updated_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Last update timestamp (output-only). Refreshed on UpdateRole, DisableRole, EnableRole. |






<a name="sso-roles-v1-RoleFilters"></a>

### RoleFilters
============================================================================
RoleFilters - filtering options for ListRoles
============================================================================
Semantics:
  - app_id scopes the listing to a single app (required).
  - search is a case-insensitive substring match over name and description
    (OR between fields).
  - If statuses is empty, both ACTIVE and DISABLED roles are returned.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  | UUID of the target app. Required - roles are always listed per app. |
| search | [string](#string) |  | Free-text search across name and description (max 128 chars). |
| statuses | [RoleStatus](#sso-roles-v1-RoleStatus) | repeated | Filter by role lifecycle status (OR logic). Empty list = no filter. |






<a name="sso-roles-v1-UpdateRoleRequest"></a>

### UpdateRoleRequest
============================================================================
UpdateRoleRequest - FieldMask-based partial update (AIP-134)
============================================================================
Only fields listed in update_mask are applied. A field omitted from the
mask is left unchanged; a field present in the mask with an empty value
clears the field (where permitted).

Valid mask paths (SERVER MUST REJECT any other path with INVALID_ARGUMENT):
  name
  description
  permissions

Explicitly INVALID mask paths (server MUST reject):
  role_id, app_id     (immutable identity and parenthood)
  status              (lifecycle; use DisableRole / EnableRole)
  etag                (server-managed; use the top-level etag field)
  created_at, updated_at (output-only timestamps)

The `Role role` payload MAY carry values for any field (including
immutable ones); the server MUST IGNORE any field whose path is not in
update_mask. Populating `status` in `role` without &#34;status&#34; in the mask
MUST be a silent no-op, never a hidden write.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_id | [string](#string) |  | UUID of the role to update (required). |
| role | [Role](#sso-roles-v1-Role) |  | New field values. Fields not referenced by update_mask are ignored. |
| update_mask | [google.protobuf.FieldMask](#google-protobuf-FieldMask) |  | Set of field paths to apply from `role`. Must be non-empty. |
| etag | [string](#string) |  | Required optimistic concurrency token. &#34;*&#34; means unconditional update. |





 


<a name="sso-roles-v1-ListRolesOrderBy"></a>

### ListRolesOrderBy
============================================================================
ListRolesOrderBy - supported sort orders for ListRoles (AIP-132 typed)
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| LIST_ROLES_ORDER_BY_UNSPECIFIED | 0 | Server default (currently CREATED_AT_DESC). |
| LIST_ROLES_ORDER_BY_CREATED_AT_DESC | 1 |  |
| LIST_ROLES_ORDER_BY_CREATED_AT_ASC | 2 |  |
| LIST_ROLES_ORDER_BY_ROLE_ID_DESC | 3 |  |
| LIST_ROLES_ORDER_BY_ROLE_ID_ASC | 4 |  |
| LIST_ROLES_ORDER_BY_NAME_DESC | 5 |  |
| LIST_ROLES_ORDER_BY_NAME_ASC | 6 |  |



<a name="sso-roles-v1-RoleStatus"></a>

### RoleStatus
============================================================================
RoleStatus - lifecycle state of a role
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| ROLE_STATUS_UNSPECIFIED | 0 |  |
| ROLE_STATUS_ACTIVE | 1 | Role is active; its permissions take effect for assigned users. |
| ROLE_STATUS_DISABLED | 2 | Role is temporarily disabled; permissions do not take effect, but assignments are preserved. Reversible via EnableRole. |


 

 


<a name="sso-roles-v1-RolesService"></a>

### RolesService
============================================================================
RolesService - Role Definition Management
============================================================================
Defines roles (named bundles of permissions) scoped to a specific
application. Roles are DEFINED here but NOT assigned to users - user-role
assignments live in AccessService.

Permission model:
  Each role carries a flat list of permission strings in the canonical
  &#34;resource:action&#34; form (e.g. &#34;users:read&#34;, &#34;apps:write&#34;). The &#34;*&#34; action
  acts as a wildcard within a resource (e.g. &#34;users:*&#34; grants all user
  actions). Permission semantics are opaque to RolesService; downstream
  apps interpret them at their discretion.

  Canonical permission grammar (validated on CreateRole / UpdateRole):
    resource := [a-z][a-z0-9_]*                      // strict
    action   := [a-z][a-z0-9_]*   |   *              // wildcard only on action
    permission := resource &#34;:&#34; action
  Length: 3-64 characters, identical to the consumer-side pattern in
  AccessService.CheckPermissionRequest.permission. The &#34;*:*&#34; form is
  NOT allowed as a &#34;grant everything&#34; shortcut - such grants MUST be
  enumerated per resource.

Lifecycle:
  ACTIVE   - role is enabled; its permissions take effect for every
             user currently assigned this role in AccessService.
  DISABLED - role is temporarily inactive. Assignments are preserved,
             but the role&#39;s permissions do NOT take effect at runtime.
             Reversible via EnableRole.
  (deleted) - DeleteRole removes the role permanently; see Cascade below.

Cascade:
  - PermanentlyDeleteApp on the parent app cascades: all roles in that
    app and all their assignments are removed.
  - DeleteRole with force = true cascades to AccessService: every active
    assignment of the role is removed as part of the deletion.

Security:
  All RPCs are authenticated; access is role-based within the target app.
    ROLE_READ   - GetRole, ListRoles
    ROLE_WRITE  - CreateRole, UpdateRole, DisableRole, EnableRole
    ROLE_DELETE - PermanentlyDeleteRole
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetRole | [GetRoleRequest](#sso-roles-v1-GetRoleRequest) | [Role](#sso-roles-v1-Role) | GetRole returns a role definition by UUID.

Errors: NOT_FOUND - role does not exist PERMISSION_DENIED - caller lacks ROLE_READ on the role&#39;s app INVALID_ARGUMENT - role_id is not a valid UUID |
| ListRoles | [ListRolesRequest](#sso-roles-v1-ListRolesRequest) | [ListRolesResponse](#sso-roles-v1-ListRolesResponse) | ListRoles returns a paginated list of roles within an app.

By default, both ACTIVE and DISABLED roles are included. To filter, set RoleFilters.statuses.

Errors: PERMISSION_DENIED - caller lacks ROLE_READ on the target app NOT_FOUND - target app does not exist INVALID_ARGUMENT - invalid page_token / page_size / filters |
| CreateRole | [CreateRoleRequest](#sso-roles-v1-CreateRoleRequest) | [Role](#sso-roles-v1-Role) | CreateRole creates a new role in the target app.

Role names must be unique per app (case-sensitive).

Errors: ALREADY_EXISTS - a role with this name already exists in the app NOT_FOUND - target app does not exist PERMISSION_DENIED - caller lacks ROLE_WRITE on the target app INVALID_ARGUMENT - app_id / name / description / permissions failed validation |
| UpdateRole | [UpdateRoleRequest](#sso-roles-v1-UpdateRoleRequest) | [Role](#sso-roles-v1-Role) | UpdateRole partially updates a role definition.

The set of fields to apply is driven by update_mask (AIP-134). Valid mask paths: name, description, permissions. role_id, app_id, status, etag and timestamps are NOT updatable here. Use DisableRole / EnableRole to change status, and DeleteRole to remove.

Optimistic concurrency: if etag is provided and does not match the server-side value, the request is rejected with ABORTED.

Errors: NOT_FOUND - role does not exist ABORTED - etag mismatch (concurrent modification) ALREADY_EXISTS - rename collides with an existing role in the app PERMISSION_DENIED - caller lacks ROLE_WRITE on the role&#39;s app INVALID_ARGUMENT - empty mask, unknown mask path, or invalid value |
| DisableRole | [DisableRoleRequest](#sso-roles-v1-DisableRoleRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | DisableRole transitions the role to DISABLED. Idempotent.

Permissions carried by the role stop taking effect at runtime; assignments are preserved so the role can be reactivated later. If allow_missing=true, NOT_FOUND is converted to a successful no-op.

Errors: NOT_FOUND - role does not exist (suppressed if allow_missing) PERMISSION_DENIED - caller lacks ROLE_WRITE on the role&#39;s app INVALID_ARGUMENT - role_id is not a valid UUID |
| EnableRole | [EnableRoleRequest](#sso-roles-v1-EnableRoleRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | EnableRole transitions the role back to ACTIVE. Idempotent. If allow_missing=true, NOT_FOUND is converted to a successful no-op.

Errors: NOT_FOUND - role does not exist (suppressed if allow_missing) PERMISSION_DENIED - caller lacks ROLE_WRITE on the role&#39;s app INVALID_ARGUMENT - role_id is not a valid UUID |
| PermanentlyDeleteRole | [PermanentlyDeleteRoleRequest](#sso-roles-v1-PermanentlyDeleteRoleRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | PermanentlyDeleteRole removes a role permanently.

Destructive confirmation: requires an etag matching the current server-side Role.etag (prevents accidental deletion based on a stale read).

Cascade: if the role has active assignments in AccessService, the request is rejected with FAILED_PRECONDITION unless allow_cascade is true. When allow_cascade=true, all assignments of the role are removed atomically as part of the deletion.

Errors: NOT_FOUND - role does not exist FAILED_PRECONDITION - role has active assignments and allow_cascade != true ABORTED - supplied etag does not match current Role.etag (ERROR_REASON_ETAG_MISMATCH) PERMISSION_DENIED - caller lacks ROLE_DELETE on the role&#39;s app INVALID_ARGUMENT - role_id is not a valid UUID, or etag missing |

 



<a name="sso_access_v1_access-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/access/v1/access.proto



<a name="sso-access-v1-BatchCheckPermissionRequest"></a>

### BatchCheckPermissionRequest
============================================================================
BatchCheckPermissionRequest - payload for BatchCheckPermission
============================================================================
Up to 32 permissions in one call. The cap matches BulkGrantRoles for
consistency across the service; the rationale is a realistic UI-render
footprint (sidebar menu, screen-level toolbar) rather than bulk
admin operations.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user whose permissions are being checked. |
| app_id | [string](#string) |  | UUID of the app in which to evaluate the permissions. |
| permissions | [string](#string) | repeated | Permissions to evaluate, each in canonical &#34;resource:action&#34; form. Same validation rules as CheckPermissionRequest.permission. |






<a name="sso-access-v1-BatchCheckPermissionResponse"></a>

### BatchCheckPermissionResponse
============================================================================
BatchCheckPermissionResponse
============================================================================
Positionally aligned with the request: allowed[i] corresponds to
BatchCheckPermissionRequest.permissions[i]. Length is guaranteed equal
to the request length.

Unlike CheckPermissionResponse, matched_role_ids is intentionally NOT
returned here - exposing N x M matched-role sets in one batch would
both balloon the response and multiply the RBAC-disclosure surface
flagged on CheckPermissionResponse. Callers that need attribution
should fall back to the single CheckPermission for that permission.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| allowed | [bool](#bool) | repeated |  |






<a name="sso-access-v1-BulkGrantRolesRequest"></a>

### BulkGrantRolesRequest
============================================================================
BulkGrantRolesRequest - payload for BulkGrantRoles
============================================================================
app_id is an explicit scope: all role_ids must belong to this app or
the request is rejected wholesale. This guards against accidentally
mixing roles from different apps in one bulk call.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user to grant roles to. |
| app_id | [string](#string) |  | UUID of the target app. All role_ids MUST belong to this app. |
| role_ids | [string](#string) | repeated | UUIDs of the roles to grant (1-32 items). |






<a name="sso-access-v1-BulkGrantRolesResponse"></a>

### BulkGrantRolesResponse
============================================================================
BulkGrantRolesResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| role_assignments | [RoleAssignment](#sso-access-v1-RoleAssignment) | repeated | All assignments for the requested (user, role) pairs after the call completes - both newly created and pre-existing. Order matches the role_ids order in the request. |
| newly_created | [bool](#bool) | repeated | Parallel to role_assignments: true for assignments created by this call, false for pre-existing ones (idempotent re-grants). Useful for audit trails. Length always equals len(role_assignments). |






<a name="sso-access-v1-BulkRemoveRolesRequest"></a>

### BulkRemoveRolesRequest
============================================================================
BulkRemoveRolesRequest - payload for BulkRemoveRoles
============================================================================
app_id is an explicit scope; same safety semantics as BulkGrantRoles.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user whose assignments should be removed. |
| app_id | [string](#string) |  | UUID of the target app. All role_ids MUST belong to this app. |
| role_ids | [string](#string) | repeated | UUIDs of the roles to remove (1-32 items). |






<a name="sso-access-v1-CheckPermissionRequest"></a>

### CheckPermissionRequest
============================================================================
CheckPermissionRequest - payload for CheckPermission
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user whose permissions are being checked. |
| app_id | [string](#string) |  | UUID of the app in which to evaluate the permission. |
| permission | [string](#string) |  | Permission in canonical &#34;resource:action&#34; form (e.g. &#34;users:read&#34;, &#34;apps:write&#34;). Wildcards in role-side permissions (&#34;users:*&#34;) match concrete actions here; the request itself must be concrete.

Pattern: `^[a-z][a-z0-9_]*:[a-z][a-z0-9_]*$`. Lowercase identifiers separated by a single colon; wildcard &#34;*&#34; is NOT accepted on the request side (only in role definitions). Malformed strings are rejected with INVALID_ARGUMENT / VALIDATION_FAILED. |






<a name="sso-access-v1-CheckPermissionResponse"></a>

### CheckPermissionResponse
============================================================================
CheckPermissionResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| allowed | [bool](#bool) |  | True if at least one ACTIVE role assigned to the user in the app carries a permission that matches the requested one. |
| matched_role_ids | [string](#string) | repeated | UUIDs of the roles that contributed to the allow decision. Empty if allowed == false. Useful for audit trails and debugging unexpected grants; do not rely on the order.

SECURITY: this field exposes the internal RBAC structure of the target app. The RPC is intended for INTERNAL service-to-service callers only. Deployments MUST reject CheckPermission at ingress from untrusted clients, or strip matched_role_ids at the gateway before returning the response to end-user clients. |






<a name="sso-access-v1-GrantRoleToUserRequest"></a>

### GrantRoleToUserRequest
============================================================================
GrantRoleToUserRequest - payload for GrantRoleToUser
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user to grant the role to. |
| role_id | [string](#string) |  | UUID of the role to grant. The app is derived from the role. |






<a name="sso-access-v1-HasRoleInAppRequest"></a>

### HasRoleInAppRequest
============================================================================
HasRoleInAppRequest - payload for HasRoleInApp
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user to check. |
| role_id | [string](#string) |  | UUID of the role. The target app is determined by the role. |






<a name="sso-access-v1-HasRoleInAppResponse"></a>

### HasRoleInAppResponse
============================================================================
HasRoleInAppResponse - result of HasRoleInApp
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| has_role | [bool](#bool) |  | True if the user currently has an assignment for this role. DISABLED roles still return true here - the assignment exists. |






<a name="sso-access-v1-ListUserRolesRequest"></a>

### ListUserRolesRequest
============================================================================
ListUserRolesRequest - paginated list of a user&#39;s roles in an app
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  | Maximum number of items per page (0-1000). 0 means &#34;server default&#34;. Negative values rejected with INVALID_ARGUMENT (AIP-158). |
| page_token | [string](#string) |  | Opaque pagination token from the previous response. Empty string for the first page. |
| user_id | [string](#string) |  | UUID of the user to list roles for. |
| app_id | [string](#string) |  | UUID of the app to scope the listing to. |
| order_by | [ListUserRolesOrderBy](#sso-access-v1-ListUserRolesOrderBy) |  | Typed sort order (AIP-132). UNSPECIFIED selects the server default. Tie-breaker role_id is always appended implicitly. |






<a name="sso-access-v1-ListUserRolesResponse"></a>

### ListUserRolesResponse
============================================================================
ListUserRolesResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| roles | [sso.roles.v1.Role](#sso-roles-v1-Role) | repeated | Roles currently assigned to the user in the target app. Includes DISABLED roles (status carried on each Role). |
| next_page_token | [string](#string) |  | Opaque token to fetch the next page. Empty if this was the last page. |
| total_size | [int32](#int32) | optional | Total number of assignments matching the request across all pages. May be approximate. Unset =&gt; server did not compute a total; set to 0 =&gt; genuinely no matches. |






<a name="sso-access-v1-RemoveRoleFromUserRequest"></a>

### RemoveRoleFromUserRequest
============================================================================
RemoveRoleFromUserRequest - payload for RemoveRoleFromUser
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user whose assignment should be removed. |
| role_id | [string](#string) |  | UUID of the role to remove. The app is derived from the role. |






<a name="sso-access-v1-RoleAssignment"></a>

### RoleAssignment
============================================================================
RoleAssignment - the (user x role) relationship with audit metadata
============================================================================
Returned by GrantRoleToUser and BulkGrantRoles so callers can observe
the audit trail without a follow-up read.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | UUID of the user this assignment is for. |
| role_id | [string](#string) |  | UUID of the assigned role. |
| app_id | [string](#string) |  | UUID of the app the role belongs to. Denormalized from the role for server-side indexing and client-side display; always equals Role.app_id looked up by role_id. |
| granted_by_user_id | [string](#string) |  | UUID of the user who created the assignment. Derived by the server from the caller&#39;s access_token at grant time. |
| granted_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Timestamp when the assignment was created. Set once on creation and preserved across idempotent re-grants. |





 


<a name="sso-access-v1-ListUserRolesOrderBy"></a>

### ListUserRolesOrderBy
============================================================================
ListUserRolesOrderBy - supported sort orders (AIP-132 typed)
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| LIST_USER_ROLES_ORDER_BY_UNSPECIFIED | 0 | Server default (currently GRANTED_AT_DESC). |
| LIST_USER_ROLES_ORDER_BY_GRANTED_AT_DESC | 1 |  |
| LIST_USER_ROLES_ORDER_BY_GRANTED_AT_ASC | 2 |  |
| LIST_USER_ROLES_ORDER_BY_ROLE_ID_DESC | 3 |  |
| LIST_USER_ROLES_ORDER_BY_ROLE_ID_ASC | 4 |  |


 

 


<a name="sso-access-v1-AccessService"></a>

### AccessService
============================================================================
AccessService - Role Assignments &amp; Authorization Decisions
============================================================================
Manages the user-to-role relationship within apps:
  - grant / revoke role assignments
  - introspect which roles a user holds
  - answer authorization queries (does user have permission X?)

Role definitions themselves live in RolesService. Assignments here
reference roles by role_id; each role already carries its app_id, so
for single-user operations the target app is determined by the role.
Bulk operations take an explicit app_id as a safety guard against
mixing roles from different apps in one request.

Resource model:
  RoleAssignment is a (user x role) tuple with audit metadata
  (granted_by_user_id, granted_at). A user may hold any number of
  role assignments within a given app.

Atomicity:
  BulkGrantRoles / BulkRemoveRoles are all-or-nothing: on any
  validation failure NO assignments are changed. Partial success
  is not supported.

Idempotency:
  - GrantRoleToUser        - re-granting returns the existing assignment
  - RemoveRoleFromUser     - removing a non-existent assignment is a no-op
  - BulkGrantRoles         - same semantics per entry
  - BulkRemoveRoles        - same semantics per entry

Role lifecycle &amp; assignments:
  A role can be DISABLED via RolesService.DisableRole. DISABLED roles
  continue to appear in ListUserRoles (assignments are preserved) but
  do NOT contribute to CheckPermission decisions. Granting a DISABLED
  role fails with FAILED_PRECONDITION; removing one is allowed.

Caching:
  HasRoleInApp and CheckPermission are designed as high-QPS read-only
  decision endpoints. Callers MAY cache results with a short TTL
  (30-60s typical). No cache-invalidation events are emitted -
  stale &#34;allow&#34; results may persist for up to the TTL after
  Revoke / DisableRole operations.

Security:
  All RPCs are authenticated; access is role-based within the target app.
    ACCESS_READ  - HasRoleInApp, ListUserRoles, CheckPermission
    ACCESS_WRITE - GrantRoleToUser, RemoveRoleFromUser
    ACCESS_ADMIN - BulkGrantRoles, BulkRemoveRoles
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| HasRoleInApp | [HasRoleInAppRequest](#sso-access-v1-HasRoleInAppRequest) | [HasRoleInAppResponse](#sso-access-v1-HasRoleInAppResponse) | HasRoleInApp checks whether a user is assigned the given role. The target app is determined by the role (role_id -&gt; Role.app_id).

Safe to cache briefly. Idempotent, side-effect-free.

Errors: NOT_FOUND - user or role does not exist PERMISSION_DENIED - caller lacks ACCESS_READ on the role&#39;s app INVALID_ARGUMENT - user_id or role_id is not a valid UUID |
| ListUserRoles | [ListUserRolesRequest](#sso-access-v1-ListUserRolesRequest) | [ListUserRolesResponse](#sso-access-v1-ListUserRolesResponse) | ListUserRoles returns a paginated list of roles assigned to the user within the target app. Includes both ACTIVE and DISABLED roles - disabled roles remain assigned but are ignored at permission-check time.

Errors: NOT_FOUND - user or app does not exist PERMISSION_DENIED - caller lacks ACCESS_READ on the target app INVALID_ARGUMENT - invalid page_size / page_token / ids |
| GrantRoleToUser | [GrantRoleToUserRequest](#sso-access-v1-GrantRoleToUserRequest) | [RoleAssignment](#sso-access-v1-RoleAssignment) | GrantRoleToUser creates a role assignment for the user. The app is derived from the role. Idempotent: repeated grants return the existing RoleAssignment unchanged (including original granted_at).

Errors: NOT_FOUND - user or role does not exist FAILED_PRECONDITION - role is DISABLED, or user is BLOCKED/DELETED PERMISSION_DENIED - caller lacks ACCESS_WRITE on the role&#39;s app INVALID_ARGUMENT - user_id or role_id is not a valid UUID |
| RemoveRoleFromUser | [RemoveRoleFromUserRequest](#sso-access-v1-RemoveRoleFromUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | RemoveRoleFromUser removes a role assignment. Idempotent: removing a non-existent assignment succeeds with no effect.

Errors: NOT_FOUND - user or role does not exist PERMISSION_DENIED - caller lacks ACCESS_WRITE on the role&#39;s app INVALID_ARGUMENT - user_id or role_id is not a valid UUID |
| BulkGrantRoles | [BulkGrantRolesRequest](#sso-access-v1-BulkGrantRolesRequest) | [BulkGrantRolesResponse](#sso-access-v1-BulkGrantRolesResponse) | BulkGrantRoles atomically grants up to 32 roles to one user within one app. All role_ids MUST belong to the given app_id - this is verified server-side as a safety guard against cross-app bulk ops.

Why the 32-item limit: - each entry requires a uniqueness/existence check &#43; insert &#43; audit-event emission inside one DB transaction; 32 is the empirical cap that keeps lock hold-time below the hot-path budget on the smallest supported database tier; - admin UIs typically commit role changes in small batches (a single screen / dialog), so 32 covers realistic UX flows; - larger bulk reshuffles (tenant onboarding, role-model migration) are expected to iterate in chunks of &lt;=32 rather than enlarge this limit.

All-or-nothing: on any validation failure, NO assignments are created. Idempotent per entry: pre-existing assignments are returned alongside the newly created ones.

Errors: NOT_FOUND - user, app, or any role does not exist FAILED_PRECONDITION - any role is DISABLED, any role does not belong to app_id, or user is BLOCKED/DELETED PERMISSION_DENIED - caller lacks ACCESS_ADMIN on the target app INVALID_ARGUMENT - invalid UUIDs, empty role_ids, or &gt;32 items |
| BulkRemoveRoles | [BulkRemoveRolesRequest](#sso-access-v1-BulkRemoveRolesRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | BulkRemoveRoles atomically removes up to 32 role assignments from one user within one app. All role_ids MUST belong to the given app_id. See BulkGrantRoles for the rationale behind the 32-item cap.

All-or-nothing: on any validation failure, NO assignments are removed. Idempotent per entry: non-existent assignments are silently ignored.

Errors: NOT_FOUND - user or app does not exist FAILED_PRECONDITION - any role does not belong to app_id PERMISSION_DENIED - caller lacks ACCESS_ADMIN on the target app INVALID_ARGUMENT - invalid UUIDs, empty role_ids, or &gt;32 items |
| BatchCheckPermission | [BatchCheckPermissionRequest](#sso-access-v1-BatchCheckPermissionRequest) | [BatchCheckPermissionResponse](#sso-access-v1-BatchCheckPermissionResponse) | BatchCheckPermission answers multiple permission queries in one round trip. Semantics per entry are identical to CheckPermission; this is purely a latency optimization for UIs that need to render capability-dependent elements (buttons, menu items, tabs) whose visibility depends on several permissions at once.

The response is positionally aligned with the request: allowed[i] corresponds to permissions[i]. matched_role_ids is NOT returned in batch form - if an UI needs attribution, it should call the single CheckPermission for that specific permission.

Same caching guidance as CheckPermission (30-60s typical).

Errors: NOT_FOUND - user or app does not exist PERMISSION_DENIED - caller lacks ACCESS_READ on the target app INVALID_ARGUMENT - invalid UUIDs; empty / &gt;32 permissions list; any permission fails the canonical pattern |
| CheckPermission | [CheckPermissionRequest](#sso-access-v1-CheckPermissionRequest) | [CheckPermissionResponse](#sso-access-v1-CheckPermissionResponse) | CheckPermission returns whether the user holds the given permission in the target app via any of their currently assigned ACTIVE roles.

DISABLED roles do not contribute to the decision. Wildcard actions in role permissions (e.g. &#34;users:*&#34;) match concrete actions (&#34;users:read&#34;, &#34;users:write&#34;).

High-QPS endpoint; safe to cache results briefly (30-60s typical).

Errors: NOT_FOUND - user or app does not exist PERMISSION_DENIED - caller lacks ACCESS_READ on the target app INVALID_ARGUMENT - invalid UUIDs or malformed permission string |

 



<a name="sso_app_v1_app-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/app/v1/app.proto



<a name="sso-app-v1-App"></a>

### App
============================================================================
App - Complete application model
============================================================================
Field-level constraints are enforced on input (CreateApp, UpdateApp)
and apply to the same named paths in UpdateAppRequest.update_mask.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  | Unique application identifier (RFC 4122 UUID format). Server-assigned on CreateApp; ignored on input. |
| name | [string](#string) |  | Human-readable application name (1-128 characters, unique). |
| link | [string](#string) |  | Entry-point URL of the application (valid URI, max 2048 chars). Example: &#34;https://myapp.example.com/dashboard&#34;. |
| status | [AppStatus](#sso-app-v1-AppStatus) |  | Current application status. Server-assigned on create (always ACTIVE); on update this path is invalid - use Enable/Disable/EnterMaintenance /ExitMaintenance RPCs. |
| etag | [string](#string) |  | Opaque version token for optimistic concurrency (AIP-154). Server-managed; send the observed value back in UpdateAppRequest.etag / PermanentlyDeleteAppRequest.etag. |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Timestamp of app creation (output-only). |
| updated_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Timestamp of last app update (output-only). |
| slug | [string](#string) |  | URL-safe stable identifier used in human-facing contexts (CLI, URL paths like /apps/{slug}/login). Unique across all apps. Pattern: starts with a lowercase letter, 3-64 chars total, lowercase letters / digits / hyphens only. Immutable after CreateApp - not updatable via UpdateApp. |






<a name="sso-app-v1-AppFilters"></a>

### AppFilters
============================================================================
AppFilters - Filtering options for ListApps
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| search | [string](#string) |  | Full-text search across name, link, and slug fields. Length aligned with UserFilters.search / RoleFilters.search. |
| statuses | [AppStatus](#sso-app-v1-AppStatus) | repeated | Filter by application statuses (OR logic) |






<a name="sso-app-v1-CreateAppRequest"></a>

### CreateAppRequest
============================================================================
CreateAppRequest - AIP-133 create
============================================================================
Shape: the resource to create (`app`). The server populates app_id,
status (always ACTIVE on creation), etag, created_at, updated_at;
any client-supplied values for those fields are ignored.

Fields the client MUST populate in `app`:
  name, link, slug
Field-level constraints (min/max/pattern) live on the App message;
see App.name / App.link / App.slug.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app | [App](#sso-app-v1-App) |  | App definition. Server-managed fields are ignored. |






<a name="sso-app-v1-DisableAppRequest"></a>

### DisableAppRequest
DisableAppRequest sets app status to DISABLED (reversible via EnableApp).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | See EnableAppRequest.allow_missing. |






<a name="sso-app-v1-EnableAppRequest"></a>

### EnableAppRequest
============================================================================
Lifecycle-transition requests
============================================================================
EnableAppRequest reactivates a DISABLED app.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | When true, a missing app_id returns OK instead of NOT_FOUND, so retries are safe after partial-success scenarios (AIP-135). |






<a name="sso-app-v1-EnterMaintenanceModeRequest"></a>

### EnterMaintenanceModeRequest
EnterMaintenanceModeRequest transitions app to MAINTENANCE status.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | See EnableAppRequest.allow_missing. |






<a name="sso-app-v1-ExitMaintenanceModeRequest"></a>

### ExitMaintenanceModeRequest
ExitMaintenanceModeRequest returns app from MAINTENANCE back to ACTIVE.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | See EnableAppRequest.allow_missing. |






<a name="sso-app-v1-GetAppRequest"></a>

### GetAppRequest
============================================================================
GetAppRequest - Request for GetApp RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  | UUID of the application to retrieve |






<a name="sso-app-v1-ListAppsRequest"></a>

### ListAppsRequest
============================================================================
ListAppsRequest - Paginated request for ListApps RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  | Maximum number of items to return per page (0-1000). Use 0 for default page size. Negative values rejected with INVALID_ARGUMENT (AIP-158). |
| page_token | [string](#string) |  | Opaque pagination token from previous response Empty string for first page |
| filters | [AppFilters](#sso-app-v1-AppFilters) |  | Optional filters to apply to the list |
| order_by | [ListAppsOrderBy](#sso-app-v1-ListAppsOrderBy) |  | Typed sort order (AIP-132). UNSPECIFIED selects the server default. Tie-breaker app_id is always appended implicitly. |






<a name="sso-app-v1-ListAppsResponse"></a>

### ListAppsResponse
============================================================================
ListAppsResponse - Paginated response for ListApps RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| apps | [App](#sso-app-v1-App) | repeated | Page of applications matching the request |
| next_page_token | [string](#string) |  | Opaque token to fetch the next page Empty string if this was the last page |
| total_size | [int32](#int32) | optional | Total number of apps matching the request across all pages. May be approximate. Unset =&gt; server did not compute a total; set to 0 =&gt; genuinely no matches. |






<a name="sso-app-v1-PermanentlyDeleteAppRequest"></a>

### PermanentlyDeleteAppRequest
PermanentlyDeleteAppRequest requires an etag matching the current
App.etag as explicit, concurrency-safe confirmation. Cascade is
implicit: all roles in this app and all role assignments in
AccessService are removed atomically with the app.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  |  |
| etag | [string](#string) |  | Current App.etag observed by the caller. &#34;*&#34; is NOT accepted. |






<a name="sso-app-v1-UpdateAppRequest"></a>

### UpdateAppRequest
============================================================================
UpdateAppRequest - FieldMask-based partial update (AIP-134)
============================================================================
Only fields listed in update_mask are applied. A field omitted from the
mask is left unchanged; a field present in the mask with an empty value
clears the field (where permitted).

Valid mask paths (SERVER MUST REJECT any other path with INVALID_ARGUMENT):
  name
  link

Explicitly INVALID mask paths (server MUST reject):
  app_id              (immutable identity)
  slug                (immutable after creation)
  status              (lifecycle; use Enable/Disable/EnterMaintenance
                       /ExitMaintenance RPCs)
  etag                (server-managed; use the top-level etag field)
  created_at, updated_at (output-only timestamps)

The `App app` payload MAY carry values for any field (including
immutable ones); the server MUST IGNORE any field whose path is not in
update_mask. Populating `status` or `slug` in `app` without placing
them in the mask MUST be a silent no-op, never a hidden write.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  | UUID of the application to update (required). |
| app | [App](#sso-app-v1-App) |  | New field values. Fields not referenced by update_mask are ignored. |
| update_mask | [google.protobuf.FieldMask](#google-protobuf-FieldMask) |  | Set of field paths to apply from `app`. Must be non-empty. |
| etag | [string](#string) |  | Required optimistic concurrency token. &#34;*&#34; means unconditional update. |





 


<a name="sso-app-v1-AppStatus"></a>

### AppStatus
============================================================================
AppStatus - Application status enum
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| APP_STATUS_UNSPECIFIED | 0 |  |
| APP_STATUS_ACTIVE | 1 | ACTIVE - application is fully operational and accessible via SSO |
| APP_STATUS_DISABLED | 2 | DISABLED - application is disabled (reversible via EnableApp) |
| APP_STATUS_MAINTENANCE | 3 | MAINTENANCE - application is under maintenance, temporarily unavailable |



<a name="sso-app-v1-ListAppsOrderBy"></a>

### ListAppsOrderBy
============================================================================
ListAppsOrderBy - supported sort orders for ListApps (AIP-132 typed)
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| LIST_APPS_ORDER_BY_UNSPECIFIED | 0 | Server default (currently CREATED_AT_DESC). |
| LIST_APPS_ORDER_BY_CREATED_AT_DESC | 1 |  |
| LIST_APPS_ORDER_BY_CREATED_AT_ASC | 2 |  |
| LIST_APPS_ORDER_BY_APP_ID_DESC | 3 |  |
| LIST_APPS_ORDER_BY_APP_ID_ASC | 4 |  |
| LIST_APPS_ORDER_BY_NAME_DESC | 5 |  |
| LIST_APPS_ORDER_BY_NAME_ASC | 6 |  |


 

 


<a name="sso-app-v1-AppService"></a>

### AppService
============================================================================
AppService - App Management API
============================================================================
Provides full CRUD operations for application management in Single Sign-On system.
Each app represents a service that can be accessed via SSO authentication.

Lifecycle:
 ACTIVE - active app
 DISABLED - disabled app
 MAINTENANCE - app on maintenance

Possible errors:
  - NotFound: app not found
  - InvalidArgument: invalid request parameters
  - PermissionDenied: insufficient permissions
  - AlreadyExists: app with same name already exists
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetApp | [GetAppRequest](#sso-app-v1-GetAppRequest) | [App](#sso-app-v1-App) | GetApp returns application by UUID Request: valid UUID format Response: full App object Error: NotFound if app doesn&#39;t exist |
| ListApps | [ListAppsRequest](#sso-app-v1-ListAppsRequest) | [ListAppsResponse](#sso-app-v1-ListAppsResponse) | ListApps returns paginated list of applications with filtering Supports: search across name/link, filter by statuses Use page_token for pagination (empty for first page) Max page_size: 1000 items per page |
| CreateApp | [CreateAppRequest](#sso-app-v1-CreateAppRequest) | [App](#sso-app-v1-App) | CreateApp registers a new application in SSO Required fields: name (1-128 chars), link (valid URI) Returns created App object with generated UUID and timestamps |
| UpdateApp | [UpdateAppRequest](#sso-app-v1-UpdateAppRequest) | [App](#sso-app-v1-App) | UpdateApp partially updates an application. The set of fields to update is driven by update_mask (AIP-134). Optimistic concurrency: if etag is provided and does not match the server-side value, the request is rejected with ABORTED. Returns updated App object. |
| EnterMaintenanceMode | [EnterMaintenanceModeRequest](#sso-app-v1-EnterMaintenanceModeRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | EnterMaintenanceMode transitions app status to MAINTENANCE. Idempotent. If allow_missing=true, NOT_FOUND is converted to a successful no-op. |
| ExitMaintenanceMode | [ExitMaintenanceModeRequest](#sso-app-v1-ExitMaintenanceModeRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | ExitMaintenanceMode returns app from MAINTENANCE back to ACTIVE. Idempotent. If allow_missing=true, NOT_FOUND is converted to a successful no-op. |
| DisableApp | [DisableAppRequest](#sso-app-v1-DisableAppRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | DisableApp sets app status to DISABLED. Reversible via EnableApp. Idempotent. If allow_missing=true, NOT_FOUND is converted to a successful no-op. |
| EnableApp | [EnableAppRequest](#sso-app-v1-EnableAppRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | EnableApp sets app status to ACTIVE (reverses DisableApp). Idempotent. If allow_missing=true, NOT_FOUND is converted to a successful no-op. |
| PermanentlyDeleteApp | [PermanentlyDeleteAppRequest](#sso-app-v1-PermanentlyDeleteAppRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | PermanentlyDeleteApp removes all app data irreversibly. Cascade: all roles defined in this app and all their role assignments in AccessService are removed atomically.

Destructive confirmation: requires an etag matching the current App.etag (stronger than a boolean; prevents accidental deletion based on a stale read).

Errors: NOT_FOUND - app does not exist ABORTED - supplied etag does not match current App.etag (ERROR_REASON_ETAG_MISMATCH) PERMISSION_DENIED - caller lacks APP_DELETE role INVALID_ARGUMENT - etag missing or malformed |

 



<a name="sso_audit_v1_audit-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/audit/v1/audit.proto



<a name="sso-audit-v1-Actor"></a>

### Actor
============================================================================
Actor - who performed the action
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [ActorType](#sso-audit-v1-ActorType) |  |  |
| id | [string](#string) |  | UUID of the user or service account. Empty for SYSTEM / ANONYMOUS. |
| ip_address | [string](#string) |  | Peer IP address observed by the server. Always populated for ANONYMOUS actors; may be populated for USER / SERVICE_ACCOUNT actors depending on deployment (set by the edge proxy or the gRPC server). Empty for SYSTEM. |
| user_agent | [string](#string) |  | User-Agent string from gRPC metadata. May be empty. |






<a name="sso-audit-v1-AuditEvent"></a>

### AuditEvent
============================================================================
AuditEvent - one immutable record
============================================================================
Canonical event_type values (informative; the enum is intentionally
open so new domains can add types without a schema bump):
  user.registered, user.login.success, user.login.failed,
  user.logout, user.password_changed, user.password_reset,
  user.blocked, user.unblocked, user.deleted, user.purged,
  user.recovery_codes_generated,
  user.mfa.totp.enrolled, user.mfa.totp.disabled,
  user.mfa.challenge.issued, user.mfa.challenge.completed,
  user.mfa.challenge.failed,
  session.created, session.revoked, session.revoked_all,
  role.created, role.updated, role.disabled, role.enabled,
  role.deleted,
  role.granted, role.revoked,
  app.created, app.updated, app.disabled, app.enabled,
  app.maintenance.entered, app.maintenance.exited, app.deleted,
  service_account.created, service_account.credentials_rotated,
  service_account.disabled, service_account.enabled,
  service_account.deleted, service_account.authenticated


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event_id | [string](#string) |  | Event UUID. Immutable. |
| occurred_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | When the event was recorded (server time). |
| event_type | [string](#string) |  | Dotted namespace / action. Stable strings; see the comment above the message for canonical values. |
| actor | [Actor](#sso-audit-v1-Actor) |  | Who did it. |
| subject | [Subject](#sso-audit-v1-Subject) |  | What it targeted. |
| outcome | [AuditOutcome](#sso-audit-v1-AuditOutcome) |  | How it resolved. |
| reason | [string](#string) |  | If outcome != SUCCESS, the ErrorReason name (e.g. &#34;ERROR_REASON_INVALID_CREDENTIALS&#34;) or a free-form server code. Empty on success. |
| metadata | [AuditEvent.MetadataEntry](#sso-audit-v1-AuditEvent-MetadataEntry) | repeated | Free-form structured metadata specific to the event_type. Examples: role.granted: {&#34;role_id&#34;: &#34;...&#34;, &#34;role_name&#34;: &#34;billing-admin&#34;} user.login.failed: {&#34;identifier_kind&#34;: &#34;email&#34;} session.created: {&#34;device_name&#34;: &#34;Dmitry&#39;s iPhone&#34;, &#34;country&#34;: &#34;RU&#34;}

Keys and values are both strings. Total encoded size SHOULD be kept under 4 KiB per event. |






<a name="sso-audit-v1-AuditEvent-MetadataEntry"></a>

### AuditEvent.MetadataEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="sso-audit-v1-AuditFilters"></a>

### AuditFilters
============================================================================
AuditFilters - filtering options for ListAuditEvents
============================================================================
All filters are AND-combined. Within a repeated field, semantics is OR.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from_time | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Events with occurred_at &gt;= from_time are included. Unset = no lower bound. |
| to_time | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Events with occurred_at &lt; to_time are included. Unset = no upper bound (up to &#34;now&#34;). |
| event_types | [string](#string) | repeated | OR-filter on event_type (exact match). Max 32 entries. |
| actor_type | [ActorType](#sso-audit-v1-ActorType) |  | Filter by actor. |
| actor_id | [string](#string) |  |  |
| actor_ip | [string](#string) |  |  |
| subject_type | [SubjectType](#sso-audit-v1-SubjectType) |  | Filter by subject. |
| subject_id | [string](#string) |  |  |
| app_id | [string](#string) |  | Scope to events with this app_id (matches Subject.app_id). |
| outcomes | [AuditOutcome](#sso-audit-v1-AuditOutcome) | repeated | OR-filter on outcome. |






<a name="sso-audit-v1-GetAuditEventRequest"></a>

### GetAuditEventRequest
============================================================================
GetAuditEventRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event_id | [string](#string) |  |  |






<a name="sso-audit-v1-ListAuditEventsRequest"></a>

### ListAuditEventsRequest
============================================================================
ListAuditEventsRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  |  |
| page_token | [string](#string) |  |  |
| filters | [AuditFilters](#sso-audit-v1-AuditFilters) |  |  |






<a name="sso-audit-v1-ListAuditEventsResponse"></a>

### ListAuditEventsResponse
============================================================================
ListAuditEventsResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| events | [AuditEvent](#sso-audit-v1-AuditEvent) | repeated |  |
| next_page_token | [string](#string) |  |  |
| total_size | [int32](#int32) | optional | Absent for queries over long time ranges (total can be expensive to compute on an append-only log). |






<a name="sso-audit-v1-Subject"></a>

### Subject
============================================================================
Subject - what the action targeted
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [SubjectType](#sso-audit-v1-SubjectType) |  |  |
| id | [string](#string) |  | UUID of the subject. Empty for events that have no single subject (rare: e.g. a listing RPC). |
| app_id | [string](#string) |  | Scoping app context, if any. For role grants this is the role&#39;s app_id; for user-level events (login, password change) it is the app the user logged into; empty for cross-app actions. |





 


<a name="sso-audit-v1-ActorType"></a>

### ActorType
============================================================================
ActorType - who performed the action
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| ACTOR_TYPE_UNSPECIFIED | 0 |  |
| ACTOR_TYPE_USER | 1 | A human user (Actor.id = user_id UUID). |
| ACTOR_TYPE_SERVICE_ACCOUNT | 2 | A service account (Actor.id = service_account_id UUID). |
| ACTOR_TYPE_SYSTEM | 3 | Server-internal actor (background job, cascade delete, system migration). Actor.id is empty; the event_type describes the source. |
| ACTOR_TYPE_ANONYMOUS | 4 | An unauthenticated caller (e.g. failed Login, anonymous ResetPasswordWithRecoveryCode). Actor.id is empty; Actor.ip_address is the primary signal. |



<a name="sso-audit-v1-AuditOutcome"></a>

### AuditOutcome
============================================================================
AuditOutcome - how the action resolved
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| AUDIT_OUTCOME_UNSPECIFIED | 0 |  |
| AUDIT_OUTCOME_SUCCESS | 1 | The action completed as intended. |
| AUDIT_OUTCOME_FAILURE | 2 | The action failed for a non-authorization reason (validation, not-found, conflict, server error). `reason` carries the ErrorReason name. |
| AUDIT_OUTCOME_DENIED | 3 | The action was rejected on authorization grounds (permission denied, role lacking). `reason` carries PERMISSION_DENIED or a domain-specific code. |



<a name="sso-audit-v1-SubjectType"></a>

### SubjectType
============================================================================
SubjectType - what the action targeted
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| SUBJECT_TYPE_UNSPECIFIED | 0 |  |
| SUBJECT_TYPE_USER | 1 |  |
| SUBJECT_TYPE_ROLE | 2 |  |
| SUBJECT_TYPE_APP | 3 |  |
| SUBJECT_TYPE_SESSION | 4 |  |
| SUBJECT_TYPE_ROLE_ASSIGNMENT | 5 |  |
| SUBJECT_TYPE_SERVICE_ACCOUNT | 6 |  |


 

 


<a name="sso-audit-v1-AuditService"></a>

### AuditService
============================================================================
AuditService - Security-relevant event log
============================================================================
Append-only record of security-relevant actions across the SSO surface:
  - authentication events (login success/failure, password change,
    MFA enrollment, recovery-code use)
  - identity lifecycle (user registered, blocked, deleted)
  - RBAC changes (role created/updated/disabled/deleted, role granted/
    revoked)
  - app lifecycle (app created, disabled, deleted)
  - session events (session created / revoked)
  - service-account events (created, rotated, disabled)

Purpose:
  - incident response (&#34;who granted this role, from what IP&#34;)
  - compliance (append-only, tamper-evident event trail)
  - debugging (&#34;why does user X have permission Y&#34;)

Semantics:
  - events are immutable after write; there is NO UpdateAuditEvent
    nor DeleteAuditEvent RPC by design;
  - write path is internal: SSO services write events as a side-effect
    of user-facing RPCs, not via a public API here;
  - read path is this service.

Ordering:
  ListAuditEvents is ordered by occurred_at DESC (newest first) with
  event_id as an implicit tie-breaker. No user-selectable ordering -
  a security log is read chronologically.

Security:
  All RPCs are authenticated; access is role-based.
    AUDIT_READ  - GetAuditEvent, ListAuditEvents

  Deployments SHOULD restrict AUDIT_READ tightly (security-team /
  compliance-team only), because the log may contain sensitive
  metadata (IPs, user agents, subject identifiers).
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetAuditEvent | [GetAuditEventRequest](#sso-audit-v1-GetAuditEventRequest) | [AuditEvent](#sso-audit-v1-AuditEvent) | GetAuditEvent returns a single event by UUID.

Errors: NOT_FOUND - event does not exist PERMISSION_DENIED - caller lacks AUDIT_READ INVALID_ARGUMENT - event_id is not a valid UUID |
| ListAuditEvents | [ListAuditEventsRequest](#sso-audit-v1-ListAuditEventsRequest) | [ListAuditEventsResponse](#sso-audit-v1-ListAuditEventsResponse) | ListAuditEvents returns a paginated chronological slice of the audit log, optionally filtered.

Errors: PERMISSION_DENIED - caller lacks AUDIT_READ INVALID_ARGUMENT - invalid page_size / page_token / filters |

 



<a name="sso_identity_v1_identity-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/identity/v1/identity.proto



<a name="sso-identity-v1-DisableUserRequest"></a>

### DisableUserRequest
============================================================================
Lifecycle-transition requests
============================================================================
DisableUserRequest sets user status to BLOCKED.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | When true, a missing user_id returns OK instead of NOT_FOUND, so retries are safe after partial-success scenarios (AIP-135). |






<a name="sso-identity-v1-EnableUserRequest"></a>

### EnableUserRequest
EnableUserRequest reactivates a BLOCKED user.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | See DisableUserRequest.allow_missing. |






<a name="sso-identity-v1-GetUserRequest"></a>

### GetUserRequest
============================================================================
GetUserRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |






<a name="sso-identity-v1-ListUsersRequest"></a>

### ListUsersRequest
============================================================================
ListUsersRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  | Page size (0-1000). 0 means &#34;server default&#34;. Negative values are rejected with INVALID_ARGUMENT (AIP-158). |
| page_token | [string](#string) |  | Opaque pagination token from previous response. Empty = first page. |
| filters | [UserFilters](#sso-identity-v1-UserFilters) |  | Optional filters. |
| order_by | [ListUsersOrderBy](#sso-identity-v1-ListUsersOrderBy) |  | Typed sort order (AIP-132). UNSPECIFIED selects the server default. Tie-breaker user_id is always appended implicitly. |






<a name="sso-identity-v1-ListUsersResponse"></a>

### ListUsersResponse
============================================================================
ListUsersResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| users | [User](#sso-identity-v1-User) | repeated | Users for current page. |
| next_page_token | [string](#string) |  | Opaque token for next page. Empty if this was the last page. |
| total_size | [int32](#int32) | optional | Total number of users matching the request across all pages (may be approximate).

Absence semantics: the field is `optional` so &#34;not computed&#34; is a distinct state from &#34;zero matches&#34;. Unset =&gt; server did not compute a total (e.g. filter too expensive); Set to 0 =&gt; genuinely no matches. |






<a name="sso-identity-v1-PermanentlyDeleteUserRequest"></a>

### PermanentlyDeleteUserRequest
PermanentlyDeleteUserRequest requires an etag matching the current
User.etag as explicit, concurrency-safe confirmation.

Why etag instead of a boolean force flag:
  - a stale copy of the request body cannot wipe a user who was
    modified in the meantime (the etag will no longer match),
  - the client had to have observed the current state (via Get/List)
    to obtain the etag, so the deletion is always a deliberate act,
  - mismatch surfaces as ABORTED (ERROR_REASON_ETAG_MISMATCH), the
    same signal used by UpdateUser.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| etag | [string](#string) |  | Current User.etag observed by the caller. &#34;*&#34; is NOT accepted here - hard-delete must be a deliberate, non-unconditional act. |






<a name="sso-identity-v1-SoftDeleteUserRequest"></a>

### SoftDeleteUserRequest
SoftDeleteUserRequest marks a user as DELETED (logical deletion).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | See DisableUserRequest.allow_missing. |






<a name="sso-identity-v1-UpdateUserRequest"></a>

### UpdateUserRequest
============================================================================
UpdateUserRequest - FieldMask-based partial update (AIP-134)
============================================================================
Only fields listed in update_mask are applied. A field omitted from the
mask is left unchanged; a field present in the mask with an empty value
clears the field (where permitted).

Valid mask paths (SERVER MUST REJECT any other path with INVALID_ARGUMENT):
  email
  username
  display_name
  avatar_url
  locale
  timezone

Explicitly INVALID mask paths (server MUST reject):
  user_id       (immutable identity)
  status        (lifecycle; use Disable/Enable/Delete RPCs instead)
  etag          (server-managed; use the top-level etag field)
  created_at, updated_at, last_login_at (output-only timestamps)

The `User user` payload MAY carry values for any field (including
immutable ones) but the server MUST IGNORE any field whose path is not
in update_mask. Conversely, populating an otherwise-valid field like
`status` in `user` without also placing &#34;status&#34; in the mask MUST be
a silent no-op, never a hidden write.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | Target user (required). |
| user | [User](#sso-identity-v1-User) |  | New field values. Fields not referenced by update_mask are ignored. |
| update_mask | [google.protobuf.FieldMask](#google-protobuf-FieldMask) |  | Set of field paths to apply from `user`. Must be non-empty. |
| etag | [string](#string) |  | Required optimistic concurrency token. &#34;*&#34; means unconditional update. |






<a name="sso-identity-v1-User"></a>

### User
============================================================================
User - identity record (response type)
============================================================================
Output-only timestamps and etag are set by the server and ignored on input.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | Unique identifier (RFC 4122 UUID). |
| email | [string](#string) |  | User email address. May be empty for soft-deleted records. |
| username | [string](#string) |  | Unique username (1-128 chars). |
| display_name | [string](#string) |  | Display name (non-unique, 1-128 chars). |
| avatar_url | [string](#string) | optional | Avatar image URL (0-2048 chars). Absent if not set; treat missing and empty string as equivalent. |
| status | [UserStatus](#sso-identity-v1-UserStatus) |  | Current lifecycle status. |
| etag | [string](#string) |  | Opaque version token for optimistic concurrency (AIP-154). Send back in UpdateUserRequest.etag to detect concurrent modifications. |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Account creation timestamp (output-only). |
| updated_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Last update timestamp (output-only). |
| last_login_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional | Last successful login timestamp. Absent if user never logged in. |
| locale | [string](#string) |  | BCP 47 language tag (e.g. &#34;en-US&#34;, &#34;ru-RU&#34;). Empty string if not set; server treats missing and empty as &#34;use system default&#34;. Format is validated loosely at the proto layer (length only); strict BCP 47 parsing is the server&#39;s responsibility. |
| timezone | [string](#string) |  | IANA time-zone identifier (e.g. &#34;Europe/Moscow&#34;, &#34;UTC&#34;). Empty string if not set. Format validated loosely here; strict IANA membership check is done server-side. |






<a name="sso-identity-v1-UserFilters"></a>

### UserFilters
============================================================================
UserFilters - filtering options for ListUsers
============================================================================
Semantics:
  - `search` is a case-insensitive fuzzy match across email / username /
    display_name (OR between fields).
  - Repeated fields apply OR within the field and AND across different fields.
  - If `statuses` is empty, USER_STATUS_DELETED is excluded by default.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| search | [string](#string) |  | Free-text search. |
| emails | [string](#string) | repeated |  |
| usernames | [string](#string) | repeated |  |
| display_names | [string](#string) | repeated |  |
| statuses | [UserStatus](#sso-identity-v1-UserStatus) | repeated |  |





 


<a name="sso-identity-v1-ListUsersOrderBy"></a>

### ListUsersOrderBy
============================================================================
ListUsersOrderBy - supported sort orders for ListUsers (AIP-132 typed)
============================================================================
Using an enum over a free-text string gives clients compile-time typing
and prevents typos. A tie-breaker on user_id is appended server-side
regardless of the selected order.

| Name | Number | Description |
| ---- | ------ | ----------- |
| LIST_USERS_ORDER_BY_UNSPECIFIED | 0 | Server default (currently CREATED_AT_DESC). |
| LIST_USERS_ORDER_BY_CREATED_AT_DESC | 1 |  |
| LIST_USERS_ORDER_BY_CREATED_AT_ASC | 2 |  |
| LIST_USERS_ORDER_BY_USER_ID_DESC | 3 |  |
| LIST_USERS_ORDER_BY_USER_ID_ASC | 4 |  |
| LIST_USERS_ORDER_BY_USERNAME_DESC | 5 |  |
| LIST_USERS_ORDER_BY_USERNAME_ASC | 6 |  |



<a name="sso-identity-v1-UserStatus"></a>

### UserStatus
============================================================================
UserStatus - lifecycle state of a user identity
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| USER_STATUS_UNSPECIFIED | 0 |  |
| USER_STATUS_ACTIVE | 1 | User is enabled and can access the system. |
| USER_STATUS_BLOCKED | 2 | User is temporarily disabled (reversible via EnableUser). |
| USER_STATUS_DELETED | 3 | User is logically deleted; excluded from default listings. |


 

 


<a name="sso-identity-v1-IdentityService"></a>

### IdentityService
============================================================================
IdentityService - User Identity Management API
============================================================================
Provides identity directory operations for authentication and authorization.

This service manages user identity records only.
It does NOT handle sessions, tokens, or authentication flows.

Lifecycle:
  ACTIVE   - active user
  BLOCKED  - temporarily disabled (reversible via EnableUser)
  DELETED  - logically deleted (irreversible via standard API)

Security:
  All methods require authentication; access is role-based.
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetUser | [GetUserRequest](#sso-identity-v1-GetUserRequest) | [User](#sso-identity-v1-User) | GetUser returns identity record by user ID.

Errors: NOT_FOUND - user with given user_id does not exist PERMISSION_DENIED - caller lacks USER_READ role INVALID_ARGUMENT - user_id is not a valid UUID |
| ListUsers | [ListUsersRequest](#sso-identity-v1-ListUsersRequest) | [ListUsersResponse](#sso-identity-v1-ListUsersResponse) | ListUsers returns paginated identity records.

By default DELETED users are excluded unless explicitly requested via filters.statuses.

Errors: PERMISSION_DENIED - caller lacks USER_READ_ALL role INVALID_ARGUMENT - invalid page_token / page_size / filters |
| UpdateUser | [UpdateUserRequest](#sso-identity-v1-UpdateUserRequest) | [User](#sso-identity-v1-User) | UpdateUser partially updates an identity record.

The set of fields to update is driven by update_mask (AIP-134). An empty update_mask is rejected with INVALID_ARGUMENT.

Optimistic concurrency: if etag is provided and does not match the server-side value, the request is rejected with ABORTED.

Errors: NOT_FOUND - user does not exist PERMISSION_DENIED - caller lacks USER_WRITE role INVALID_ARGUMENT - empty mask, unknown field in mask, invalid value ABORTED - etag mismatch (concurrent modification) FAILED_PRECONDITION - user is DELETED |
| DisableUser | [DisableUserRequest](#sso-identity-v1-DisableUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | DisableUser sets user status to BLOCKED. Idempotent.

If allow_missing=true, NOT_FOUND is converted to a successful no-op (AIP-135 idempotence).

Errors: NOT_FOUND - user does not exist (suppressed if allow_missing) FAILED_PRECONDITION - user is DELETED PERMISSION_DENIED - caller lacks USER_WRITE role |
| EnableUser | [EnableUserRequest](#sso-identity-v1-EnableUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | EnableUser sets user status to ACTIVE. Idempotent.

If allow_missing=true, NOT_FOUND is converted to a successful no-op.

Errors: NOT_FOUND - user does not exist (suppressed if allow_missing) FAILED_PRECONDITION - user is DELETED (cannot be re-enabled via this API) PERMISSION_DENIED - caller lacks USER_WRITE role |
| SoftDeleteUser | [SoftDeleteUserRequest](#sso-identity-v1-SoftDeleteUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | SoftDeleteUser marks user as DELETED (logical deletion). Idempotent.

User data is retained; the account cannot authenticate and is hidden from default ListUsers results. If allow_missing=true, NOT_FOUND is converted to a successful no-op.

Errors: NOT_FOUND - user does not exist (suppressed if allow_missing) PERMISSION_DENIED - caller lacks USER_DELETE role |
| PermanentlyDeleteUser | [PermanentlyDeleteUserRequest](#sso-identity-v1-PermanentlyDeleteUserRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | PermanentlyDeleteUser removes all user data irreversibly.

Requires an etag matching the current server-side User.etag as an explicit concurrency-safe confirmation (stronger than a boolean force flag: prevents accidental deletion based on a stale read or a copy-pasted request body). Typically invoked only after SoftDeleteUser and only by privileged roles.

Errors: NOT_FOUND - user does not exist FAILED_PRECONDITION - user is not in DELETED status ABORTED - supplied etag does not match current User.etag (ERROR_REASON_ETAG_MISMATCH) PERMISSION_DENIED - caller lacks USER_PURGE role INVALID_ARGUMENT - etag missing or malformed |

 



<a name="sso_auth_v1_auth-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/auth/v1/auth.proto



<a name="sso-auth-v1-AuthTokens"></a>

### AuthTokens
============================================================================
AuthTokens - the credential bundle issued on successful authentication
============================================================================
Returned by every RPC that establishes or rotates a session:
  Login (on single-factor path), CompleteMfaChallenge, Refresh,
  ChangePassword, ResetPasswordWithRecoveryCode, AuthenticateServiceAccount.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| access_token | [string](#string) |  | Short-lived bearer credential. |
| refresh_token | [string](#string) |  | Long-lived rotation token. Send back in RefreshRequest.refresh_token to obtain a new access/refresh pair. |
| subject_id | [string](#string) |  | Subject of the token: for user sessions, the user UUID; for service-account sessions, the service-account UUID. The concrete type is recoverable from ValidateTokenResponse.subject_type. |
| session_id | [string](#string) |  | UUID of the server-side session backing these tokens. Bearer-handle; redacted from debug dumps. |
| access_token_expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Expiration timestamp of access_token. |
| refresh_token_expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Advisory expiration time of current refresh_token. Subject to earlier revocation, password change, admin action, inactivity timeout, or token rotation. |






<a name="sso-auth-v1-ChangePasswordRequest"></a>

### ChangePasswordRequest
============================================================================
ChangePasswordRequest - payload for ChangePassword RPC
============================================================================
The target user is identified by the caller&#39;s access_token in gRPC
metadata; callers can only change their own password.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| old_password | [string](#string) |  | The caller&#39;s current password. Required as a proof-of-identity check independent of the access_token. Same length policy as LoginRequest.password (12-64 chars). |
| new_password | [string](#string) |  | The new password (12-64 chars). Must differ from old_password; server enforces additional complexity rules. Transmitted only over TLS-protected transport. |






<a name="sso-auth-v1-CompleteMfaChallengeRequest"></a>

### CompleteMfaChallengeRequest
============================================================================
CompleteMfaChallengeRequest - second factor
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| challenge_id | [string](#string) |  | The challenge_id from LoginResponse.challenge. |
| method | [MfaMethod](#sso-auth-v1-MfaMethod) |  | Which method the client is completing with. |
| code | [string](#string) |  | Verification code. TOTP: exactly 6 ASCII digits RECOVERY_CODE: &#34;XXXX-XXXX-XXXX&#34; (14 chars, hyphens between groups of 4 alphanumerics; server-side normalization accepts codes without hyphens too). |






<a name="sso-auth-v1-ConfirmTotpEnrollmentRequest"></a>

### ConfirmTotpEnrollmentRequest
============================================================================
ConfirmTotpEnrollmentRequest - activate a pending TOTP enrollment
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | Live 6-digit TOTP code generated from the just-issued secret. |






<a name="sso-auth-v1-DeviceInfo"></a>

### DeviceInfo
============================================================================
DeviceInfo - optional client metadata captured on Login
============================================================================
Helps users identify their sessions in ListSessions. Servers SHOULD
augment user-supplied values with authoritative ones (e.g. IP from the
gRPC peer, user-agent from metadata).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_agent | [string](#string) |  | Raw User-Agent string. Max 512 chars to accommodate modern UAs. |
| ip_address | [string](#string) |  | Client IP address. Server OVERRIDES with the authoritative peer address; client-supplied value is ignored (prevents spoofing). Output-only from the client&#39;s perspective. |
| device_name | [string](#string) |  | Free-form device-name label from the client (e.g. &#34;Dmitry&#39;s iPhone&#34;). Optional; shown to the user in ListSessions UI. |
| country_code | [string](#string) |  | ISO 3166-1 alpha-2 country code derived server-side from ip_address. Output-only. |






<a name="sso-auth-v1-DisableTotpRequest"></a>

### DisableTotpRequest
============================================================================
DisableTotpRequest - tear down TOTP for the caller
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | Proof-of-possession: EITHER a current 6-digit TOTP code OR a one-time recovery code. Required to prevent an attacker with only a stolen access_token from silently stripping MFA. |






<a name="sso-auth-v1-ListSessionsRequest"></a>

### ListSessionsRequest
============================================================================
ListSessionsRequest - paginated list of the caller&#39;s sessions
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  | Page size (0-100). 0 means server default. Capped lower than other List* endpoints because typical users have O(10) sessions, not O(1000). |
| page_token | [string](#string) |  | Opaque pagination token. Empty = first page. |






<a name="sso-auth-v1-ListSessionsResponse"></a>

### ListSessionsResponse
============================================================================
ListSessionsResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sessions | [SessionInfo](#sso-auth-v1-SessionInfo) | repeated |  |
| next_page_token | [string](#string) |  |  |
| total_size | [int32](#int32) | optional |  |






<a name="sso-auth-v1-LoginRequest"></a>

### LoginRequest
============================================================================
LoginRequest - payload for Login RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| app_id | [string](#string) |  |  |
| app_slug | [string](#string) |  |  |
| email | [string](#string) |  |  |
| username | [string](#string) |  |  |
| password | [string](#string) |  | Plaintext password (12-64 chars). Same policy as RegisterRequest. Transmitted only over TLS-protected transport. |
| device | [DeviceInfo](#sso-auth-v1-DeviceInfo) |  | Optional client-supplied device metadata for session attribution. The server MUST override DeviceInfo.ip_address with the peer&#39;s authoritative IP; client-supplied ip_address is ignored. |






<a name="sso-auth-v1-LoginResponse"></a>

### LoginResponse
============================================================================
LoginResponse - either tokens (single-factor) or MFA challenge
============================================================================
Callers MUST check which oneof branch is set:
  result.tokens    -&gt; authentication complete, use tokens
  result.challenge -&gt; MFA required, call CompleteMfaChallenge next


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tokens | [AuthTokens](#sso-auth-v1-AuthTokens) |  |  |
| challenge | [MfaChallenge](#sso-auth-v1-MfaChallenge) |  |  |






<a name="sso-auth-v1-MfaChallenge"></a>

### MfaChallenge
============================================================================
MfaChallenge - issued by Login when the user has MFA enrolled
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| challenge_id | [string](#string) |  | Opaque identifier for the pending partial-authentication state. Single-use; expires at `expires_at` (~5 minutes after Login). Bearer-handle: redacted from debug dumps. |
| available_methods | [MfaMethod](#sso-auth-v1-MfaMethod) | repeated | MFA methods the user has enrolled. Client picks one and passes it to CompleteMfaChallenge. A user with TOTP enabled is guaranteed to see both TOTP and RECOVERY_CODE here (recovery codes are always available as fallback). |
| expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Challenge expiry. After this time the challenge_id is no longer accepted; the client must start a fresh Login. |






<a name="sso-auth-v1-RecoveryCodesResponse"></a>

### RecoveryCodesResponse
============================================================================
RecoveryCodesResponse - one-time recovery codes, shown once
============================================================================
The codes below are displayed to the user exactly once. The server
stores only salted hashes and cannot re-display them; a new batch
fully supersedes the previous batch.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| codes | [string](#string) | repeated | Typically 10 codes in the form &#34;XXXX-XXXX-XXXX&#34; (14 chars). Alphabet is restricted to unambiguous characters to reduce transcription errors (no 0/O, 1/I/l confusion). |
| generated_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | When the batch was generated. Useful for the UI to tell the user &#34;these codes were generated on &lt;date&gt;&#34;. |






<a name="sso-auth-v1-RefreshRequest"></a>

### RefreshRequest
============================================================================
RefreshRequest - payload for Refresh RPC
============================================================================
The target application is encoded inside the refresh_token and resolved
server-side; clients do not pass app_id separately.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| refresh_token | [string](#string) |  | Refresh token previously issued by Login or an earlier Refresh. |






<a name="sso-auth-v1-RegisterRequest"></a>

### RegisterRequest
============================================================================
RegisterRequest - payload for Register RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  | User email address (RFC 5321, max 254 chars). Must be unique. |
| username | [string](#string) |  | Unique username (1-128 chars). |
| display_name | [string](#string) |  | Human-readable display name (1-128 chars, non-unique). |
| password | [string](#string) |  | Plaintext password (12-64 chars). Server enforces additional complexity rules; never logged or echoed back. Transmitted only over TLS-protected transport. |






<a name="sso-auth-v1-ResetPasswordWithRecoveryCodeRequest"></a>

### ResetPasswordWithRecoveryCodeRequest
============================================================================
ResetPasswordWithRecoveryCodeRequest - unauthenticated password reset
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |
| username | [string](#string) |  |  |
| app_id | [string](#string) |  |  |
| app_slug | [string](#string) |  |  |
| recovery_code | [string](#string) |  | One of the user&#39;s unused recovery codes. Consumed on success. Server-side normalization: hyphens are optional, case-insensitive. |
| new_password | [string](#string) |  | The new password. Same policy as Register / ChangePassword. |






<a name="sso-auth-v1-RevokeAllSessionsRequest"></a>

### RevokeAllSessionsRequest
============================================================================
RevokeAllSessionsRequest - payload for RevokeAllSessions
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| except_current | [bool](#bool) |  | When true, keep the session making this call alive (&#34;log out everywhere except here&#34;). When false (default), ALL sessions including the current one are revoked and the caller must Login again. |






<a name="sso-auth-v1-RevokeSessionRequest"></a>

### RevokeSessionRequest
============================================================================
RevokeSessionRequest - payload for RevokeSession RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| session_id | [string](#string) |  | UUID of the session to revoke. Must belong to the calling user (ownership is verified server-side against the caller&#39;s access_token). Bearer-handle: redacted from debug dumps. |






<a name="sso-auth-v1-RevokeTokenRequest"></a>

### RevokeTokenRequest
============================================================================
RevokeTokenRequest - payload for RevokeToken RPC
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| refresh_token | [string](#string) |  | Refresh token to revoke. All access_tokens derived from it stop validating on the next ValidateToken call. |






<a name="sso-auth-v1-ServiceAccountAuthRequest"></a>

### ServiceAccountAuthRequest
============================================================================
ServiceAccountAuthRequest - OAuth2 client_credentials grant
============================================================================
Service-account credentials are issued and managed via
sso.serviceaccount.v1.ServiceAccountService. This RPC exchanges them
for AuthTokens on the user-auth surface.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| client_id | [string](#string) |  | Public identifier of the service account. |
| client_secret | [string](#string) |  | Secret issued alongside the client_id. Shown only once at creation; can be rotated via ServiceAccountService.RotateCredentials. |
| app_id | [string](#string) |  |  |
| app_slug | [string](#string) |  |  |






<a name="sso-auth-v1-SessionInfo"></a>

### SessionInfo
============================================================================
SessionInfo - one session as displayed to the session owner
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| session_id | [string](#string) |  | UUID of the session. Bearer-handle: redacted from debug dumps. |
| app_id | [string](#string) |  | App the session was issued for. |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | When the session was created (last Login or ChangePassword). |
| last_seen_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Last observed activity (any authenticated RPC, any ValidateToken). |
| expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Hard expiry of the session (refresh_token expiry). |
| device | [DeviceInfo](#sso-auth-v1-DeviceInfo) |  | Device metadata captured at Login. Fields may be empty if the client did not supply them and the server could not infer them. |
| is_current | [bool](#bool) |  | True for the session that issued this ListSessions call. The caller&#39;s own session is always returned as part of the list; this flag lets the UI highlight it and disable &#34;revoke&#34; on that row. |






<a name="sso-auth-v1-TotpEnrollmentResponse"></a>

### TotpEnrollmentResponse
============================================================================
TotpEnrollmentResponse - begin TOTP enrollment
============================================================================
The secret is shown ONCE. The client renders otpauth_url as a QR code.
Enrollment is NOT active until ConfirmTotpEnrollment verifies a live code.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| secret_base32 | [string](#string) |  | Base32-encoded TOTP secret (RFC 6238). Typically 26-32 chars for a 128-bit / 160-bit secret. Shown once. |
| otpauth_url | [string](#string) |  | otpauth:// URL encoding issuer, account name, secret, algorithm, digits, and period. Clients render this as a QR code for the user to scan with their TOTP app. Example: otpauth://totp/nergous.ru:alice@example.com?secret=...&amp;issuer=nergous.ru |






<a name="sso-auth-v1-ValidateTokenRequest"></a>

### ValidateTokenRequest
============================================================================
ValidateTokenRequest - payload for ValidateToken RPC
============================================================================
The target application is encoded inside the access_token and resolved
server-side; clients do not pass app_id separately.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| access_token | [string](#string) |  | Access token to introspect. |






<a name="sso-auth-v1-ValidateTokenResponse"></a>

### ValidateTokenResponse
============================================================================
ValidateTokenResponse - metadata of a valid access_token
============================================================================
Only returned when the token is valid; invalid / expired / revoked tokens
surface as UNAUTHENTICATED gRPC errors without a response body.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| subject_id | [string](#string) |  | Subject UUID (user or service account). See subject_type. |
| subject_type | [SubjectType](#sso-auth-v1-SubjectType) |  | What the subject is. |
| session_id | [string](#string) |  | UUID of the server-side session backing this token. Bearer-handle; redacted from debug dumps. |
| expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | Token expiration timestamp. |
| app_id | [string](#string) |  | UUID of the app the token was issued for. Downstream services MUST check this against their own app_id before trusting the token - a token issued for app A is not valid for app B even if the signature verifies. |





 


<a name="sso-auth-v1-MfaMethod"></a>

### MfaMethod
============================================================================
MfaMethod - ways a user can satisfy the second factor
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| MFA_METHOD_UNSPECIFIED | 0 |  |
| MFA_METHOD_TOTP | 1 | 6-digit time-based one-time password (RFC 6238). |
| MFA_METHOD_RECOVERY_CODE | 2 | One-time recovery code from GenerateRecoveryCodes. Consumed on use. |



<a name="sso-auth-v1-SubjectType"></a>

### SubjectType
============================================================================
SubjectType - what kind of identity a token represents
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| SUBJECT_TYPE_UNSPECIFIED | 0 |  |
| SUBJECT_TYPE_USER | 1 |  |
| SUBJECT_TYPE_SERVICE_ACCOUNT | 2 |  |


 

 


<a name="sso-auth-v1-AuthService"></a>

### AuthService
============================================================================
AuthService - Authentication, Sessions, MFA, Recovery, Service Accounts
============================================================================
Handles every credential-handling flow in SSO:
  - global user registration
  - per-app login (with optional MFA step) and session issuance
  - token lifecycle (refresh, validate, revoke)
  - self-service session management (list / revoke-all)
  - password change and recovery-code-based password reset
  - TOTP enrollment / confirmation / disablement
  - service-account authentication (backend-to-backend)

Token model:
  access_token  - short-lived bearer credential (~15 min recommended)
  refresh_token - long-lived rotation token used to obtain new access tokens
  session_id    - server-side session handle, bearer-handle, redacted

Both tokens encode app_id internally; Refresh / ValidateToken resolve the
target app from the token itself - clients do not pass app_id separately.

Token rotation:
  Each Refresh issues a new refresh_token and invalidates the old one
  (RFC 6819 mitigation against refresh-token replay).

Login flow variants:
  Single-factor (MFA not enrolled):
    Login -&gt; LoginResponse{tokens}
  Two-factor (MFA enrolled):
    Login -&gt; LoginResponse{challenge}
    CompleteMfaChallenge(challenge_id, code) -&gt; AuthTokens

Authentication requirements:
  Public (no access_token): Register, Login, CompleteMfaChallenge,
    Refresh, ValidateToken, ResetPasswordWithRecoveryCode,
    AuthenticateServiceAccount
  Authenticated: everything else (access_token via
    `authorization: Bearer &lt;access_token&gt;` gRPC metadata).
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Register | [RegisterRequest](#sso-auth-v1-RegisterRequest) | [.sso.identity.v1.User](#sso-identity-v1-User) | Register creates a new user identity in the global SSO directory and returns it (AIP-133: Create RPCs return the created resource).

Not scoped to any application; access to specific apps is granted separately via AccessService (role grants). Does NOT issue tokens - the client must call Login afterwards.

User-enumeration mitigation: On ALREADY_EXISTS the server MUST NOT disclose which specific field (email vs username) collided. See sso.common.v1.ErrorReason.ERROR_REASON_USER_ALREADY_EXISTS.

Errors: ALREADY_EXISTS - email or username is already taken (opaque) INVALID_ARGUMENT - email / username / display_name / password failed validation |
| Login | [LoginRequest](#sso-auth-v1-LoginRequest) | [LoginResponse](#sso-auth-v1-LoginResponse) | Login authenticates a user against a specific app.

If the user has no MFA enrolled, the response carries `tokens` directly and the login is complete. If MFA is enrolled, the response carries `challenge`; the client MUST then call CompleteMfaChallenge with the challenge_id and an MFA code to obtain tokens.

Errors: UNAUTHENTICATED - invalid credentials NOT_FOUND - app does not exist (by app_id or app_slug) FAILED_PRECONDITION - user is BLOCKED/DELETED or app is DISABLED/MAINTENANCE INVALID_ARGUMENT - app_target / identifier / password failed validation RESOURCE_EXHAUSTED - rate limit hit after repeated INVALID_CREDENTIALS |
| CompleteMfaChallenge | [CompleteMfaChallengeRequest](#sso-auth-v1-CompleteMfaChallengeRequest) | [AuthTokens](#sso-auth-v1-AuthTokens) | CompleteMfaChallenge finalizes a two-factor login. Issues tokens on success. The challenge_id is single-use and short-lived (~5 minutes); after expiry the client must start a fresh Login.

Errors: UNAUTHENTICATED - invalid or expired challenge_id, or wrong code FAILED_PRECONDITION - challenge already consumed INVALID_ARGUMENT - malformed code or unsupported method RESOURCE_EXHAUSTED - too many code-verification attempts for this challenge |
| Logout | [.google.protobuf.Empty](#google-protobuf-Empty) | [.google.protobuf.Empty](#google-protobuf-Empty) | Logout invalidates the current session identified by the caller&#39;s access_token in gRPC metadata. Idempotent.

Errors: UNAUTHENTICATED - missing, malformed, or expired access_token |
| Refresh | [RefreshRequest](#sso-auth-v1-RefreshRequest) | [AuthTokens](#sso-auth-v1-AuthTokens) | Refresh exchanges a refresh_token for a new access/refresh pair. The previous refresh_token is atomically invalidated (rotation).

Errors: UNAUTHENTICATED - refresh_token invalid, revoked, or expired INVALID_ARGUMENT - refresh_token failed validation |
| ValidateToken | [ValidateTokenRequest](#sso-auth-v1-ValidateTokenRequest) | [ValidateTokenResponse](#sso-auth-v1-ValidateTokenResponse) | ValidateToken introspects an access_token and returns its metadata. On invalid / expired / revoked token, returns UNAUTHENTICATED - the response is only populated for tokens that are currently valid.

Errors: UNAUTHENTICATED - access_token invalid, revoked, or expired INVALID_ARGUMENT - access_token failed validation |
| RevokeSession | [RevokeSessionRequest](#sso-auth-v1-RevokeSessionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | RevokeSession terminates a session owned by the caller. All tokens associated with the session are invalidated. Idempotent.

Errors: UNAUTHENTICATED - missing, malformed, or expired access_token PERMISSION_DENIED - session_id does not belong to the caller NOT_FOUND - session does not exist INVALID_ARGUMENT - session_id is not a valid UUID |
| RevokeToken | [RevokeTokenRequest](#sso-auth-v1-RevokeTokenRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | RevokeToken invalidates a refresh_token chain. All currently outstanding access_tokens derived from it stop validating on the next ValidateToken call. Idempotent.

Errors: UNAUTHENTICATED - missing, malformed, or expired access_token INVALID_ARGUMENT - refresh_token failed validation |
| ListSessions | [ListSessionsRequest](#sso-auth-v1-ListSessionsRequest) | [ListSessionsResponse](#sso-auth-v1-ListSessionsResponse) | ListSessions returns the caller&#39;s currently active sessions, across all apps. Lets the user see which devices/browsers are logged in.

Errors: UNAUTHENTICATED - missing/invalid access_token |
| RevokeAllSessions | [RevokeAllSessionsRequest](#sso-auth-v1-RevokeAllSessionsRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | RevokeAllSessions terminates every session owned by the caller. By default the current session (the one that made this call) is also revoked - i.e. &#34;log out everywhere&#34;. Set except_current=true for &#34;log out everywhere except here&#34;.

Errors: UNAUTHENTICATED - missing/invalid access_token |
| ChangePassword | [ChangePasswordRequest](#sso-auth-v1-ChangePasswordRequest) | [AuthTokens](#sso-auth-v1-AuthTokens) | ChangePassword replaces the caller&#39;s password. The current password must be supplied as proof of identity - this guards against account takeover via a stolen session/token.

Token rotation: on success, ALL of the caller&#39;s sessions are revoked (including the one that made this call), and a fresh (access_token, refresh_token) pair is issued inline in the response. The client MUST replace its tokens.

Rate-limiting (REQUIRED server-side): see ERROR_REASON_PASSWORD_MISMATCH.

Errors: UNAUTHENTICATED - access_token missing/invalid (INVALID_TOKEN) OR old_password did not match (PASSWORD_MISMATCH) RESOURCE_EXHAUSTED - rate limit hit after repeated PASSWORD_MISMATCH INVALID_ARGUMENT - new_password failed policy validation OR new_password equals old_password FAILED_PRECONDITION - user is BLOCKED or DELETED |
| ResetPasswordWithRecoveryCode | [ResetPasswordWithRecoveryCodeRequest](#sso-auth-v1-ResetPasswordWithRecoveryCodeRequest) | [AuthTokens](#sso-auth-v1-AuthTokens) | ResetPasswordWithRecoveryCode lets a user who forgot their password set a new one using one of the recovery codes previously issued by GenerateRecoveryCodes. PUBLIC endpoint (no access_token required).

On success: - the used recovery code is consumed (single-use); - ALL of the user&#39;s existing sessions are revoked; - a fresh session is issued inline (same shape as Login).

Rate-limiting (REQUIRED server-side): this endpoint accepts unauthenticated (identifier, code) pairs and is a prime target for brute-force. Servers MUST enforce aggressive per-identifier and per-IP throttling with exponential backoff.

Errors: UNAUTHENTICATED - identifier/code combination does not match NOT_FOUND - identifier does not resolve to a user FAILED_PRECONDITION - user is BLOCKED or DELETED RESOURCE_EXHAUSTED - rate limit hit INVALID_ARGUMENT - new_password failed policy validation |
| GenerateRecoveryCodes | [.google.protobuf.Empty](#google-protobuf-Empty) | [RecoveryCodesResponse](#sso-auth-v1-RecoveryCodesResponse) | GenerateRecoveryCodes issues a fresh batch of 10 one-time recovery codes for the caller. ANY previously issued codes are invalidated atomically. Codes are SHOWN ONLY ONCE in the response; the server retains only salted hashes and cannot re-display them.

Recovery codes serve a dual purpose: 1. Offline password reset (ResetPasswordWithRecoveryCode). 2. MFA bypass (CompleteMfaChallenge with method=RECOVERY_CODE).

Errors: UNAUTHENTICATED - missing/invalid access_token FAILED_PRECONDITION - user is BLOCKED or DELETED |
| EnrollTotp | [.google.protobuf.Empty](#google-protobuf-Empty) | [TotpEnrollmentResponse](#sso-auth-v1-TotpEnrollmentResponse) | EnrollTotp begins TOTP enrollment. Generates a fresh secret and returns it (plus an otpauth:// URL the client renders as a QR code). TOTP is NOT yet active after this call - the client MUST follow up with ConfirmTotpEnrollment to prove the secret was correctly recorded in the authenticator app.

If the user has an unconfirmed enrollment from a previous call, it is atomically replaced.

Errors: UNAUTHENTICATED - missing/invalid access_token FAILED_PRECONDITION - TOTP already enrolled and active (disable first) |
| ConfirmTotpEnrollment | [ConfirmTotpEnrollmentRequest](#sso-auth-v1-ConfirmTotpEnrollmentRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | ConfirmTotpEnrollment activates a pending TOTP enrollment by verifying a live 6-digit code generated from the secret. After success, subsequent Logins will require MFA.

Errors: UNAUTHENTICATED - missing/invalid access_token FAILED_PRECONDITION - no pending enrollment INVALID_ARGUMENT - code is not 6 digits PERMISSION_DENIED - code did not match (treat as ERROR_REASON_MFA_CODE_INVALID) |
| DisableTotp | [DisableTotpRequest](#sso-auth-v1-DisableTotpRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | DisableTotp removes TOTP from the caller&#39;s account. Requires proof-of-possession: a valid TOTP code OR a valid recovery code. This prevents an attacker holding only a stolen access_token from silently stripping MFA.

Errors: UNAUTHENTICATED - missing/invalid access_token FAILED_PRECONDITION - TOTP is not enrolled PERMISSION_DENIED - proof code did not match (ERROR_REASON_MFA_CODE_INVALID) INVALID_ARGUMENT - proof code is neither 6 digits nor a recovery code |
| AuthenticateServiceAccount | [ServiceAccountAuthRequest](#sso-auth-v1-ServiceAccountAuthRequest) | [AuthTokens](#sso-auth-v1-AuthTokens) | AuthenticateServiceAccount exchanges a (client_id, client_secret) pair for AuthTokens, analogous to OAuth2 client_credentials grant. Service accounts are managed in sso.serviceaccount.v1.

The issued access_token has subject = service_account:{id} instead of user:{id}; downstream authorization (roles, CheckPermission) works identically.

Errors: UNAUTHENTICATED - invalid client_id / client_secret combo FAILED_PRECONDITION - service account is DISABLED, or target app is DISABLED/MAINTENANCE NOT_FOUND - target app does not exist INVALID_ARGUMENT - app_target / credentials failed validation RESOURCE_EXHAUSTED - rate limit hit |

 



<a name="sso_common_v1_errors-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/common/v1/errors.proto


 


<a name="sso-common-v1-ErrorReason"></a>

### ErrorReason
============================================================================
ErrorReason - machine-readable cause of a failed RPC
============================================================================
Stability contract:
  Once assigned, a (name, number) pair MUST NOT be reused for a different
  semantic meaning. Removed values stay `reserved` to prevent silent
  repurposing.

Scope:
  This enum is shared across every sso.*.v1 service. It MAY ONLY be
  extended additively within sso.common.v1 - new values are appended to
  an existing block, or a fresh block is opened above the headroom of
  an existing one. Renumbering, repurposing, or removing a value is a
  WIRE-BREAKING change across the whole surface.

  For buf breaking: sso/common/v1/errors.proto is the single file whose
  modification can affect every other package. `breaking: use: PACKAGE`
  at the buf.yaml level enforces this as a tripwire.

Numbering convention:
  Values are grouped by domain. Each block leaves headroom for future
  reasons:
    1-19    Authentication
    20-39   Validation / concurrency
    40-59   User identity
    60-79   Apps
    80-99   Roles
    100-119 Authorization
    120-139 MFA
    140-159 Recovery codes
    160-179 Service accounts

The comment on each value lists the RPCs that emit it and the gRPC
Status code it maps to.

| Name | Number | Description |
| ---- | ------ | ----------- |
| ERROR_REASON_UNSPECIFIED | 0 | Default. MUST NOT be used explicitly - indicates a server bug (reason was never set). |
| ERROR_REASON_INVALID_CREDENTIALS | 1 | Login credentials did not match any known user. Generic on purpose - the server does not disclose whether email or password was wrong. Emitted by: AuthService.Login. gRPC Status: UNAUTHENTICATED. |
| ERROR_REASON_INVALID_TOKEN | 2 | The supplied token is expired, malformed, revoked, or otherwise invalid. Generic on purpose (same security rationale as above). Emitted by: AuthService.Logout, Refresh, ValidateToken, RevokeSession, RevokeToken; and any RPC requiring an access_token in metadata. gRPC Status: UNAUTHENTICATED. |
| ERROR_REASON_SESSION_NOT_FOUND | 3 | Requested session does not exist. Emitted by: AuthService.RevokeSession. gRPC Status: NOT_FOUND. |
| ERROR_REASON_SESSION_NOT_OWNED | 4 | Session exists but belongs to a different user than the caller. Emitted by: AuthService.RevokeSession. gRPC Status: PERMISSION_DENIED. |
| ERROR_REASON_PASSWORD_MISMATCH | 5 | The old_password supplied to ChangePassword did not match the caller&#39;s current password. Distinct from INVALID_TOKEN: the access_token itself is valid, but the proof-of-identity check failed.

Rate-limiting (REQUIRED on the server): A caller with a valid access_token can otherwise probe passwords for their own account. Servers MUST enforce a per-user exponential backoff on repeated PASSWORD_MISMATCH results (e.g. 5 failures in 15 minutes -&gt; temporary ChangePassword lockout) and SHOULD emit a security-audit event on each mismatch.

Emitted by: AuthService.ChangePassword. gRPC Status: UNAUTHENTICATED. |
| ERROR_REASON_VALIDATION_FAILED | 20 | One or more request fields failed validation. The accompanying google.rpc.BadRequest enumerates the offending fields. Emitted by: every RPC with field validators. gRPC Status: INVALID_ARGUMENT. |
| ERROR_REASON_ETAG_MISMATCH | 21 | Optimistic-concurrency check failed: the supplied etag does not match the current server-side value (concurrent modification), or a destructive RPC (PermanentlyDelete*) was issued with a stale or mismatched etag. Emitted by: UpdateUser, UpdateApp, UpdateRole, PermanentlyDeleteUser, PermanentlyDeleteApp, PermanentlyDeleteRole. gRPC Status: ABORTED. |
| ERROR_REASON_USER_ALREADY_EXISTS | 40 | A user with the supplied email or username already exists.

User-enumeration mitigation (REQUIRED on the server): The server MUST NOT reveal which specific field collided. In particular: - DO NOT attach a google.rpc.BadRequest enumerating the offending field (email vs username). - DO NOT populate ErrorInfo.metadata with the colliding value. - The status message SHOULD be a fixed generic string (e.g. &#34;registration failed&#34;), identical to the message used for benign validation rejections where practical. The reason code itself is machine-readable and leaks only that *some* uniqueness constraint tripped - which is the minimum a well-behaved client still needs to recover (retry with different credentials vs. fix a format error).

 Deployments with a hard no-enumeration requirement (public self-registration) SHOULD additionally consider returning OK unconditionally and driving verification through an out-of-band email confirmation step.

Emitted by: AuthService.Register. gRPC Status: ALREADY_EXISTS. |
| ERROR_REASON_USER_NOT_FOUND | 41 | No user matches the requested id. Emitted by: IdentityService.*, AccessService.*, AuthService.* (when resolving a user by id). gRPC Status: NOT_FOUND. |
| ERROR_REASON_USER_BLOCKED | 42 | Target user is in BLOCKED status and cannot perform the requested operation (e.g. Login, receive a role grant). Emitted by: AuthService.Login, AccessService.GrantRoleToUser, AccessService.BulkGrantRoles. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_USER_DELETED | 43 | Target user is in DELETED status (soft-deleted). Most write operations on a deleted user are rejected. Emitted by: IdentityService.UpdateUser / EnableUser / DisableUser, AuthService.Login, AccessService.GrantRoleToUser. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_APP_NOT_FOUND | 60 | No app matches the requested id. Emitted by: AppService.*, RolesService.*, AccessService.*, AuthService.Login. gRPC Status: NOT_FOUND. |
| ERROR_REASON_APP_ALREADY_EXISTS | 61 | An app with the supplied name or slug already exists. Emitted by: AppService.CreateApp, AppService.UpdateApp (rename). gRPC Status: ALREADY_EXISTS. |
| ERROR_REASON_APP_DISABLED | 62 | Target app is DISABLED; login and runtime operations are rejected. Emitted by: AuthService.Login. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_APP_IN_MAINTENANCE | 63 | Target app is in MAINTENANCE mode; user-facing operations are temporarily rejected. Emitted by: AuthService.Login. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_ROLE_NOT_FOUND | 80 | No role matches the requested id. Emitted by: RolesService.*, AccessService.*. gRPC Status: NOT_FOUND. |
| ERROR_REASON_ROLE_ALREADY_EXISTS | 81 | A role with the supplied name already exists within the target app (role names are unique per app, case-sensitive). Emitted by: RolesService.CreateRole, RolesService.UpdateRole (rename). gRPC Status: ALREADY_EXISTS. |
| ERROR_REASON_ROLE_DISABLED | 82 | Target role is DISABLED. Role assignments on a disabled role are preserved but new grants are rejected. Emitted by: AccessService.GrantRoleToUser, AccessService.BulkGrantRoles. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_ROLE_NOT_IN_APP | 83 | One or more role_ids in a bulk request do not belong to the supplied app_id. Bulk operations refuse cross-app role sets as a safety guard. Emitted by: AccessService.BulkGrantRoles, AccessService.BulkRemoveRoles. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_ROLE_HAS_ASSIGNMENTS | 84 | Role has active assignments and force=true was not set on the delete request. Emitted by: RolesService.PermanentlyDeleteRole. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_PERMISSION_DENIED | 100 | Caller is authenticated but not authorized for the requested operation. The accompanying ErrorInfo.metadata MAY include a `required_permission` key to help clients explain the denial. Emitted by: any mutating or privileged RPC. gRPC Status: PERMISSION_DENIED. |
| ERROR_REASON_MFA_CODE_INVALID | 120 | Supplied MFA code (TOTP digits or recovery code) did not match. Intentionally generic - does NOT distinguish between &#34;wrong code&#34; and &#34;code for wrong method&#34; to limit guess-and-check leakage. Emitted by: AuthService.CompleteMfaChallenge, AuthService.ConfirmTotpEnrollment, AuthService.DisableTotp. gRPC Status: UNAUTHENTICATED (CompleteMfaChallenge) or PERMISSION_DENIED (Confirm/Disable Totp, where the access_token itself is valid but the proof-of-possession failed). |
| ERROR_REASON_MFA_NOT_ENROLLED | 121 | MFA is not enrolled for the user, but an operation required it (DisableTotp, or a deployment policy requiring MFA before sensitive action). Emitted by: AuthService.DisableTotp. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_MFA_ALREADY_ENROLLED | 122 | MFA is already enrolled and a client tried to enroll again without disabling first. Emitted by: AuthService.EnrollTotp. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_MFA_CHALLENGE_EXPIRED | 123 | The MFA challenge_id passed to CompleteMfaChallenge is expired (TTL exceeded) or unknown (never issued / server-restarted). Emitted by: AuthService.CompleteMfaChallenge. gRPC Status: UNAUTHENTICATED. |
| ERROR_REASON_MFA_CHALLENGE_CONSUMED | 124 | The MFA challenge_id has already been consumed or exceeded its max-attempts budget. Emitted by: AuthService.CompleteMfaChallenge. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_RECOVERY_CODE_INVALID | 140 | Recovery code supplied to ResetPasswordWithRecoveryCode or CompleteMfaChallenge did not match any outstanding code for the target user. Intentionally generic - does NOT distinguish &#34;wrong code&#34; from &#34;code was already used&#34;. Emitted by: AuthService.ResetPasswordWithRecoveryCode, AuthService.CompleteMfaChallenge (method=RECOVERY_CODE). gRPC Status: UNAUTHENTICATED. |
| ERROR_REASON_SERVICE_ACCOUNT_NOT_FOUND | 160 | No service account matches the requested id. Emitted by: ServiceAccountService.*, AuthService.AuthenticateServiceAccount. gRPC Status: NOT_FOUND. |
| ERROR_REASON_SERVICE_ACCOUNT_ALREADY_EXISTS | 161 | A service account with the supplied name already exists. Emitted by: ServiceAccountService.CreateServiceAccount, ServiceAccountService.UpdateServiceAccount (rename). gRPC Status: ALREADY_EXISTS. |
| ERROR_REASON_SERVICE_ACCOUNT_DISABLED | 162 | Service account is DISABLED; authentication is rejected. Emitted by: AuthService.AuthenticateServiceAccount. gRPC Status: FAILED_PRECONDITION. |
| ERROR_REASON_INVALID_CLIENT_CREDENTIALS | 163 | (client_id, client_secret) pair does not match a known service account. Intentionally generic (same security rationale as INVALID_CREDENTIALS). Emitted by: AuthService.AuthenticateServiceAccount. gRPC Status: UNAUTHENTICATED. |


 

 

 



<a name="sso_serviceaccount_v1_serviceaccount-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sso/serviceaccount/v1/serviceaccount.proto



<a name="sso-serviceaccount-v1-CreateServiceAccountRequest"></a>

### CreateServiceAccountRequest
============================================================================
CreateServiceAccountRequest - AIP-133 create
============================================================================
Shape: the resource to create (`service_account`). Server-managed
fields (service_account_id, client_id, status, etag, timestamps,
last_authenticated_at) are ignored if populated in the payload.

Fields the client MUST populate in `service_account`:
  name
Fields the client MAY populate:
  description


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account | [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount) |  |  |






<a name="sso-serviceaccount-v1-CreateServiceAccountResponse"></a>

### CreateServiceAccountResponse
============================================================================
CreateServiceAccountResponse - includes the one-time client_secret
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| credentials | [ServiceAccountCredentials](#sso-serviceaccount-v1-ServiceAccountCredentials) |  |  |






<a name="sso-serviceaccount-v1-DisableServiceAccountRequest"></a>

### DisableServiceAccountRequest
============================================================================
DisableServiceAccountRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | When true, missing service_account_id returns OK instead of NOT_FOUND (AIP-135). |






<a name="sso-serviceaccount-v1-EnableServiceAccountRequest"></a>

### EnableServiceAccountRequest
============================================================================
EnableServiceAccountRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  |  |
| allow_missing | [bool](#bool) |  | See DisableServiceAccountRequest.allow_missing. |






<a name="sso-serviceaccount-v1-GetServiceAccountRequest"></a>

### GetServiceAccountRequest
============================================================================
GetServiceAccountRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  |  |






<a name="sso-serviceaccount-v1-ListServiceAccountsRequest"></a>

### ListServiceAccountsRequest
============================================================================
ListServiceAccountsRequest
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  |  |
| page_token | [string](#string) |  |  |
| filters | [ServiceAccountFilters](#sso-serviceaccount-v1-ServiceAccountFilters) |  |  |
| order_by | [ListServiceAccountsOrderBy](#sso-serviceaccount-v1-ListServiceAccountsOrderBy) |  | Typed sort order (AIP-132). UNSPECIFIED selects the server default. |






<a name="sso-serviceaccount-v1-ListServiceAccountsResponse"></a>

### ListServiceAccountsResponse
============================================================================
ListServiceAccountsResponse
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_accounts | [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount) | repeated |  |
| next_page_token | [string](#string) |  |  |
| total_size | [int32](#int32) | optional |  |






<a name="sso-serviceaccount-v1-PermanentlyDeleteServiceAccountRequest"></a>

### PermanentlyDeleteServiceAccountRequest
============================================================================
PermanentlyDeleteServiceAccountRequest
============================================================================
Requires an etag matching the current ServiceAccount.etag as explicit
confirmation. Cascade is implicit: all role assignments for this
account in sso.access.v1.AccessService are removed atomically.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  |  |
| etag | [string](#string) |  | Current ServiceAccount.etag observed by the caller. &#34;*&#34; is NOT accepted - hard-delete must be a deliberate, non-unconditional act. |






<a name="sso-serviceaccount-v1-RotateCredentialsRequest"></a>

### RotateCredentialsRequest
============================================================================
RotateCredentialsRequest - issue a new client_secret
============================================================================
The old secret is invalidated atomically with issuance of the new
one. All running services authenticating with the old secret will
start getting UNAUTHENTICATED on their next call and must be updated.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  |  |
| etag | [string](#string) |  | Current ServiceAccount.etag observed by the caller. Guards against racing rotations (&#34;who rotated last&#34; confusion). |






<a name="sso-serviceaccount-v1-ServiceAccount"></a>

### ServiceAccount
============================================================================
ServiceAccount - canonical service-account record (response type)
============================================================================
Field-level constraints are enforced on input (CreateServiceAccount,
UpdateServiceAccount).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  | UUID of the service account. |
| client_id | [string](#string) |  | Public client identifier used in AuthenticateServiceAccount. Generated by the server at creation; immutable; shown in audit logs. |
| name | [string](#string) |  | Human-readable name (1-128 chars, unique across all service accounts). |
| description | [string](#string) |  | Optional free-form description (0-1024 chars). |
| status | [ServiceAccountStatus](#sso-serviceaccount-v1-ServiceAccountStatus) |  | Lifecycle status. Server-assigned on create (always ACTIVE); on update this path is invalid - use Enable/Disable RPCs. |
| etag | [string](#string) |  | Optimistic concurrency token (AIP-154). |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| updated_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| last_authenticated_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) | optional | Last successful AuthenticateServiceAccount call. Absent if the account has never been used. |






<a name="sso-serviceaccount-v1-ServiceAccountCredentials"></a>

### ServiceAccountCredentials
============================================================================
ServiceAccountCredentials - issued once at creation / rotation
============================================================================
client_secret is shown exactly ONCE and cannot be re-retrieved. The
consumer MUST persist it immediately (env var, secret manager, etc.).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount) |  | The fully-populated service-account record after the operation. |
| client_secret | [string](#string) |  | Secret; displayed once. Rotate via RotateCredentials to revoke. |
| issued_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | When this credential pair was issued. |






<a name="sso-serviceaccount-v1-ServiceAccountFilters"></a>

### ServiceAccountFilters
============================================================================
ServiceAccountFilters - filtering options for ListServiceAccounts
============================================================================


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| search | [string](#string) |  | Case-insensitive substring search over name and description. |
| statuses | [ServiceAccountStatus](#sso-serviceaccount-v1-ServiceAccountStatus) | repeated | Filter by lifecycle status (OR logic). Empty list = no filter. |






<a name="sso-serviceaccount-v1-UpdateServiceAccountRequest"></a>

### UpdateServiceAccountRequest
============================================================================
UpdateServiceAccountRequest - FieldMask-based partial update (AIP-134)
============================================================================
Valid mask paths (SERVER MUST REJECT any other path with INVALID_ARGUMENT):
  name
  description

Explicitly INVALID mask paths:
  service_account_id, client_id (immutable identity / credential)
  status                         (use Enable/Disable RPCs)
  etag                           (server-managed; top-level etag field)
  created_at, updated_at, last_authenticated_at (output-only)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| service_account_id | [string](#string) |  |  |
| service_account | [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount) |  |  |
| update_mask | [google.protobuf.FieldMask](#google-protobuf-FieldMask) |  |  |
| etag | [string](#string) |  |  |





 


<a name="sso-serviceaccount-v1-ListServiceAccountsOrderBy"></a>

### ListServiceAccountsOrderBy
============================================================================
ListServiceAccountsOrderBy - supported sort orders (AIP-132 typed)
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_UNSPECIFIED | 0 |  |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_CREATED_AT_DESC | 1 |  |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_CREATED_AT_ASC | 2 |  |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_NAME_DESC | 3 |  |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_NAME_ASC | 4 |  |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_LAST_AUTHENTICATED_AT_DESC | 5 |  |
| LIST_SERVICE_ACCOUNTS_ORDER_BY_LAST_AUTHENTICATED_AT_ASC | 6 |  |



<a name="sso-serviceaccount-v1-ServiceAccountStatus"></a>

### ServiceAccountStatus
============================================================================
ServiceAccountStatus
============================================================================

| Name | Number | Description |
| ---- | ------ | ----------- |
| SERVICE_ACCOUNT_STATUS_UNSPECIFIED | 0 |  |
| SERVICE_ACCOUNT_STATUS_ACTIVE | 1 | Can authenticate and hold role assignments. |
| SERVICE_ACCOUNT_STATUS_DISABLED | 2 | Cannot authenticate; role assignments preserved. Reversible via EnableServiceAccount. |


 

 


<a name="sso-serviceaccount-v1-ServiceAccountService"></a>

### ServiceAccountService
============================================================================
ServiceAccountService - Backend-to-backend identities
============================================================================
A ServiceAccount represents a non-human caller (background worker,
cron job, another backend microservice) that needs to authenticate
to SSO and hold roles, without any of the user-facing machinery
(no password, no MFA, no recovery codes, no session-owner UX).

Credential model:
  client_id       - public identifier (shown in audit logs, config)
  client_secret   - high-entropy secret, shown ONLY at creation or
                    rotation; server stores a hash

Authentication:
  sso.auth.v1.AuthService.AuthenticateServiceAccount exchanges
  (client_id, client_secret) for AuthTokens. The issued access_token
  has subject_type = SERVICE_ACCOUNT; CheckPermission treats the
  service_account_id exactly like a user_id for role-assignment
  purposes (assignments live in sso.access.v1.AccessService).

Lifecycle:
  ACTIVE   - enabled, can authenticate
  DISABLED - cannot authenticate (AuthenticateServiceAccount fails
             with FAILED_PRECONDITION); role assignments preserved
  (deleted) - PermanentlyDeleteServiceAccount removes everything;
              cascade to role assignments is implicit

Security notes:
  - client_secret is returned exactly twice in the API lifetime:
    CreateServiceAccount and RotateCredentials. Both responses are
    debug_redact. Callers are responsible for persisting the secret
    out-of-band (env var, secret manager, etc.).
  - No &#34;self-service&#34; endpoints: creating/rotating service accounts
    is a privileged administrative operation, audited by the caller&#39;s
    user_id (AuditEvent.actor).

Security:
  All RPCs are authenticated; access is role-based.
    SA_READ   - GetServiceAccount, ListServiceAccounts
    SA_WRITE  - CreateServiceAccount, UpdateServiceAccount,
                Enable/Disable, RotateCredentials
    SA_DELETE - PermanentlyDeleteServiceAccount
============================================================================

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetServiceAccount | [GetServiceAccountRequest](#sso-serviceaccount-v1-GetServiceAccountRequest) | [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount) | GetServiceAccount returns a service account by UUID.

Errors: NOT_FOUND - service account does not exist PERMISSION_DENIED - caller lacks SA_READ INVALID_ARGUMENT - service_account_id is not a valid UUID |
| ListServiceAccounts | [ListServiceAccountsRequest](#sso-serviceaccount-v1-ListServiceAccountsRequest) | [ListServiceAccountsResponse](#sso-serviceaccount-v1-ListServiceAccountsResponse) | ListServiceAccounts returns a paginated list of service accounts.

Errors: PERMISSION_DENIED - caller lacks SA_READ INVALID_ARGUMENT - invalid page_size / page_token / filters |
| CreateServiceAccount | [CreateServiceAccountRequest](#sso-serviceaccount-v1-CreateServiceAccountRequest) | [CreateServiceAccountResponse](#sso-serviceaccount-v1-CreateServiceAccountResponse) | CreateServiceAccount provisions a new service account and issues the initial credentials. The client_secret is returned exactly ONCE in the response - the server stores only a hash.

Errors: ALREADY_EXISTS - a service account with this name already exists PERMISSION_DENIED - caller lacks SA_WRITE INVALID_ARGUMENT - name / description failed validation |
| UpdateServiceAccount | [UpdateServiceAccountRequest](#sso-serviceaccount-v1-UpdateServiceAccountRequest) | [ServiceAccount](#sso-serviceaccount-v1-ServiceAccount) | UpdateServiceAccount partially updates a service account. Uses FieldMask (AIP-134) and etag (AIP-154).

Valid mask paths: name, description.

Errors: NOT_FOUND - service account does not exist ABORTED - etag mismatch (ERROR_REASON_ETAG_MISMATCH) ALREADY_EXISTS - rename collides with an existing account PERMISSION_DENIED - caller lacks SA_WRITE INVALID_ARGUMENT - empty mask, unknown mask path, invalid value |
| RotateCredentials | [RotateCredentialsRequest](#sso-serviceaccount-v1-RotateCredentialsRequest) | [ServiceAccountCredentials](#sso-serviceaccount-v1-ServiceAccountCredentials) | RotateCredentials issues a fresh client_secret for an existing service account and invalidates the previous one. The new secret is returned ONCE; all services using the old secret must be updated to use the new one.

Requires an etag matching the current ServiceAccount.etag (guards against racing rotation).

Errors: NOT_FOUND - service account does not exist ABORTED - etag mismatch (ERROR_REASON_ETAG_MISMATCH) PERMISSION_DENIED - caller lacks SA_WRITE INVALID_ARGUMENT - service_account_id is not a valid UUID, or etag missing/malformed |
| DisableServiceAccount | [DisableServiceAccountRequest](#sso-serviceaccount-v1-DisableServiceAccountRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | DisableServiceAccount marks the account as DISABLED. Idempotent. AuthenticateServiceAccount for disabled accounts fails with FAILED_PRECONDITION; existing role assignments are preserved so the account can be re-enabled later.

If allow_missing=true, NOT_FOUND is converted to a no-op.

Errors: NOT_FOUND - service account does not exist (unless allow_missing) PERMISSION_DENIED - caller lacks SA_WRITE |
| EnableServiceAccount | [EnableServiceAccountRequest](#sso-serviceaccount-v1-EnableServiceAccountRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | EnableServiceAccount transitions the account back to ACTIVE. Idempotent. See DisableServiceAccountRequest.allow_missing.

Errors: NOT_FOUND - service account does not exist (unless allow_missing) PERMISSION_DENIED - caller lacks SA_WRITE |
| PermanentlyDeleteServiceAccount | [PermanentlyDeleteServiceAccountRequest](#sso-serviceaccount-v1-PermanentlyDeleteServiceAccountRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) | PermanentlyDeleteServiceAccount removes the service account permanently. Requires an etag matching the current server value as explicit confirmation. Cascade is implicit: all role assignments for this service account are removed atomically.

Errors: NOT_FOUND - service account does not exist ABORTED - etag mismatch (ERROR_REASON_ETAG_MISMATCH) PERMISSION_DENIED - caller lacks SA_DELETE INVALID_ARGUMENT - etag missing, malformed, or &#34;*&#34; |

 



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |

