---
name: Read Vanquis account and transaction data (AIS)
description: Set up an account-access consent, authorise the PSU, then read accounts, balances and transactions from Vanquis Bank under the OBIE Read/Write AIS v3.1.10 standard.
api: openapi/obie-account-info-openapi.yaml
operations:
  - CreateAccountAccessConsents
  - GetAccountAccessConsentsConsentId
  - GetAccounts
  - GetAccountsAccountIdBalances
  - GetAccountsAccountIdTransactions
---

# Read Vanquis account and transaction data (AIS)

Prerequisite: you are an FCA-authorised AISP enrolled in the Open Banking Directory,
onboarded to Vanquis, and hold valid OBIE/eIDAS transport + signing certificates.
All calls use mutual-TLS and a bearer access token; the production host is the one
Vanquis provisions to your TPP at onboarding.

## Steps

1. **Get a TPP token.** Use the `client_credentials` flow (`TPPOAuth2Security`) to obtain
   an access token with the `accounts` scope.

2. **Create the account-access consent** — `CreateAccountAccessConsents`
   (`POST /account-access-consents`). Send the `Permissions` you need (e.g.
   `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`) with the required
   headers: `Authorization`, `x-fapi-interaction-id`, and `x-jws-signature`. Capture
   the returned `ConsentId`.

3. **Redirect the PSU for authorisation (SCA).** Send the customer through the
   `authorization_code` / OIDC hybrid flow (`PSUOAuth2Security`, `accounts` scope),
   referencing the `ConsentId`. On return, exchange the code for a PSU access token.

4. **Confirm consent status** — `GetAccountAccessConsentsConsentId`
   (`GET /account-access-consents/{ConsentId}`). Proceed only when `Status` is
   `Authorised`.

5. **List accounts** — `GetAccounts` (`GET /accounts`) with the PSU token to retrieve
   each `AccountId` covered by the consent.

6. **Read balances** — `GetAccountsAccountIdBalances`
   (`GET /accounts/{AccountId}/balances`).

7. **Read transactions** — `GetAccountsAccountIdTransactions`
   (`GET /accounts/{AccountId}/transactions`). Page with the `Links.Next` cursor and
   window with `fromBookingDateTime`/`toBookingDateTime`.

## Rules
- Echo/track `x-fapi-interaction-id` on every call for audit correlation.
- Respect OBIE polling limits; back off on HTTP `429`.
- Errors arrive as an OBIE `OBErrorResponse1` envelope with `UK.OBIE.*` codes — a
  `401` + `UK.OBIE.Reauthenticate` means the PSU must re-authenticate.
- See `conventions/vanquis-banking-group-conventions.yml` and
  `errors/vanquis-banking-group-problem-types.yml`.
