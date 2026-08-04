# TrueLayer (truelayer)

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

TrueLayer is Europe's leading open banking platform providing unified access to bank data, payments, payouts, refunds, and variable recurring payments across the UK and EU. TrueLayer connects to 69+ financial institutions and enables instant bank payments, data enrichment, and account verification through a single API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Data API
- Financial Services
- Open Banking
- Payments
- PSD2
- UK Banking
- VRP

## Timestamps

- **Created:** 2026-03-27
- **Modified:** 2026-05-19

## APIs

### TrueLayer Payments API

The TrueLayer Payments API v3 enables creation and management of open banking payments, payouts, refunds, and variable recurring payment mandates. Supports closed-loop pay-ins, single external payments, VRP mandates, merchant account management, and full webhook event coverage across UK and EU markets.

- **Human URL:** [https://docs.truelayer.com/docs/payments-api-basics](https://docs.truelayer.com/docs/payments-api-basics)
- **Base URL:** `https://api.truelayer.com`

#### Tags

- Open Banking
- Payments
- Payouts
- Refunds
- VRP

#### Properties

- [Documentation](https://docs.truelayer.com/docs/payments-api-basics)
- [Getting Started](https://docs.truelayer.com/docs/create-a-payment)
- [Webhooks](https://docs.truelayer.com/docs/payments-api-webhook-reference)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/openapi/truelayer-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Spectral Rules](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/rules/truelayer-rules.yml)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/json-schema/truelayer-payment-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [J S O N L D Context](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/json-ld/truelayer-context.jsonld)
- [Vocabulary](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/vocabulary/truelayer-vocabulary.yml)
- [Postman Collection](collections/truelayer-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/truelayer-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### TrueLayer Data API

The TrueLayer Data API provides access to bank account data including account information, balances, transactions, identity verification, and standing orders. Used for account verification, affordability assessments, and financial data enrichment.

- **Human URL:** [https://docs.truelayer.com/docs/data-api-basics](https://docs.truelayer.com/docs/data-api-basics)
- **Base URL:** `https://api.truelayer.com`

#### Tags

- Account Data
- Bank Data
- Data API
- Identity Verification
- Open Banking

#### Properties

- [Documentation](https://docs.truelayer.com/docs/data-api-basics)
- [Reference](https://docs.truelayer.com/reference)
- [Postman Collection](collections/truelayer-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/truelayer-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://truelayer.com/)
- [Documentation](https://docs.truelayer.com/)
- [API Reference](https://docs.truelayer.com/reference)
- [GitHub Organization](https://github.com/TrueLayer)
- [Console](https://console.truelayer.com/)
- [Sandbox](https://console.truelayer-sandbox.com/)
- [S D Ks](https://docs.truelayer.com/docs/client-libraries)
- [Changelog](https://docs.truelayer.com/changelog)
- [Blog](https://truelayer.com/blog/)
- [LinkedIn](https://www.linkedin.com/company/truelayer/)
- [Twitter](https://twitter.com/TrueLayer)
- [M C P Server](https://github.com/TrueLayer/truelayer_mcp)
- [L L Ms Txt](https://docs.truelayer.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
