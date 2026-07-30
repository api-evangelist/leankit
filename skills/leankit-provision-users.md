---
name: leankit-provision-users
description: Provision, search, update, and deactivate Planview AgilePlace (LeanKit) users through the SCIM 1.1 User Provisioning API.
api: leankit:user-provisioning-api
generated: '2026-07-19'
method: generated
source: openapi/leankit-user-provisioning-api-openapi.yml
operations:
  - scimGetServiceProviderConfigs
  - scimSearchUsers
  - scimCreateUser
  - scimGetUser
  - scimReplaceUser
  - scimPatchUser
  - scimDeleteUser
---

# Provision AgilePlace users over SCIM 1.1

Base URL is `https://{account}.leankit.com/io/scim/v1`. **Only account administrators may call this
API.** Authenticate with `Authorization: Basic <base64 email:password>`, or exchange those credentials
once at `POST https://{account}.leankit.com/io/auth/token` for a Bearer token.

## Steps

1. **Check what the service supports** with `GET /ServiceProviderConfigs`. AgilePlace reports
   `filter.supported: true` with `maxResults: 200` and `sort.supported: true`, but
   `patch.supported: false`, `bulk.supported: false`, `changePassword.supported: false`, and
   `etag.supported: false`. Plan around those limits before writing the integration.
2. **Look before you create.** Search with `GET /Users` and a SCIM filter to see whether the person
   already exists. Never create first and reconcile later.
3. **Create** with `POST /Users`, carrying both the core schema and the LeanKit extension:
   `urn:scim:schemas:extension:leankit:user:1.0` with `administrator`, `boardCreator`, and `dateFormat`
   (`mm/dd/yyyy`, `dd/mm/yyyy`, or `yyyy/mm/dd`). `licenseType` is reserved for future use and
   `lastAccess` is read-only.
4. **Read one user** with `GET /Users/{id}`.
5. **Update** with `PUT /Users/{id}` for a full replacement. `PATCH /Users/{id}` is documented, but
   `ServiceProviderConfigs` reports `patch.supported: false` — verify behaviour on the account before
   depending on it, and fall back to `PUT`.
6. **Deactivate rather than delete** where possible; `DELETE /Users/{id}` is permanent.

## Rules

- This is **SCIM 1.1, not SCIM 2.0**. Do not send RFC 7644 PATCH operation documents or 2.0 schema URNs.
- AgilePlace names Okta, OneLogin, and Ping Identity as compatible identity providers. If the account
  already has a SCIM connector configured, **do not also drive this API directly** — you will fight the
  connector.
- The same per-user rate limit applies: watch `X-RateLimit-Remaining` and back off on `429`.
- User lifecycle changes revoke real access. Confirm before deleting or deactivating anyone.
