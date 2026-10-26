# Ensurance (ensurance)

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

Ensurance Limited (ASX:ENA) was an Australian ASX-listed insurance underwriting agency headquartered in Perth, Western Australia, marketing itself as "innovating the online insurance sector." Its Australian arm, Ensurance Underwriting Australia, operated as a wholesale underwriting agency under an Australian Financial Services Licence, placing construction-specific products with a consortium of local and international capacity — Lloyd's, Swiss Re and XL Catlin — and distributing them exclusively through a broker network the company described as 340-plus intermediaries. A sister company, Ensurance UK Limited, ran as a Managing General Agent authorised and regulated by the UK Financial Conduct Authority and a coverholder at Lloyd's.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ensurance/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ensurance/refs/heads/main/apis.yml)

## Tags

- Insurance
- Australia
- Underwriting
- Property and Casualty
- Construction Insurance
- Managing General Agent
- Broker
- Wholesale Insurance
- Insurtech
- Partner Gated
- No Public API

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

**None.** Ensurance publishes no public API, and on the evidence available never did.

This is a deliberate, verified empty record rather than an incomplete one. It is exactly the outcome the Australian insurance seam predicts, and recording it accurately is the point.

### What was probed

Every conventional developer path on `ensurance.com.au` — `/developers`, `/developer`, `/api`, `/apis`, `/docs`, `/partners`, `/integrations`, `/developer-portal`, `/brokers` — returns **HTTP 301** from `nginx/1.26.2` to a single Chase Underwriting Solutions page. The redirect is a blanket catch-all: every path resolves to the same `Location`. The domain's TLS certificate (Let's Encrypt E5, `CN=ensurance.com.au`) **expired 2025-09-26** and has not been renewed, so any client using default verification cannot reach the primary domain at all.

The hostnames `developer.`, `developers.`, `docs.`, `api.`, `bob.`, `partner.` and `euw.ensurance.com.au` do not resolve.

### The false positive worth recording

`api.ensurance.ltd` and `developer.ensurance.ltd` both return **HTTP 200**. Neither is a developer surface. Each serves a byte-identical 4,126-byte default Bootstrap landing template titled *"Tapanko - Making Complex Tasks Easy"* — the same body returned by a randomly generated control hostname on the same domain. This is wildcard DNS with an unconfigured web-server default. It is documented here so the 200 status is never mistaken for a portal.

### The only integration surface that ever existed

Ensurance marketing described a "customised online platform" giving intermediaries "fast, simple, reliable and comprehensive construction insurance." That platform was **BOB** at `bob.ensurance.com.au`: an ASP.NET MVC quote-and-proposal wizard behind `/Login/Login`, with per-broker deep links of the form `/Proposal/New/3/Agent/{AGENTCODE}`. Quote and bind were reachable by a logged-in human agent, never by a program. There was no issuance API and no first-notice-of-loss API. The host is now offline.

| Verb | Exposed | Surface |
| --- | --- | --- |
| Quote | No | Historic, agent login-walled (BOB) |
| Bind | No | Historic, agent login-walled (BOB) |
| Issue | No | Never documented |
| FNOL | No | Never documented |

### ACORD posture

**No ACORD reference found.** A case-insensitive search for ACORD, AL3, ACORD XML, NGDS and IVANS across the complete 1,520-URL Wayback index for `ensurance.com.au` and its subdomains returned zero matches, and the live Chase Underwriting site names no ACORD standard, agency-download feed, or agency-management-system integration. Australian construction-lines wholesale distribution here ran on a proprietary web portal, not on a standards-based interchange.

### Auth, specs, events

- **Auth model:** none public. No API key issuance, no OAuth2, no mTLS, no SAML federation. `/.well-known/openid-configuration` and `/.well-known/oauth-authorization-server` are served by no Ensurance or Chase hostname — 301 (catch-all redirect) on the `ensurance.com.au` and `ensurance.ltd` apexes, 404 on `3rdp.`, `api.ensurance.ltd` and Chase. The historic BOB portal used form-based session login.
- **OpenAPI / Swagger:** none. `/openapi.json`, `/openapi.yaml`, `/swagger.json`, `/v1/openapi.json`, `/api-docs`, `/spec` and `/redoc` all 404. There is no `openapi/` directory in this repository because there is nothing real to put in it.
- **AsyncAPI / webhooks / events:** none.
- **GraphQL, gRPC, Postman:** none.

