# TrueLayer GraphQL Schema

## Overview

This conceptual GraphQL schema represents the TrueLayer open banking platform, covering unified access to bank data, payments, payouts, variable recurring payments (VRP), identity verification, and consent management across the UK and EU. TrueLayer connects to 69+ financial institutions through a single API surface.

The schema is derived from the [TrueLayer Data API](https://docs.truelayer.com/docs/data-api-basics) and [Payments API v3](https://docs.truelayer.com/docs/payments-api-basics) documentation.

## Schema File

- [truelayer-schema.graphql](truelayer-schema.graphql)

## Type Summary

### Account Number and Routing

| Type | Description |
|------|-------------|
| `AccountNumber` | Composite account identifier including number, sort code, IBAN, and BIC |
| `SortCode` | UK six-digit bank branch routing code |
| `IBAN` | International Bank Account Number with country and BBAN components |
| `BIC` | Bank Identifier Code (SWIFT) for international routing |

### Balance

| Type | Description |
|------|-------------|
| `AccountBalance` | Full balance snapshot including available, current, and overdraft amounts |
| `AvailableBalance` | Funds immediately available for use |
| `CurrentBalance` | Ledger balance including pending transactions |
| `CardBalance` | Balance for a credit or debit card including credit limit |

### Bank Account

| Type | Description |
|------|-------------|
| `BankAccount` | Core bank account entity with type, currency, details, and linked data |
| `BankAccountDetails` | Structured account number, sort code, IBAN, BIC, and bank metadata |
| `BankAccountType` | Enum: CURRENT, SAVINGS, LOAN, MORTGAGE, PENSION, CREDIT_CARD, OTHER |

### Card

| Type | Description |
|------|-------------|
| `Card` | Credit or debit card entity linked to a provider |
| `CardDetails` | Partial card number, cardholder name, validity dates, and PAN reference |
| `CardType` | Enum: DEBIT, CREDIT, PREPAID, CHARGE, OTHER |
| `PAN` | Masked primary account number |
| `EncryptedPAN` | Encrypted PAN with algorithm and key reference |

### Transaction

| Type | Description |
|------|-------------|
| `Transaction` | Individual financial transaction with amount, type, and status |
| `TransactionDetails` | Extended transaction metadata including merchant, category, and running balance |
| `TransactionType` | Enum: CREDIT, DEBIT |
| `TransactionStatus` | Enum: PENDING, SETTLED, FAILED, CANCELLED, REVERSED |
| `TransactionCategory` | Enum covering 20 spending categories (GROCERIES, TRANSPORT, BILLS, etc.) |

### Merchant

| Type | Description |
|------|-------------|
| `Merchant` | Merchant entity linked to a transaction |
| `MerchantDetails` | Merchant address, city, country, MCC, and website |
| `Category` | Hierarchical spending category with optional parent |

### Standing Orders and Direct Debits

| Type | Description |
|------|-------------|
| `StandingOrder` | Scheduled recurring payment instruction from an account |
| `StandingOrderStatus` | Enum: ACTIVE, INACTIVE, CANCELLED, EXPIRED |
| `DirectDebit` | Variable recurring debit instruction authorised by the account holder |
| `DirectDebitDetails` | Reference, mandate identification, and contract date |
| `DirectDebitStatus` | Enum: ACTIVE, INACTIVE, FAILED, CANCELLED |

### Payment

| Type | Description |
|------|-------------|
| `Payment` | Open banking payment entity covering initiation through settlement |
| `PaymentDetails` | Reference, beneficiary, remittance, and scheme details |
| `PaymentStatus` | Enum covering full payment lifecycle (AUTHORIZATION_REQUIRED through REFUNDED) |
| `PaymentMethod` | Enum: BANK_TRANSFER, MANDATE, MERCHANT_ACCOUNT |
| `PaymentRequest` | Input representation of a payment initiation request |

### Mandate (Variable Recurring Payments)

| Type | Description |
|------|-------------|
| `Mandate` | VRP mandate authorising future variable debits |
| `MandateDetails` | Constraint type, periodic limits, validity window, and reference |
| `MandateStatus` | Enum covering mandate lifecycle (AUTHORIZATION_REQUIRED through EXPIRED) |

### Provider

| Type | Description |
|------|-------------|
| `Provider` | Financial institution connected to the TrueLayer network |
| `ProviderDetails` | Display name, logo, country, and division information |
| `ProviderCredentials` | OAuth client ID, redirect URI, and scopes for a provider |
| `ProviderType` | Enum: BANK, CREDIT_CARD, INSURANCE, INVESTMENT, PENSION, OTHER |

### Authentication and Tokens

| Type | Description |
|------|-------------|
| `AuthFlow` | Enum: OAUTH, CREDENTIALS, API_KEY |
| `AuthDetails` | Flow type, redirect URI, state, and nonce for authorisation |
| `AuthToken` | Short-lived access token with refresh and expiry metadata |
| `OAuthToken` | OAuth 2.0 token pair with scopes and expiry |
| `APIKey` | API key entity with scopes, creation date, and activation status |
| `Token` | Generic token value wrapper |

### Consent

| Type | Description |
|------|-------------|
| `Consent` | Data sharing consent granted by a user to access their bank data |
| `ConsentDetails` | Permissions, expiry window, and data access duration |
| `ConsentScope` | Enum: ACCOUNTS, BALANCE, TRANSACTIONS, CARDS, IDENTITY, DIRECT_DEBITS, STANDING_ORDERS, OFFLINE_ACCESS |
| `ConsentStatus` | Enum: AWAITING_AUTHORISATION, AUTHORISED, REJECTED, REVOKED, EXPIRED |
| `ConsentExpiry` | Expiry timestamp and duration for a consent grant |

### Identity

| Type | Description |
|------|-------------|
| `UserInfo` | Authenticated user profile with linked accounts, cards, and consents |
| `UserDetails` | Full name, email, phone, date of birth, address, and nationality |
| `VerifiedIdentity` | Bank-verified identity record tied to a user and provider |
| `BankIdentity` | Identity data sourced from bank records including account and sort code |

### Utility

| Type | Description |
|------|-------------|
| `Metadata` | Generic key-value metadata pair |
| `Error` | Structured error with code, message, detail, trace ID, and type URI |
| `ErrorCode` | Enum covering common TrueLayer API error conditions |

## Queries

| Query | Description |
|-------|-------------|
| `account(id)` | Retrieve a bank account by ID |
| `accounts` | List all accessible bank accounts |
| `card(id)` | Retrieve a card by ID |
| `cards` | List all accessible cards |
| `transactions(accountId, from, to)` | Paginated transaction list for an account |
| `balance(accountId)` | Account balance snapshot |
| `cardBalance(cardId)` | Card balance snapshot |
| `standingOrders(accountId)` | Standing orders on an account |
| `directDebits(accountId)` | Direct debits on an account |
| `payment(id)` | Retrieve a payment by ID |
| `payments` | List payments |
| `mandate(id)` | Retrieve a VRP mandate by ID |
| `mandates` | List VRP mandates |
| `identity` | Authenticated user identity and linked data |
| `provider(id)` | Retrieve a provider by ID |
| `providers(countryCode)` | List providers, optionally filtered by country |
| `consent(id)` | Retrieve a consent by ID |
| `consents` | List active consents |

## Mutations

| Mutation | Description |
|----------|-------------|
| `createPayment(input)` | Initiate a new open banking payment |
| `cancelPayment(id)` | Cancel a pending payment |
| `refundPayment(id, amountInMinor)` | Initiate a full or partial refund |
| `createMandate(input)` | Create a new VRP mandate |
| `revokeMandate(id)` | Revoke an active mandate |
| `revokeConsent(id)` | Revoke a data sharing consent |
| `exchangeCode(code, redirectUri)` | Exchange an authorisation code for tokens |
| `refreshToken(refreshToken)` | Refresh an expired access token |

## References

- [TrueLayer Documentation](https://docs.truelayer.com/)
- [Data API Basics](https://docs.truelayer.com/docs/data-api-basics)
- [Payments API Basics](https://docs.truelayer.com/docs/payments-api-basics)
- [API Reference](https://docs.truelayer.com/reference)
- [Webhooks Reference](https://docs.truelayer.com/docs/payments-api-webhook-reference)
