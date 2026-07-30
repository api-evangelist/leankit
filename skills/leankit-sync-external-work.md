---
name: leankit-sync-external-work
description: Incrementally sync AgilePlace cards changed since a watermark into an external system, and push updates back without duplicating cards.
api: leankit:agileplace-api
generated: '2026-07-19'
method: generated
source: openapi/leankit-agileplace-api-openapi.yml, conventions/leankit-conventions.yml
operations:
  - cardList
  - cardListCards
  - cardGet
  - cardUpdate
  - cardCreate
  - customFieldList
  - tagsList
  - boardLeafLanes
  - cardActivity
---

# Incrementally sync AgilePlace cards

Base URL is `https://{account}.leankit.com/io` with `Authorization: Bearer <token>`.

## Steps

1. **Bootstrap the board context once.** Call `boardLeafLanes` (`GET /io/board/{boardId}/leafLanes`),
   `customFieldList` (`GET /io/board/{boardId}/customfield`), and `tagsList`
   (`GET /io/board/{boardId}/tag`), then cache the results. Planview's own guidance is to cache resolved
   identifiers instead of looking them up on every run.
2. **Pull only what changed.** Call `cardList` (`GET /io/card`) with the `since` parameter set to your
   last successful watermark. This is the documented way to avoid polling full card state and the single
   biggest rate-limit saver. Use `cardListCards` (`POST /io/card/list`) when your filter is too large for
   a query string.
3. **Page through the result** with `limit` and `offset`, reading `pageMeta.totalRecords` to know when
   you are done.
4. **Correlate** each card by `externalCardId` (and `externalLink.url`) rather than by title. Read custom
   field values from `customFieldsByLabel` when present, otherwise from the `customFields[]` array.
5. **Write back** with `cardUpdate` (`PATCH /io/card/{cardId}`), sending an array of add / replace /
   remove operations. Create anything genuinely new with `cardCreate` (`POST /io/card`), always setting
   `externalCardId` so the next run matches it instead of duplicating it.
6. **Advance the watermark** only after the whole page set succeeded. Store it as an ISO 8601 UTC
   timestamp.

## Rules

- **No idempotency key exists.** Before creating, search by `externalCardId`; on a timeout, re-read
  before you re-write.
- **Rate limits are points per 60-second window, per user, shared across every token that user holds.**
  Most calls cost 1 point; expensive routes cost more. Read `X-RateLimit-Remaining` and
  `X-RateLimit-Reset` and pace against them; do not fan out 20 parallel requests.
- On `429`, wait for `Retry-After` (HTTP-date) or `X-RateLimit-Reset` (Unix timestamp), then resume from
  the same watermark — the sync must be restartable.
- If your HTTP stack cannot send `PATCH`, send `POST` with `X-HTTP-Method-Override: PATCH`.
- `422` means required properties were missing; fix the payload rather than retrying it unchanged.
