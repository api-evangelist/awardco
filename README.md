# Awardco (awardco)

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
