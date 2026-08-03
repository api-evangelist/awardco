# Awardco (awardco)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Awardco is an all-in-one employee recognition, rewards, and engagement platform built around a global rewards marketplace that includes a native Amazon Business integration, gift cards, service awards, and swag. It lets organizations recognize contributions, fund and redeem employee points, run milestone/service-award programs, and gather engagement signals from a single system.

Awardco exposes a **documented public REST API** at `https://api.awardco.com/api` (each method appended as `/api/{method}`). Callers authenticate with a **permission-scoped API key** passed as a request header, all responses are JSON with a `success` flag, and all timestamps are ISO 8601.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/awardco/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/awardco/refs/heads/main/apis.yml)

## Access model (read this first)

The API is documented and public in the sense that its conventions are published at [code.awardco.com/api](https://code.awardco.com/api), but it is **not open self-serve**:

- Using it requires an **Awardco account** plus the **API Key Management** permission.
- API keys are **scoped per endpoint** - you grant only the operations an integration needs.
- **Sensitive** endpoints (Create User, Reset User Password, Import Users) are meant to be granted sparingly.
- Integration **partners** additionally send an `X-Partner-Id` header for identification and troubleshooting.
- For custom flows beyond the prebuilt connectors, Awardco offers **Awardco Connect**, alongside prebuilt **HRIS, SSO/SAML, Slack, and Microsoft Teams** integrations.

**Endpoints are modeled, not transcribed.** Awardco's public docs confirm the base URL, API-key header auth, the JSON/`success` response envelope, ISO 8601 timestamps, and named capabilities (create/import users, reset password, recognize employees / award points, retrieve or schedule reports). Awardco does **not** publish exact per-method paths, request bodies, or response schemas on the open web (the reference site is a single-page app that returns `Authorization failed` without a key, and the help articles are gated). The API surfaces below are therefore modeled from Awardco's documentation and help center - `endpointsModeled: true` - and no endpoints were fabricated beyond the documented capabilities. No OpenAPI, Postman collection, or WebSocket surface is included because none could be sourced.

## Tags

- Employee Recognition
- Rewards
- Engagement
- HR Tech
- Incentives
- Points

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Awardco Users API

Provision and manage employees in an Awardco instance. Awardco's public documentation names **Create User**, **Import Users** (bulk), and **Reset User Password** endpoints, all flagged as sensitive and permission-scoped. `endpointsModeled: true`.

- **Documentation:** [https://code.awardco.com/api](https://code.awardco.com/api)
- **Base URL:** `https://api.awardco.com/api`

### Awardco Recognition API

Programmatically recognize employees and issue recognition tied to an organization's programs and values. Recognizing employees is a documented capability of API keys with the appropriate permission; the exact method path and payload are not published, so this surface is modeled. `endpointsModeled: true`.

- **Documentation:** [https://code.awardco.com/api](https://code.awardco.com/api)
- **Base URL:** `https://api.awardco.com/api`

### Awardco Points and Awards API

Award, adjust, and reconcile employee point balances that fund redemptions in Awardco's rewards marketplace (Amazon Business, gift cards, swag, service awards). Awarding and adjusting points are documented administrative capabilities; specific method paths and schemas are not public. `endpointsModeled: true`.

- **Documentation:** [https://code.awardco.com/api](https://code.awardco.com/api)
- **Base URL:** `https://api.awardco.com/api`

### Awardco Reporting API

Retrieve reporting data and program activity over REST. Awardco documents that reporting templates can be exported to CSV or scheduled to send via its REST API, and that API keys can retrieve reports. Method paths and response schemas are not published. `endpointsModeled: true`.

- **Documentation:** [https://code.awardco.com/api](https://code.awardco.com/api)
- **Base URL:** `https://api.awardco.com/api`

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/awardco)
- [Website](https://www.awardco.com)
- [Documentation](https://code.awardco.com/api)
- [Authentication / API Keys](https://awardco.my.site.com/Customerhelp/s/article/Managing-API-Keys)
- [Integrations](https://www.awardco.com/platform/integrations)
- [Plans](plans/awardco-plans-pricing.yml)
- [Rate Limits](rate-limits/awardco-rate-limits.yml)
- [Fin Ops](finops/awardco-finops.yml)
- [Blog](https://www.awardco.com/blog)

## Pricing

Awardco pricing is **quote-based**. Public plan tiers are Standard, Scale, Enterprise, Service Awards Only, and Automated + 2, plus add-ons (A-Pay, Company Store, Awardco Engage). Per-user and platform fees are not publicly disclosed; startups and small businesses (100 employees or fewer) can get flexible packages **starting at $3,000**. The API is an account capability, not a separately metered product. See [plans/awardco-plans-pricing.yml](plans/awardco-plans-pricing.yml).

## WebSocket

**No.** Awardco does not publish a documented public WebSocket API. Its own API is request/response REST over HTTPS. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
