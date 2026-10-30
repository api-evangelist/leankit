# LeanKit

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

LeanKit is the enterprise Kanban platform now shipped by Planview as Planview AgilePlace, used to visually track and manage the flow of work from strategy to delivery across boards, lanes, cards, taskboards, and connected parent/child hierarchies. LeanKit exposes a documented RESTful v2 API at https://<yourhostname>.leankit.com/io/ covering boards, cards, lanes, comments, attachments, card types, custom fields, custom icons, tags, teams, users, board filters, connections, dependencies, planning series and increments, and board automations, plus a SCIM 1.1 User Provisioning API and an Advanced Reporting export API. Authentication is Basic or Bearer API token, responses are JSON, list endpoints page with limit/offset, and every response carries X-RateLimit-* headers. LeanKit was acquired by Planview in 2017 and the product was renamed Planview AgilePlace; the leankit.com host remains the per-account API and application domain.

**Areas:** Company · Kanban · Project Management · Agile · Work Management · Collaboration · Enterprise Software · Workflow Automation · Software-as-a-Service · Project Portfolio Management

## LeanKit on APIs.io

Everything profiled for LeanKit is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/leankit/](https://apis.io/providers/leankit/)** — or go straight to one of the APIs or properties below.

### APIs (25)

- [Planview AgilePlace Advanced Reporting API](https://apis.io/apis/leankit/advanced-reporting-api/) — Bulk export API for LeanKit / Planview AgilePlace reporting data — cards, card lane positions, blocked card history, comments, connections, lanes, tags, and…
- [LeanKit Account API](https://apis.io/apis/leankit/leankit-account-api/) — The account API from LeanKit — 1 operation(s) for account.
- [LeanKit Attachment API](https://apis.io/apis/leankit/leankit-attachment-api/) — The attachment API from LeanKit — 3 operation(s) for attachment.
- [LeanKit Automation API](https://apis.io/apis/leankit/leankit-automation-api/) — The automation API from LeanKit — 5 operation(s) for automation.
- [LeanKit Board API](https://apis.io/apis/leankit/leankit-board-api/) — The board API from LeanKit — 15 operation(s) for board.
- [LeanKit Board Filter API](https://apis.io/apis/leankit/leankit-board-filter-api/) — The board-filter API from LeanKit — 2 operation(s) for board-filter.
- [LeanKit Board Level API](https://apis.io/apis/leankit/leankit-board-level-api/) — The board-level API from LeanKit — 1 operation(s) for board-level.
- [LeanKit Board Template API](https://apis.io/apis/leankit/leankit-board-template-api/) — The board-template API from LeanKit — 2 operation(s) for board-template.
- [LeanKit Card API](https://apis.io/apis/leankit/leankit-card-api/) — The card API from LeanKit — 8 operation(s) for card.
- [LeanKit Card Scoring API](https://apis.io/apis/leankit/leankit-card-scoring-api/) — The card-scoring API from LeanKit — 1 operation(s) for card-scoring.
- [LeanKit Card Type API](https://apis.io/apis/leankit/leankit-card-type-api/) — The card-type API from LeanKit — 2 operation(s) for card-type.
- [LeanKit Comment API](https://apis.io/apis/leankit/leankit-comment-api/) — The comment API from LeanKit — 2 operation(s) for comment.
- [LeanKit Config API](https://apis.io/apis/leankit/leankit-config-api/) — The config API from LeanKit — 1 operation(s) for config.
- [LeanKit Connections API](https://apis.io/apis/leankit/leankit-connections-api/) — The connections API from LeanKit — 8 operation(s) for connections.
- [LeanKit Custom Field API](https://apis.io/apis/leankit/leankit-custom-field-api/) — The custom-field API from LeanKit — 1 operation(s) for custom-field.
- [LeanKit Custom Icon API](https://apis.io/apis/leankit/leankit-custom-icon-api/) — The custom-icon API from LeanKit — 2 operation(s) for custom-icon.
- [LeanKit Dependencies API](https://apis.io/apis/leankit/leankit-dependencies-api/) — The dependencies API from LeanKit — 2 operation(s) for dependencies.
- [LeanKit Lane API](https://apis.io/apis/leankit/leankit-lane-api/) — The lane API from LeanKit — 1 operation(s) for lane.
- [LeanKit Planning Series API](https://apis.io/apis/leankit/leankit-planning-series-api/) — The planning-series API from LeanKit — 6 operation(s) for planning-series.
- [LeanKit Tags API](https://apis.io/apis/leankit/leankit-tags-api/) — The tags API from LeanKit — 2 operation(s) for tags.
- [LeanKit Team API](https://apis.io/apis/leankit/leankit-team-api/) — The team API from LeanKit — 5 operation(s) for team.
- [LeanKit Token Auth API](https://apis.io/apis/leankit/leankit-token-auth-api/) — The token-auth API from LeanKit — 2 operation(s) for token-auth.
- [LeanKit User API](https://apis.io/apis/leankit/leankit-user-api/) — The user API from LeanKit — 6 operation(s) for user.
- [LeanKit User Invitation API](https://apis.io/apis/leankit/leankit-user-invitation-api/) — The user-invitation API from LeanKit — 2 operation(s) for user-invitation.
- [LeanKit Users API](https://apis.io/apis/leankit/leankit-users-api/) — The users API from LeanKit — 2 operation(s) for users.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Leankit Automation Webhooks](https://apis.io/asyncapis/leankit/leankit-automation-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [LeanKit / Planview AgilePlace MCP candidate](https://apis.io/servers/leankit/leankit-planview-agileplace-mcp-candidate/)

#### Collections (48)

Postman and Open Collection request collections.

- [Planview AgilePlace API (LeanKit) v2 account API](https://apis.io/collections/leankit/open-leankit-account-api/)
- [Planview AgilePlace API (LeanKit) v2 account attachment API](https://apis.io/collections/leankit/open-leankit-attachment-api/)
- [Planview AgilePlace API (LeanKit) v2 account automation API](https://apis.io/collections/leankit/open-leankit-automation-api/)
- [Planview AgilePlace API (LeanKit) v2 account board API](https://apis.io/collections/leankit/open-leankit-board-api/)
- [Planview AgilePlace API (LeanKit) v2 account board-filter API](https://apis.io/collections/leankit/open-leankit-board-filter-api/)
- [Planview AgilePlace API (LeanKit) v2 account board-level API](https://apis.io/collections/leankit/open-leankit-board-level-api/)
- [Planview AgilePlace API (LeanKit) v2 account board-template API](https://apis.io/collections/leankit/open-leankit-board-template-api/)
- [Planview AgilePlace API (LeanKit) v2 account card API](https://apis.io/collections/leankit/open-leankit-card-api/)
- [Planview AgilePlace API (LeanKit) v2 account card-scoring API](https://apis.io/collections/leankit/open-leankit-card-scoring-api/)
- [Planview AgilePlace API (LeanKit) v2 account card-type API](https://apis.io/collections/leankit/open-leankit-card-type-api/)
- [Planview AgilePlace API (LeanKit) v2 account comment API](https://apis.io/collections/leankit/open-leankit-comment-api/)
- [Planview AgilePlace API (LeanKit) v2 account config API](https://apis.io/collections/leankit/open-leankit-config-api/)
- [Planview AgilePlace API (LeanKit) v2 account connections API](https://apis.io/collections/leankit/open-leankit-connections-api/)
- [Planview AgilePlace API (LeanKit) v2 account custom-field API](https://apis.io/collections/leankit/open-leankit-custom-field-api/)
- [Planview AgilePlace API (LeanKit) v2 account custom-icon API](https://apis.io/collections/leankit/open-leankit-custom-icon-api/)
- [Planview AgilePlace API (LeanKit) v2 account dependencies API](https://apis.io/collections/leankit/open-leankit-dependencies-api/)
- [Planview AgilePlace API (LeanKit) v2 account lane API](https://apis.io/collections/leankit/open-leankit-lane-api/)
- [Planview AgilePlace API (LeanKit) v2 account planning-series API](https://apis.io/collections/leankit/open-leankit-planning-series-api/)
- [Planview AgilePlace API (LeanKit) v2 account tags API](https://apis.io/collections/leankit/open-leankit-tags-api/)
- [Planview AgilePlace API (LeanKit) v2 account team API](https://apis.io/collections/leankit/open-leankit-team-api/)
- [Planview AgilePlace API (LeanKit) v2 account token-auth API](https://apis.io/collections/leankit/open-leankit-token-auth-api/)
- [Planview AgilePlace API (LeanKit) v2 account user API](https://apis.io/collections/leankit/open-leankit-user-api/)
- [Planview AgilePlace API (LeanKit) v2 account user-invitation API](https://apis.io/collections/leankit/open-leankit-user-invitation-api/)
- [Planview AgilePlace API (LeanKit) v2 account users API](https://apis.io/collections/leankit/open-leankit-users-api/)
- [Planview AgilePlace API (LeanKit) v2 account API](https://apis.io/collections/leankit/postman-leankit-account-api/)
- …and 23 more published on APIs.io

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Leankit Agileplace Api Overlay](https://apis.io/overlays/leankit/leankit-agileplace-api-overlay/)
- [Leankit User Provisioning Api Overlay](https://apis.io/overlays/leankit/leankit-user-provisioning-api-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Leankit Authentication](https://apis.io/security/leankit/leankit-authentication/)
- [Leankit Domain Security](https://apis.io/security/leankit/leankit-domain-security/)
- [Leankit Trust Center](https://apis.io/security/leankit/leankit-trust-center/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.planview.com/products-solutions/products/agileplace/)
- [Documentation](https://success.planview.com/Planview_AgilePlace)
- [Getting started](https://success.planview.com/Planview_AgilePlace/Getting_Started)
- [API reference](https://success.planview.com/Planview_AgilePlace/AgilePlace_API/01_v2)
- [Pricing](https://www.planview.com/products-solutions/products/agileplace/agileplace-pricing/)
- [Sign up](https://www.planview.com/products-solutions/products/agileplace/get-agileplace/)
- [Support](https://success.planview.com/Planview_AgilePlace/Support)
- [Changelog](https://success.planview.com/Planview_AgilePlace/Product_Releases)
- [Blog](https://blog.planview.com/)
- [Trust centre](https://trust.planview.com/)
- [Terms of service](https://www.planview.com/legal/legal-terms/)
- [Privacy policy](https://www.planview.com/trust/privacy/statement/)
- [GitHub](https://github.com/LeanKit)
- [Status](https://status.planview.com/)

## API Evangelist rating

**Kin Score 62.8** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 64.7 |
| Contract governance | 18.2 |
| Operational transparency | 60.5 |
| Developer ergonomics | 67.3 |
| Access clarity | 60.5 |

**Agent readiness 42.0** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 29.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/leankit/](https://apis.io/providers/leankit/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for LeanKit: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/leankit/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
