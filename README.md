# TrueLayer

TrueLayer is Europe's leading open banking platform providing unified access to bank data, payments, payouts, refunds, and variable recurring payments across the UK and EU. TrueLayer connects to 69+ financial institutions and enables instant bank payments, data enrichment, and account verification through a single API.

**URL:** [apis.yml](https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/apis.yml)

## APIs

### TrueLayer Payments API v3

Create and manage open banking payments, payouts, refunds, and variable recurring payment mandates.

- **Base URL:** `https://api.truelayer.com`
- **Sandbox:** `https://api.truelayer-sandbox.com`
- **Authentication:** OAuth2 Bearer token + request signing (Tl-Signature)
- **Documentation:** [Payments API Basics](https://docs.truelayer.com/docs/payments-api-basics)

**Key Endpoints:**
- `POST /v3/payments` — Create a payment (pay-in or single payment)
- `GET /v3/payments/{id}` — Get payment status
- `POST /v3/payments/{id}/refunds` — Create a refund
- `POST /v3/mandates` — Create a VRP mandate
- `GET/DELETE /v3/mandates/{id}` — Get or revoke a mandate
- `POST /v3/payouts` — Create a payout
- `GET /v3/merchant-accounts` — List merchant accounts
- `GET /v3/merchant-accounts/{id}/transactions` — Transaction history

**Webhook Events:** 17 event types including payment_creditable, mandate_authorized, payout_executed, refund_executed, balance_notification

### TrueLayer Data API

Access bank account data for account information, transactions, balances, and identity verification.

- **Documentation:** [Data API Basics](https://docs.truelayer.com/docs/data-api-basics)

## Artifacts

| Type | File |
|---|---|
| OpenAPI Spec (Payments) | [openapi/truelayer-payments-openapi.yml](openapi/truelayer-payments-openapi.yml) |
| Spectral Rules | [rules/truelayer-rules.yml](rules/truelayer-rules.yml) |
| Naftiko Capabilities | [capabilities/open-banking-payments.yaml](capabilities/open-banking-payments.yaml) |
| Shared Capability | [capabilities/shared/truelayer-payments.yaml](capabilities/shared/truelayer-payments.yaml) |
| Payment JSON Schema | [json-schema/truelayer-payment-schema.json](json-schema/truelayer-payment-schema.json) |
| Payment Structure | [json-structure/truelayer-payment-structure.json](json-structure/truelayer-payment-structure.json) |
| JSON-LD Context | [json-ld/truelayer-context.jsonld](json-ld/truelayer-context.jsonld) |
| Examples | [examples/](examples/) |
| Vocabulary | [vocabulary/truelayer-vocabulary.yml](vocabulary/truelayer-vocabulary.yml) |

## Capabilities

### Open Banking Payments (`capabilities/open-banking-payments.yaml`)

Workflow capability for the full open banking payment lifecycle — creating payments and mandates, handling payouts, processing refunds, and monitoring merchant accounts across UK and EU.

- **REST port:** 8080
- **MCP port:** 9090
- **Tools:** 12 tools covering payments, refunds, mandates, payouts, and merchant accounts

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
- **Modified:** 2026-05-03

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
