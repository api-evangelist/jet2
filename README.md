# Jet2

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

Jet2 plc (London Stock Exchange: JET2, formerly Dart Group plc) is a British leisure travel group headquartered at Low Fare Finder House, Leeds Bradford Airport, Yeadon, Leeds, West Yorkshire — an address confirmed verbatim in the Extended Validation TLS certificate served by www.jet2.com, issued to "JET2.COM LIMITED", company serial number 02739537, jurisdiction GB. Its home market is the United Kingdom. The group combines two businesses that are unusual in this sector for being deliberately fused: Jet2.com (IATA code LS, ICAO code EXS), the UK's third-largest airline, and Jet2holidays, the UK's largest ATOL holder and leading provider of ATOL-protected package holidays to the Mediterranean, the Canary Islands and European city destinations. For the year ended 31 March 2026 the group reported revenue of £7,482.1 million, operating profit of £439.6 million and a record 20.83 million passengers, flying from 14 UK airport bases including newly added London Luton and London Gatwick, with more than 63% of flown passengers buying an end-to-end package holiday and 155 Airbus A321neo aircraft on order. Jet2holidays sells through its own website and through more than 2,500 independent UK travel agent partners, and carries ABTA number Y1256. Where Jet2 sits in the distribution chain is the point of this record. Like easyJet and Ryanair, Jet2.com was built with no Global Distribution System dependency at all: it never filed fares into the GDS rail that Amadeus, Sabre and Travelport have intermediated for forty years, and it therefore never needed IATA's New Distribution Capability as a remedy. Travelport supports Jet2 in Smartpoint only as a "Direct Payment Carrier" — its low-cost-carrier workaround — point-to-point only, no connecting flights, and with no post-booking change or cancellation possible through the GDS at all ("Requests for changes must be made directly through Jet2"). In June 2025 Jet2.com signed a distribution agreement with airline technology company Kyte, whose Kyte Direct Connect (KDC) JSON/REST API "standardises airline NDC and LCC proprietary content", opening Jet2 seats and ancillaries to travel management companies and corporate booking tools for the first time, with the same content reaching agency desktops through AirGateway. Separately, Jet2holidays operates an agency API that lets independent agents sell Jet2 packages on their own bookable websites for commission. Its API posture, stated honestly, is that Jet2 runs real production distribution APIs and publishes nothing about them. There is no developer portal — developer.jet2.com, developers.jet2.com, docs.jet2.com, apis.jet2.com, ndc.jet2.com, partner.jet2.com and trade.jet2.com all fail to resolve — no API reference, no OpenAPI, Swagger, AsyncAPI or GraphQL contract, no security.txt, no .well-known catalogue and no official GitHub organisation. api.jet2.com resolves and answers HTTP 200 with nothing but the stock Microsoft IIS 10.0 default page, 404 on every spec path probed. Access is by commercial agreement only, negotiated bilaterally or through Kyte, whose own FAQ states that "Access to airline products is controlled by each airline." This record is an honest stub: apis[] is intentionally empty because no Jet2 API is publicly documented, and listing an undocumented hostname as an API would be fabrication. The evidence, including every URL probed with its HTTP status, is in review.yml. A second enrichment pass on 28 July 2026 found the one genuinely public first-party developer surface Jet2 has, and it is not an API: the Jet2 Design System, published as two npm packages under the @jet2 scope (design tokens for seven brand themes, and a React component library containing a single Button), sourced from Jet2's private Azure DevOps organisation at jet2tfs.visualstudio.com/Jet2Digital and documented at design.jet2.com behind a Supernova login. Both packages were last published in April 2024. The same pass confirmed no /.well-known/ document on any host that answers, no security.txt, no vulnerability disclosure programme, no trust centre, no public Postman collection and no SDK in any package registry. Jet2's engineering voice, such as it is, comes from Jet2 Travel Technologies (J2TT), its in-house development centre in Pune, India, which runs a public blog with an RSS feed.

**Areas:** Travel · United Kingdom · Aviation · Airlines · Low Cost Carrier · Package Holidays · Tour Operator · Distribution · Booking · Ancillaries

## Jet2 on APIs.io

Everything profiled for Jet2 is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/jet2/](https://apis.io/providers/jet2/)** — or go straight to one of the APIs or properties below.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Jet2 Domain Security](https://apis.io/security/jet2/jet2-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.jet2.com/)
- [Blog](https://jet2traveltech.com/blogs)
- [Privacy policy](https://www.jet2plc.com/privacy)

## API Evangelist rating

**Kin Score 7.0** — minimal · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 55.4 |
| Contract quality | 0.0 |
| Contract governance | 0.0 |
| Operational transparency | 5.3 |
| Developer ergonomics | 2.4 |
| Access clarity | 10.5 |

**Agent readiness 0.0** — human-only

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 8.3** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/jet2/](https://apis.io/providers/jet2/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Jet2: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/jet2/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