## Current status

Every request to `ensurance.com.au` and to the parallel `ensurance.ltd` domain family now lands on **Chase Underwriting Solutions Pty Ltd** (ABN 50 156 554 808, AFSL 454344), an Australian professional-lines underwriting agency covering professional indemnity, cyber liability, IT liability and management liability. Chase publishes no API, no developer portal and no ACORD posture either; brokers are directed to contact regional underwriters directly. The redirect is the observed fact recorded here — no transaction terms are asserted.

One hostname still serves its own content: `3rdp.ensurance.com.au`, a page describing "3RDP | Innovative Remote Platform," an internal secure remote-desktop and VPN environment for staff. It is not an insurance API surface.

## Market context

Australia has the legal machinery for open insurance and no live obligation. APRA supervises prudentially, and the Consumer Data Right that already opened banking and energy was designated to extend to general insurance, then deferred and de-prioritised. General insurers and underwriting agencies therefore face no forcing function to expose anything. Ensurance is a clean illustration of what that produces: a company that positioned itself as innovating online insurance and still shipped its entire intermediary experience as a login-walled web portal, with no API, no specification, and no ACORD posture.

## Identity note

`github.com/ensurance` is an **unrelated** organisation (contact `opensource@howtohireme.ru`, two repositories, last updated 2018). It is deliberately not attributed to this company.

## Artifacts in this record

There is no `openapi/`, `asyncapi/`, `mcp/`, `skills/`, `errors/`, `conventions/`, `scopes/` or `authentication/` directory here, because there is no specification and no auth surface to derive them from. What the enrichment pipeline could honestly produce is:

- [`conformance/ensurance-conformance.yml`](conformance/ensurance-conformance.yml) — standards posture as evidenced negatives: OpenAPI, AsyncAPI, GraphQL, gRPC, OAuth2, OIDC, RFC 9457, RFC 9116, RFC 8594, and the insurance interchange standards (ACORD AL3, ACORD XML, NGDS, IVANS), plus the Australian CDR general-insurance designation-then-deferral.
- [`lifecycle/ensurance-lifecycle.yml`](lifecycle/ensurance-lifecycle.yml) — the estate lifecycle: certificate issued 2025-06-28, expired 2025-09-26, whole domain family 301'd to Chase by 2026-07-25; retired `bob.`/`partner.`/`euw.` hosts; surviving `3rdp.` host; successor entity.
- [`security/ensurance-domain-security.yml`](security/ensurance-domain-security.yml) — probed TLS/HSTS/DNSSEC/CAA/SPF/DMARC. `ensurance.com.au` fails certificate verification and carries no DNSSEC, no CAA and no DMARC record.
- [`well-known/ensurance-well-known.yml`](well-known/ensurance-well-known.yml) — the `/.well-known` probe log. Zero documents served, so no `WellKnown` or `SecurityTxt` pointer is claimed in `apis.yml`.
- [`packages/ensurance-packages.yml`](packages/ensurance-packages.yml) — no first-party SDK anywhere, plus the **"ensurance" homonym trap**: unrelated assertion/validation libraries hold that name on npm, PyPI, RubyGems and Packagist and must never be attributed to this company.
- [`llms/ensurance-llms.txt`](llms/ensurance-llms.txt) — this record in llms.txt form for AI consumers.

### A false positive worth knowing about

Following redirects (`curl -L`) returns **HTTP 200 for every path** on `ensurance.com.au` and `ensurance.ltd` — including `/openapi.json`, `/swagger.json`, `/llms.txt` and `/.well-known/security.txt` — because the blanket 301 lands on the Chase Underwriting page, which returns 200. That 200 is the redirect destination, not the requested document. Probe these hosts with `curl -I` and read the first response.

## Links

- [Ensurance (primary domain — expired TLS, 301 catch-all)](https://ensurance.com.au/)
- [Chase Underwriting Solutions — current redirect destination](https://www.chaseunderwriting.com.au/capabilities/professional-risks/)
- [3RDP Remote Platform](https://3rdp.ensurance.com.au/)
- [Review findings](review.yml)
