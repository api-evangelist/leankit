---
name: leankit-triage-blocked-work
description: Find blocked and at-risk cards on an AgilePlace board, inspect their dependencies and history, and comment or raise a custom event to drive an automation.
api: leankit:agileplace-api
generated: '2026-07-19'
method: generated
source: openapi/leankit-agileplace-api-openapi.yml
operations:
  - boardCards
  - cardList
  - cardGet
  - dependenciesGetCard
  - connectionsChildren
  - connectionsParents
  - connectionsStatistics
  - cardActivity
  - commentList
  - commentCreate
  - automationInitiateCardEvent
---

# Triage blocked work in AgilePlace

Base URL is `https://{account}.leankit.com/io` with `Authorization: Bearer <token>`.

## Steps

1. **Pull the board's cards** with `boardCards` (`GET /io/board/{boardId}/card`), or search across boards
   with `cardList` (`GET /io/card`). Page with `limit` and `offset`; the response carries a `pageMeta`
   envelope with `totalRecords`, `offset`, `limit`, `startRow`, and `endRow`.
2. **Identify blocked cards** from each card's `blockedStatus` object (`isBlocked`, `reason`, `date`).
3. **Read the dependency picture** with `dependenciesGetCard` (`GET /io/card/{cardId}/dependency`).
   Dependencies carry a health status of Healthy, At risk, or Blocked (GA 2026-07-16). Walk the
   hierarchy with `connectionsChildren` (`GET /io/card/{cardId}/connection/children`) and
   `connectionsParents` (`GET /io/card/{cardId}/connection/parents`), and summarise with
   `connectionsStatistics` (`GET /io/card/{cardId}/statistics`).
4. **Establish how long it has been stuck** with `cardActivity` (`GET /io/card/{cardId}/activity`).
5. **Report back on the card** with `commentList` (`GET /io/card/{cardId}/comment`) then `commentCreate`
   (`POST /io/card/{cardId}/comment`). Read the existing comments first so you do not repeat a note the
   team already left.
6. **Hand off to the team's own automation** with `automationInitiateCardEvent`
   (`POST /io/card/{cardId}/automation/customevent`), raising the named custom event the board's
   automations already listen for. Prefer this to moving cards yourself — the board owner decided what
   should happen.

## Rules

- **Never move or unblock a card without explicit confirmation.** `cardMove` and `cardUpdate` change
  someone's live work board.
- Raising a custom event may fire a **Web service call automation**, which POSTs a signed payload to an
  external system (`x-lk-signature`, HMAC-SHA256 over the raw body). Treat it as an external side effect.
- **Batch politely.** Cache lane and board ids rather than re-resolving them, keep parallelism low, and
  honour `X-RateLimit-Remaining`. On `429`, stop until `Retry-After` / `X-RateLimit-Reset`.
- Reporting data from the Advanced Reporting API can be up to **24 hours stale** — use the v2 card
  endpoints, not the reporting export, when the answer must be current.
