---
name: leankit-create-and-place-card
description: Create a card in Planview AgilePlace (LeanKit) on the right board and lane, tag it, assign it, and move it once work starts.
api: leankit:agileplace-api
generated: '2026-07-19'
method: generated
source: openapi/leankit-agileplace-api-openapi.yml
operations:
  - boardList
  - boardGet
  - boardLeafLanes
  - cardTypeList
  - tagsList
  - cardCreate
  - cardAssignMembers
  - cardMove
  - cardGet
---

# Create and place a card in AgilePlace

Base URL is `https://{account}.leankit.com/io`. Send
`Authorization: Bearer <token>`, `Content-Type: application/json`, and `Accept: application/json`.

## Steps

1. **Resolve the board.** Call `boardList` (`GET /io/board`) with a search parameter, or use
   `userListMyRecentBoards` (`GET /io/user/me/board/recent`) when the user says "my board". Cache the
   board id — do not re-resolve it on every run.
2. **Resolve the destination lane.** Call `boardLeafLanes` (`GET /io/board/{boardId}/leafLanes`) to get
   the lanes that can actually hold cards, or `boardGet` (`GET /io/board/{boardId}`) for the full layout.
   Match the lane by label and cache the lane id.
3. **Resolve the card type** with `cardTypeList` (`GET /io/board/{boardId}/cardType`) when the user names
   one. Omit it to accept the board default.
4. **Create the card** with `cardCreate` (`POST /io/card`). The destination decides where it lands:
   - `{"destination": {"boardId": "..."}, "title": "..."}` → end of the board's default drop lane
   - `{"destination": {"laneId": "..."}, "title": "..."}` → end of that lane
   - `{"destination": {"cardId": "..."}, "title": "..."}` → the TODO lane of that card's taskboard
   Pass `?returnFullRecord=true` when you need the created card back in full.
5. **Assign people** with `cardAssignMembers` (`POST /io/card/assign`).
6. **Move it later** with `cardMove` (`POST /io/card/move`) when work starts. Confirm with `cardGet`
   (`GET /io/card/{cardId}`).

## Rules

- **There is no idempotency key.** A retried `cardCreate` creates a second card. On a timeout or a 5xx,
  search with `cardList` (`GET /io/card`) before retrying, and never retry a write blindly.
- **Set `externalCardId` and `externalLink`** on create when the card mirrors an issue in another system.
  That is how you find it again without storing a mapping table.
- **Respect the rate limit.** Every response carries `X-RateLimit-Limit`, `X-RateLimit-Remaining`, and
  `X-RateLimit-Reset` (a Unix timestamp). On `429`, wait for `Retry-After` (an HTTP-date) or
  `X-RateLimit-Reset` before continuing. Limits are per user and shared across all of that user's tokens.
- **Errors are status codes only** — there is no `problem+json` body. `422` means a required property was
  missing or invalid; `403` means the token's user lacks the board role; `404` means the id is wrong or
  invisible to this user.
- Dates are ISO 8601 in UTC, for example `2026-07-19T13:29:31Z`.
