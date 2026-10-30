# Infer by Flow7

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

**Areas:** AI/ML inference · LLM API gateway · Responses-compatible API · Coding-agent tooling · Developer Tools · Usage-Based Billing · Prepaid billing · Agent-Native · Agent Skills · Model Routing

## Infer by Flow7 on APIs.io

Everything profiled for Infer by Flow7 is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/infer-by-flow7/](https://apis.io/providers/infer-by-flow7/)** — or go straight to one of the APIs or properties below.

### APIs (3)

- [Infer by Flow7 Catalog API](https://apis.io/apis/infer-by-flow7/infer-by-flow7-catalog-api/) — Model selectors, published prices, and route capability metadata.
- [Infer by Flow7 Inference API](https://apis.io/apis/infer-by-flow7/infer-by-flow7-inference-api/) — Authenticated customer inference operations.
- [Infer by Flow7 Status API](https://apis.io/apis/infer-by-flow7/infer-by-flow7-status-api/) — Customer-facing service state without private routing topology.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [infer-by-flow7-mcp.yml](https://apis.io/servers/infer-by-flow7/infer-by-flow7-mcp-yml/)

#### Collections (1)

Postman and Open Collection request collections.

- [Infer by Flow7 Public API](https://apis.io/collections/infer-by-flow7/open-infer-by-flow7-public-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Infer By Flow7 Public Api Overlay](https://apis.io/overlays/infer-by-flow7/infer-by-flow7-public-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Infer By Flow7 Authentication](https://apis.io/security/infer-by-flow7/infer-by-flow7-authentication/)
- [Infer By Flow7 Domain Security](https://apis.io/security/infer-by-flow7/infer-by-flow7-domain-security/)
- [Infer By Flow7 Trust Center](https://apis.io/security/infer-by-flow7/infer-by-flow7-trust-center/)
- [Infer By Flow7 Vulnerability Disclosure](https://apis.io/security/infer-by-flow7/infer-by-flow7-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Infer By Flow7 Scopes](https://apis.io/scopes/infer-by-flow7/infer-by-flow7-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Infer By Flow7 Plans Pricing](https://apis.io/plans/infer-by-flow7/infer-by-flow7-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Infer By Flow7 Rate Limits](https://apis.io/rate-limits/infer-by-flow7/infer-by-flow7-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Documentation](https://infer.flow7.org/docs)
- [Getting started](https://infer.flow7.org/docs#quickstart)
- [API reference](https://infer.flow7.org/docs)
- [Pricing](https://infer.flow7.org/models)
- [Sign up](https://infer.flow7.org/signup)
- [Support](https://infer.flow7.org/support)
- [Terms of service](https://infer.flow7.org/terms)
- [Privacy policy](https://infer.flow7.org/privacy)
- [Status](https://infer.flow7.org/status)

## API Evangelist rating

**Unrated** — no public website could be reached for this company, so there was almost nothing to measure and nothing a reader could check.

This is not a score of zero. No rating is published for this company. If that is wrong because something public exists that we missed, say so on this repository or email [info@apievangelist.com](mailto:info@apievangelist.com) and it will be re-run — free, and no justification needed.

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Infer by Flow7: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/infer-by-flow7/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
