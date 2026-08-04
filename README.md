# Jet2 (jet2)

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

Jet2 plc (London Stock Exchange: JET2, formerly Dart Group plc) is a British leisure travel group headquartered at Low Fare Finder House, Leeds Bradford Airport, Yeadon, Leeds, West Yorkshire. Its home market is the United Kingdom. The group fuses two businesses that most of the sector keeps apart: Jet2.com (IATA code LS, ICAO code EXS), the UK's third-largest airline, and Jet2holidays, the UK's largest ATOL holder. For the year ended 31 March 2026 it reported revenue of £7,482.1 million, operating profit of £439.6 million and a record 20.83 million passengers across 14 UK airport bases, with more than 63% of flown passengers buying an end-to-end package holiday. Jet2 sits at the direct end of the airline distribution chain: like easyJet and Ryanair it was built with no Global Distribution System dependency and therefore never needed IATA's New Distribution Capability as a remedy. Its API posture, stated honestly, is that Jet2 runs real production distribution APIs and publishes nothing about them — no developer portal, no reference documentation, no machine-readable contract, and no published commercial terms for access.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/jet2/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/jet2/refs/heads/main/apis.yml)

## Tags

- Travel
- United Kingdom
- Aviation
- Airline
- Low Cost Carrier
- Package Holidays
- Tour Operator
- Distribution
- Booking
- Ancillaries
- Partner Gated

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

No Jet2 API is publicly documented, so `apis[]` is intentionally empty.

Two Jet2 distribution APIs demonstrably exist in production, and neither is documented by Jet2:

1. **The Jet2.com flight distribution API**, reached by travel sellers through Kyte. The June 2025 Jet2.com/Kyte distribution agreement put Jet2 seats and the full ancillary range onto Kyte Direct Connect — which Kyte describes as "a powerful, flexible, JSON/REST API that supports full airline content and functionality from both NDC and LCC airlines" — opening Jet2 to travel management companies and corporate booking tools for the first time, with downstream desktop presentation via AirGateway.
2. **The Jet2holidays agency API**, which lets independent agencies sell Jet2 packages on their own websites for the agreed commission. Trade press on the trial notes that "agencies that want to use the API to its full potential must already have bookable websites", and that companies can sign up direct with Jet2holidays or through a third-party technology supplier.

Neither has a published base URL, operation, schema, authentication scheme, scope or rate limit. `api.jet2.com` resolves via `api.lb.jet2.com` and answers HTTP 200 with nothing but the stock Microsoft IIS 10.0 default page — 404 on `/swagger`, `/swagger.json`, `/openapi.json`, `/api-docs` and `/.well-known/openapi.json`. `api.jet2holidays.com` resolves and does not answer. `b2b.jet2.com` is a Microsoft ADFS organisational-account login. `developer`, `developers`, `docs`, `apis`, `ndc`, `partner`, `partners`, `trade`, `agent`, `sandbox`, `mcp`, `status`, `trust` and `xml` subdomains of `jet2.com` all fail to resolve. There is no official Jet2 GitHub organisation. Listing any of these as an API would be fabrication.

Third-party flight-data products marketed as a "Jet2.com API" (AirLabs, Aviationstack, FlightAware AeroAPI) are other companies' APIs that happen to cover LS/EXS flights. They are deliberately excluded.

## Distribution

Jet2 is **not** an NDC carrier. It is absent from Duffel's published list of NDC-certified airlines, no IATA NDC certification level or ARM index entry was found, `ndc.jet2.com` does not resolve, and no NDC endpoint, schema or message set exists anywhere. Kyte's own positioning separates "NDC" from "LCC proprietary content" and every piece of evidence places Jet2 on the proprietary side of that line.

Travelport's own Smartpoint documentation confirms the shape: **Jet2 is supported only as a "Direct Payment Carrier"**, Travelport's low-cost-carrier bolt-on rather than normal EDIFACT GDS participation. The documented constraints are the finding:

| Constraint | Documented behaviour |
| --- | --- |
| Carrier code | LS |
| Connections | Point-to-point only — "connecting flights are not supported" |
| Passengers per booking | 13 maximum (9 on Travelport+ and Apollo) |
| Multi-city | 8 destinations maximum |
| Currencies | GBP, EUR, CHF, CZK, PLN, USD |
| Payment | Restricted forms of payment, mandatory CVV |
| Post-booking changes | **None through the GDS** — "Requests for changes must be made directly through Jet2" |

Jet2.com never filed fares into the GDS rail as a normal participant. The GDSes reach it on Jet2's terms, not the other way round — which is why the NDC question, framed as an escape from GDS intermediation, simply does not arise here.

## Switching cost

