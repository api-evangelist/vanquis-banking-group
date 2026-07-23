---
name: Initiate a domestic payment from Vanquis (PIS)
description: Create a domestic-payment consent, authorise the PSU, optionally confirm funds, then submit an idempotent domestic payment under the OBIE Read/Write PIS v3.1.10 standard.
api: openapi/obie-payment-initiation-openapi.yaml
operations:
  - CreateDomesticPaymentConsents
  - GetDomesticPaymentConsentsConsentId
  - GetDomesticPaymentConsentsConsentIdFundsConfirmation
  - CreateDomesticPayments
  - GetDomesticPaymentsDomesticPaymentId
---

# Initiate a domestic payment from Vanquis (PIS)

Prerequisite: you are an FCA-authorised PISP enrolled in the Open Banking Directory
and onboarded to Vanquis, using mutual-TLS with OBIE/eIDAS certificates.

## Steps

1. **Get a TPP token** via `client_credentials` (`TPPOAuth2Security`) with the
   `payments` scope.

2. **Create the payment consent** — `CreateDomesticPaymentConsents`
   (`POST /domestic-payment-consents`). Include `Initiation` (creditor account,
   amount, reference) and send `Authorization`, `x-fapi-interaction-id`,
   `x-idempotency-key`, and `x-jws-signature`. Capture the returned `ConsentId`.

3. **Authorise the PSU (SCA)** through the `authorization_code`/OIDC flow
   (`PSUOAuth2Security`, `payments` scope) referencing the `ConsentId`; exchange the
   code for a PSU token.

4. **Confirm the consent is authorised** — `GetDomesticPaymentConsentsConsentId`
   (`GET /domestic-payment-consents/{ConsentId}`); proceed only when `Status` is
   `Authorised`.

5. **(Optional) Check funds** — `GetDomesticPaymentConsentsConsentIdFundsConfirmation`
   (`GET /domestic-payment-consents/{ConsentId}/funds-confirmation`).

6. **Submit the payment** — `CreateDomesticPayments` (`POST /domestic-payments`) with a
   fresh, unique `x-idempotency-key` and a body whose `Initiation` matches the consent
   exactly. The key is honoured for 24 hours: replaying it returns the original result
   instead of creating a duplicate.

7. **Track settlement** — `GetDomesticPaymentsDomesticPaymentId`
   (`GET /domestic-payments/{DomesticPaymentId}`) and poll `Status`.

## Rules
- `x-idempotency-key` is REQUIRED on payment submission (string, maxLength 40); reuse
  the same key on retries. A mismatch/duplicate raises `UK.OBIE.Rules.DuplicateReference`.
- Submitting after the cut-off returns `UK.OBIE.Rules.AfterCutOffDateTime`.
- Validate the detached `x-jws-signature` on responses.
- See `conventions/vanquis-banking-group-conventions.yml` (idempotency) and
  `errors/vanquis-banking-group-problem-types.yml`.
