# Prixtel

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

Prixtel is a French mobile virtual network operator (MVNO) founded in 2004 by David Charles and
headquartered in Aix-en-Provence. It is known for *forfaits flexibles* — mobile plans whose monthly
price moves automatically between published tiers according to the data a subscriber actually
consumed, with the ceiling known in advance — and it rides the SFR (historically also Orange) radio
network rather than owning spectrum. Prixtel serves roughly 300,000 to 500,000 subscribers and was
acquired by Altice France, the owner of SFR, in June 2021 for approximately €415M, continuing to
trade under its own brand.

## Why this profile is thin

**Prixtel has no developer program.** It publishes no API, no developer portal, no SDK, no webhook
catalog, and no machine-readable contract of any kind. Contract discovery was run in full against
every live Prixtel host — `www.prixtel.com`, `prixtel.com`, `api.prixtel.com`, `pro.prixtel.com`,
`assistance.prixtel.com`, `espaceclient.prixtel.com`, `tunnel.prixtel.com` — covering OpenAPI/Swagger
paths, GraphQL introspection surfaces, MCP endpoints, A2A agent cards at both the canonical and
legacy well-known paths, and `llms.txt`. Every probe missed.

`api.prixtel.com` does resolve and is a live nginx origin — it is the private backend for the Prixtel
iOS/Android app — but it answers HTTP 404 on its own root and on every path probed. It is not a
documented, credentialed, or supported integration surface. `robots.txt` disallows `/ws-externe/`,
the only path on the estate whose name implies a machine interface; it was not probed, because API
Evangelist honors `robots.txt`.

Prixtel also has no GitHub organization (`api.github.com/orgs/prixtel` → 404) and no first-party
package in any of the nine registries swept. Its only first-party software distribution is an
end-user mobile app.

This is an honest zero, not a failed pass. See the `x-coverage` block in `apis.yml`.

## What is in this repository

| Path | What it records |
|---|---|
| `apis.yml` | APIs.json 0.20 profile, identity properties, and the `x-coverage` explanation |
| `well-known/prixtel-well-known.yml` | `/.well-known/` probe across seven hosts — every path missed |
| `packages/prixtel-packages.yml` | Nine-registry sweep; zero first-party packages, third-party finds labelled |
| `plans/prixtel-plans-pricing.yml` | `plan_count: 0` — consumer mobile tariffs are not API plans |
| `rate-limits/prixtel-rate-limits.yml` | `limit_count: 0` |
| `security/prixtel-domain-security.yml` | Probed TLS / HSTS / DNSSEC / CAA / SPF / DMARC |
| `llms/prixtel-llms.txt` | Generated agent-facing index of the public Prixtel surface |

Source: portfolio company of [serena](https://github.com/api-evangelist/serena) (a realized exit —
Altice France acquired Prixtel in 2021) — https://www.prixtel.com/
