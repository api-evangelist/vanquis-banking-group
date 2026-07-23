# Vanquis Banking Group (vanquis-banking-group)

Vanquis Banking Group plc (formerly Provident Financial plc, rebranded 2023) is a UK specialist non-prime lender and savings bank headquartered in Bradford, England, listed on the London Stock Exchange under the ticker VANQ and serving around 1.75 million customers under the Vanquis, Moneybarn and Snoop brands. Its banking subsidiary, Vanquis Bank Limited, is authorised by the Prudential Regulation Authority and regulated by the Financial Conduct Authority (Financial Services Register no. 221156), and as an FCA-authorised ASPSP it is a UK Open Banking participant (not one of the CMA9). It exposes the OBIE Read/Write API family at v3.1.10 - Account & Transaction Information (AIS), Payment Initiation (PIS) and Confirmation of Funds (CBPII) - plus Dynamic Client Registration, onboarded and secured through the Open Banking Directory under the PSD2 / FAPI security profile. As a credit-card and savings specialist with no branch or current-account estate, Vanquis publishes no public Open Data (ATM/Branch/PCA/BCA) API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vanquis-banking-group/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vanquis-banking-group/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- United Kingdom
- Specialist Lender
- Credit Cards
- Account Information
- Payments

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Vanquis Bank Account and Transaction API (AIS)

OBIE Read/Write Account and Transaction Information API (AISP), conformant to the Open Banking Read/Write Data API Standard v3.1.10. Account, balance and transaction access with customer consent, secured under the PSD2 / FAPI profile (OAuth2/OIDC, mutual-TLS, SCA). Production host is provisioned per TPP during Open Banking Directory onboarding and is not publicly published.

- **Human URL:** [https://www.vanquis.com/developer-portal/](https://www.vanquis.com/developer-portal/)

#### Tags

- Account Information
- AISP
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-account-info-openapi.yaml) — shared OBIE standard v3.1.10 (not a Vanquis-proprietary contract)
- [Documentation](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/937820271/Account+and+Transaction+API+Specification+-+v3.1)
- [API Reference](https://www.vanquis.com/developer-portal/)

### Vanquis Bank Payment Initiation API (PIS)

OBIE Read/Write Payment Initiation API (PISP), conformant to the Open Banking Read/Write API Standard v3.1.10. Payment initiation from a customer account with consent, secured under the PSD2 / FAPI profile.

- **Human URL:** [https://www.vanquis.com/developer-portal/](https://www.vanquis.com/developer-portal/)

#### Tags

- Payment Initiation
- PISP
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-payment-initiation-openapi.yaml) — shared OBIE standard v3.1.10
- [Documentation](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/937754701/Payment+Initiation+API+Specification+-+v3.1)
- [API Reference](https://www.vanquis.com/developer-portal/)

### Vanquis Bank Confirmation of Funds API (CBPII)

OBIE Read/Write Confirmation of Funds API (CBPII), conformant to the Open Banking Read/Write API Standard v3.1.10. Confirms availability of funds on a customer account with consent, secured under the PSD2 / FAPI profile.

- **Human URL:** [https://www.vanquis.com/developer-portal/](https://www.vanquis.com/developer-portal/)

#### Tags

- Confirmation of Funds
- CBPII
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-confirmation-funds-openapi.yaml) — shared OBIE standard v3.1.10
- [Documentation](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/937951380/Confirmation+of+Funds+API+Specification+-+v3.1)
- [API Reference](https://www.vanquis.com/developer-portal/)

### Vanquis Bank Dynamic Client Registration API

OpenID / OBIE Dynamic Client Registration (DCR), letting onboarded Third Party Providers register OAuth clients programmatically using OBIE/eIDAS certificates as part of Open Banking Directory enrolment. No Vanquis-proprietary OpenAPI is published for this surface.

- **Human URL:** [https://www.vanquis.com/developer-portal/](https://www.vanquis.com/developer-portal/)

#### Tags

- Dynamic Client Registration
- Onboarding
- Open Banking

#### Properties

- [Documentation](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/36667724/The+OpenBanking+OpenID+Dynamic+Client+Registration+Specification+-+v1.0.0-rc2)
- [API Reference](https://www.vanquis.com/developer-portal/)

## Common Properties

- [Website](https://www.vanquis.com/)
- [Group / Investor site](https://www.vanquisbankinggroup.com/)
- [Developer Portal](https://www.vanquis.com/developer-portal/)
- [Documentation](https://openbanking.atlassian.net/wiki/spaces/DZ/overview)
- [Sign Up (Open Banking Directory)](https://directory.openbanking.org.uk/s/login/SelfRegister)
- [Support (OB Service Desk)](https://directory.openbanking.org.uk/obieservicedesk/s/)
- [LinkedIn](https://www.linkedin.com/company/vanquis/)
- [Terms of Service](https://www.vanquis.com/legal/terms-of-use/)
- [Privacy Policy](https://www.vanquis.com/legal/privacy/)
- [Contact](https://www.vanquis.com/contact-us/)

## Note on Open Data

Vanquis Banking Group is a credit-card and savings specialist with no branch or current-account estate, so it publishes no public UK Open Data API (ATM/Branch/Personal Current Account/Business Current Account). Probes of candidate Open Data paths (e.g. `/open-banking/v2.3/atms`, `/open-banking/v3.1/atms`) returned HTTP 301 redirects to the marketing homepage with `text/html`, not JSON — no live Open Data endpoint exists.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
