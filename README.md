# Vanquis Banking Group (vanquis-banking-group)

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
