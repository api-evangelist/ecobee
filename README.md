# ecobee (ecobee)

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
