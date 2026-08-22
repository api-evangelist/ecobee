# ecobee (ecobee)

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

ecobee makes smart Wi-Fi thermostats, room sensors, cameras, and other connected home devices. The ecobee API is a REST-like JSON interface, based at `https://api.ecobee.com/1/`, that lets authorized third-party applications read and control registered ecobee thermostats - retrieving live runtime state, settings, sensors, and equipment status, updating programs and comfort settings via thermostat functions, pulling historical runtime and meter reports, grouping thermostats, and (for EMS and Utility accounts) organizing thermostats in a management-set hierarchy and issuing demand response events. Authorization uses OAuth 2.0 with an ecobee PIN flow or the standard authorization-code flow, plus refresh tokens.

> **Developer program status:** As of late 2024, ecobee closed its consumer developer program to **new** API-key registrations. Existing API keys continue to function, and the underlying v1 API remains documented and operational. EMS/Utility (commercial energy) access is arranged directly with ecobee. This descriptor documents the API honestly as real but with restricted new onboarding.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ecobee/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ecobee/refs/heads/main/apis.yml)

## Tags

- Smart Home
- Thermostat
- IoT
- HVAC
- Energy
- Home Automation
- Demand Response

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### ecobee Thermostat API

Retrieve registered ecobee thermostats and their selectable data (runtime state, settings, program, events, alerts, remote sensors, equipment status) via `GET /thermostat`, and poll for changes efficiently with `GET /thermostatSummary`.

- **Human URL:** [get-thermostats](https://www.ecobee.com/home/developer/api/documentation/v1/operations/get-thermostats.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Thermostat Update and Functions API

Update writable thermostat properties and run thermostat functions via `POST /thermostat` - set holds and comfort settings, resume program, send messages, control fan/vents. Requires the `smartWrite` scope.

- **Human URL:** [post-update-thermostats](https://www.ecobee.com/home/developer/api/documentation/v1/operations/post-update-thermostats.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Runtime Report API

Pull historical five-minute-interval runtime data for a set of thermostats via `GET /runtimeReport`. Limited to 25 thermostats and a 31-day window per request.

- **Human URL:** [get-runtime-report](https://www.ecobee.com/home/developer/api/documentation/v1/operations/get-runtime-report.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Group API

Retrieve (`GET /group`) and update (`POST /group`) the grouping data for the thermostats registered to a user. Smart accounts only.

- **Human URL:** [get-group](https://www.ecobee.com/home/developer/api/documentation/v1/operations/get-group.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Demand Response API

Issue, list, and cancel Demand Response events against a set of thermostats via `/demandResponse`. Utility accounts only.

- **Human URL:** [post-issue-demand-response](https://www.ecobee.com/home/developer/api/documentation/v1/operations/post-issue-demand-response.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Hierarchy API

Organize EMS and Utility fleets in a management-set hierarchy - register/unregister/move/assign thermostats (`/hierarchy/thermostat`), manage management sets (`/hierarchy/set`), and manage users (`/hierarchy/user`). EMS and Utility accounts only.

- **Human URL:** [getting-started-management-set-hierarchy](https://www.ecobee.com/home/developer/api/documentation/v1/operations/hierarchy/getting-started-management-set-hierarchy.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Meter Report API

Retrieve meter reading history (energy / metering data) for a set of thermostats via `GET /meterReport`. EMS and Utility accounts.

- **Human URL:** [operations-intro](https://www.ecobee.com/home/developer/api/documentation/v1/operations/operations-intro.shtml)
- **Base URL:** `https://api.ecobee.com/1`

### ecobee Authorization API

OAuth 2.0 authorization. `GET /authorize` starts the ecobee PIN flow (`response_type=ecobeePin`) or the authorization-code flow; `POST /token` exchanges an authorization code and refreshes expired access tokens. Scopes: `smartRead`, `smartWrite`, `ems`.

- **Human URL:** [auth-intro](https://www.ecobee.com/home/developer/api/documentation/v1/auth/auth-intro.shtml)
- **Base URL:** `https://api.ecobee.com`

## Common Properties

- [GitHub Organization](https://github.com/ecobee)
- [LinkedIn](https://www.linkedin.com/company/ecobee)
- [Website](https://www.ecobee.com)
- [Documentation](https://www.ecobee.com/home/developer/api/introduction/index.shtml)
- [Plans](plans/ecobee-plans-pricing.yml)
- [Rate Limits](rate-limits/ecobee-rate-limits.yml)
- [Fin Ops](finops/ecobee-finops.yml)

## Artifacts

- **OpenAPI:** [openapi/ecobee-openapi.yml](openapi/ecobee-openapi.yml)
- **Postman Collection:** [collections/ecobee.postman_collection.json](collections/ecobee.postman_collection.json)
- **Open Collection:** [collections/ecobee.opencollection.json](collections/ecobee.opencollection.json)
- **Review:** [review.yml](review.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