- **Interface shape:** `proprietary-undocumented`. No standard is referenced — no NDC, no OpenTravel/OTA, no HTNG, no OpenAPI. Two real APIs exist and Jet2 has never described either in public. Nothing in a Jet2 integration is reusable against another carrier.
- **Second source:** `few-alternatives`. For Jet2's own inventory there is no second source at all — only Jet2 sells Jet2. For the *route* to it there are three verifiable and unequal options: Kyte (KDC, plus AirGateway downstream), Travelport as a Direct Payment Carrier (which cannot service a booking after creation), and a direct Jet2holidays agency agreement. Duffel publishes no Jet2 support. Jet2 publishes no approved-channel list at all, unlike easyJet's fourteen graded channels.
- **Exit path:** `no-export-published`. No export, dump, bulk or reporting operation exists, because no API is published. No privacy notice, portability commitment or data-protection contact could be retrieved from either domain — every HTML page on `jet2.com` and `jet2holidays.com` returned HTTP 000 to every automated client tried. UK GDPR Article 20 applies as a matter of law; Jet2 publishes no retrievable statement of how it implements it, and there is nothing whatsoever for an agency wanting its own booking book.
- **Identifier portability:** IATA airline designator LS, ICAO designator EXS and IATA 3-letter airport codes travel. The Jet2 booking reference does not — Travelport's own documentation concedes the GDS cannot modify or cancel a Jet2 booking it holds. No cross-reference to a GDS record locator or an IATA ticket number is published, and IATA/ARC accreditation is not required to sell Jet2.
- **Contractual lock-in:** *nothing verifiable.* A published Jet2holidays standard agency agreement exists in two indexed versions (April 2025 and 26 May 2021), and both were blocked by Akamai (HTTP 000, WebFetch timeout). **No clause is quoted anywhere in this repository, because none was read.** There is no Jet2 equivalent of easyJet's Distribution Charter: no public distribution policy, no approved-channel list, no reseller acceptable-use policy. Term, notice, exclusivity, fees, commission, data ownership and amendment rights are all unverifiable.
- **Access gate:** `commercial-agreement`. No published application route, contact, pricing or eligibility criteria. Kyte's FAQ is explicit that "Access to airline products is controlled by each airline. Kyte provides only technical connectivity through the KDC Network." No sandbox, no trial, no self-serve key, no published rate limits.

## Machine accessibility

Both `jet2.com` and `jet2holidays.com` sit behind Akamai bot management that terminates HTTP/2 streams with `INTERNAL_ERROR` and drops HTTP/1.1 requests. Every HTML page on both domains returned HTTP 000 to every client tried. Exactly one static asset came back: `https://www.jet2.com/robots.txt`, HTTP 200 once on 2026-07-28, quoted verbatim in [`review.yml`](review.yml) — it disallows `/api*` and `/docs*` and blocks CCBot outright. Company identity was therefore confirmed from the EV TLS certificate served by `www.jet2.com` (`O=JET2.COM LIMITED`, `serialNumber=02739537`, `street=Low Fare Finder House, Leeds Bradford Airport`, `L=Yeadon`, `ST=West Yorkshire`, `C=GB`) rather than from any page.

One hygiene observation, recorded but not exploited: `agent.jet2holidays.com` is a CNAME to `prod-uks-jet2-appservice-website.azurewebsites.net`, which has no A record — a dangling CNAME to a deallocated Azure Web App, a subdomain-takeover exposure pattern. Observed by DNS lookup only.

## Common Properties

- [Jet2.com](https://www.jet2.com/)
- [Jet2holidays](https://www.jet2holidays.com/)
- [Jet2holidays trade site for independent travel agents](https://trade.jet2holidays.com/)
- [Jet2holidays standard agency agreement (April 2025)](https://www.jet2holidays.com/-/media/pdfs/agency%20agreement_april_2025.pdf)
- [Jet2holidays standard agency agreement (effective 26 May 2021)](https://www.jet2holidays.com/-/media/pdfs/new_agencyagreement_jet2holidays.pdf)
- [ATOL protection](https://www.jet2holidays.com/atol)
- [Carrier information and liability notice](https://www.jet2.com/en/carrier-information-and-liability-notice)
- [About us](https://www.jet2.com/en/about-us)
- [Jet2 plc corporate and investor site](https://www.jet2plc.com/)
- [Wikipedia — Jet2 plc](https://en.wikipedia.org/wiki/Jet2_plc)
- [Wikipedia — Jet2.com](https://en.wikipedia.org/wiki/Jet2.com)

Full evidence, including every URL probed with its HTTP status, the DNS chain for every hostname, and the verbatim `robots.txt`, is in [`review.yml`](review.yml).

## Maintainers

- Kin Lane — kin@apievangelist.com
