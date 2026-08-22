# Infer by Flow7 (infer-by-flow7)

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

A single Responses-compatible inference API that fronts multiple model families through a private, opaque supplier pool. Public paid beta offering a prepaid-wallet billing model, locked prices, spending limits, and per-call receipts for accountable coding-agent inference. Four operations — two of them unauthenticated — cover a machine-readable price catalog, per-model route status with p95 latency, an authenticated selector list, and the Responses endpoint itself. Distinguished by an unusually legible commercial surface: the full rate card, including per-tier margin floors and dated market-reference discounts, is served as JSON without a key, and every completed request returns a receipt with the locked price version and the exact charge.

**APIs.json:** [https://infer-by-flow7.apievangelist.com/apis.yml](https://infer-by-flow7.apievangelist.com/apis.yml)

## Tags

- AI/ML inference
- LLM API gateway
- Responses-compatible API
- Coding-agent tooling
- Developer tools
- Usage-based billing
- Prepaid billing
- Agent-native
- Agent Skills
- Model routing

## Timestamps

- **Created:** 2026-08-11
- **Modified:** 2026-08-11

## APIs

### Infer Responses API

Responses-compatible inference REST API fronting many model families through opaque routing, with unauthenticated public catalog/status endpoints and authenticated model-list and Responses endpoints. Includes a public OpenAPI 3.1 contract, RFC 9727 api-catalog, llms.txt, and three published agent skills.

- **Human URL:** [https://infer.flow7.org/docs](https://infer.flow7.org/docs)
- **Base URL:** `https://infer.flow7.org/v1`

#### Tags

- AI/ML inference
- LLM API gateway
- Responses-compatible API
- Coding-agent tooling
- Developer tools
- Usage-based billing
- Prepaid billing
- Agent-native
- Agent Skills
- Model routing

#### Properties

- [OpenAPI](https://infer.flow7.org/openapi-public.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/infer-by-flow7-public-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/infer-by-flow7-public-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infer-by-flow7-public-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://infer.flow7.org/docs)
- [API Reference](https://infer.flow7.org/docs)
- [L L Ms Txt](https://infer.flow7.org/llms.txt)
- [L L Ms Txt](llms/infer-by-flow7-llms.txt)
- [Agent Skill](https://infer.flow7.org/.well-known/agent-skills/index.json)
- [Agent Skill](skills/_index.yml)
- [Authentication](authentication/infer-by-flow7-authentication.yml)
- [Conventions](conventions/infer-by-flow7-conventions.yml)
- [Idempotency](conventions/infer-by-flow7-conventions.yml)
- [Error Catalog](errors/infer-by-flow7-problem-types.yml)
- [Rate Limits](rate-limits/infer-by-flow7-rate-limits.yml)
- [Plans](plans/infer-by-flow7-plans-pricing.yml)
- [Sandbox](sandbox/infer-by-flow7-sandbox.yml)
- [Data Model](data-model/infer-by-flow7-data-model.yml)
- [Overlay](overlays/infer-by-flow7-public-api-overlay.yaml)
- [Lifecycle](lifecycle/infer-by-flow7-lifecycle.yml)
- [Changelog](changelog/infer-by-flow7-changelog.yml)
- [Conformance](conformance/infer-by-flow7-conformance.yml)

## Common Properties

- [M C P Server](mcp/infer-by-flow7-mcp.yml)
- [Domain Security](security/infer-by-flow7-domain-security.yml)
- [Developer Portal](https://infer.flow7.org/)
- [Documentation](https://infer.flow7.org/docs)
- [API Reference](https://infer.flow7.org/docs)
- [Getting Started](https://infer.flow7.org/docs#quickstart)
- [Support](https://infer.flow7.org/support)
- [Blog R S S](https://infer.flow7.org/feed.xml)
- [Pricing](https://infer.flow7.org/models)
- [Sign Up](https://infer.flow7.org/signup)
- [Terms of Service](https://infer.flow7.org/terms)
- [Privacy Policy](https://infer.flow7.org/privacy)
- [Status Page](https://infer.flow7.org/status)
- [Status Page](lifecycle/infer-by-flow7-lifecycle.yml)
- [Well Known](well-known/infer-by-flow7-well-known.yml)
- [A P I Catalog](https://infer.flow7.org/.well-known/api-catalog)
- [A P Is J S O N](https://infer.flow7.org/.well-known/apis.json)
- [Security](security/infer-by-flow7-vulnerability-disclosure.yml)
- [Vulnerability Disclosure](security/infer-by-flow7-vulnerability-disclosure.yml)
- [Compliance](conformance/infer-by-flow7-conformance.yml)
- [Packages](packages/infer-by-flow7-packages.yml)
- [Changelog](changelog/infer-by-flow7-changelog.yml)

## Maintainers

**FN:** Infer by Flow7
**URL:** https://infer.flow7.org
