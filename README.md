# TicketSpice (ticketspice)

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

TicketSpice is an online event ticketing platform built by [Webconnex](https://www.webconnex.com) that lets organizers design fully customizable ticketing pages and sell tickets for events, festivals, tours, and immersive experiences at a flat 99-cent per-ticket fee. TicketSpice is one of several Webconnex products (alongside RegFox, RedPodium, and GivingFuel) that share a single REST API.

TicketSpice's programmable surface is the **shared Webconnex v2 Public REST API** (base `https://api.webconnex.com/v2/public`). Callers select the TicketSpice product with a `product=ticketspice` query parameter and authenticate with an `apiKey` request header. The API is request/response REST over HTTPS: GET search-and-view endpoints for orders, registrants, tickets, subscriptions, transactions, customers, forms, and inventory; write operations for coupons and webhooks; and registrant check-in/check-out. The only push mechanism is outbound webhooks (HTTP callbacks) - there is no public WebSocket API.

**Access model:** The API is real and documented at [docs.webconnex.io/api/v2](https://docs.webconnex.io/api/v2/), but access is provisioned per account. An organizer generates an API key from the dashboard, and API access is gated to higher-tier plans (RegFox documents this as Premium/Professional; TicketSpice documents API access on Enterprise-tier packages). The endpoints below are transcribed from the public reference and are real; a live account and key are required to exercise them.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ticketspice/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ticketspice/refs/heads/main/apis.yml)

## Tags

- Event Ticketing
- Ticketing
- Events
- Registration
- Payments
- Webconnex

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

All APIs share the base URL `https://api.webconnex.com/v2/public`, the `apiKey` header, and the `product=ticketspice` parameter.

### TicketSpice Forms and Inventory API

List and view the ticketing forms (event pages) in a TicketSpice account and read their remaining ticket and product inventory.

- **Human URL:** [https://docs.webconnex.io/api/v2/](https://docs.webconnex.io/api/v2/)
- **Base URL:** `https://api.webconnex.com/v2/public`

### TicketSpice Orders and Registrants API

Search and view ticket orders and the registrants (ticket buyers/attendees) within them, and check registrants in or out at the door.

- **Human URL:** [https://docs.webconnex.io/api/v2/](https://docs.webconnex.io/api/v2/)
- **Base URL:** `https://api.webconnex.com/v2/public`

### TicketSpice Tickets API

Search and view individual issued tickets across a TicketSpice account.

- **Human URL:** [https://docs.webconnex.io/api/v2/](https://docs.webconnex.io/api/v2/)
- **Base URL:** `https://api.webconnex.com/v2/public`

### TicketSpice Transactions and Customers API

Search and view financial transactions (payments, refunds) and the customer records tied to them.

- **Human URL:** [https://docs.webconnex.io/api/v2/](https://docs.webconnex.io/api/v2/)
- **Base URL:** `https://api.webconnex.com/v2/public`

### TicketSpice Coupons API

Full read-write management of discount coupons - list global or per-form coupons and create, view, update, and delete individual coupons.

- **Human URL:** [https://docs.webconnex.io/api/v2/](https://docs.webconnex.io/api/v2/)
- **Base URL:** `https://api.webconnex.com/v2/public`

### TicketSpice Webhooks API

Programmatically manage outbound webhooks - create, list, view, update, and delete subscriptions, inspect delivery logs, and resend a prior delivery. Webhooks fire on events such as new registration, subscription/deposit processed, form publish, inventory thresholds, and coupon changes.

- **Human URL:** [https://help.ticketspice.com/en/articles/2471509-webhooks](https://help.ticketspice.com/en/articles/2471509-webhooks)
- **Base URL:** `https://api.webconnex.com/v2/public`

## Pricing

TicketSpice charges a flat **$0.99 per paid ticket** ($5+), **$0.49** for paid tickets under $5 or box-office card sales, no fee for cash box-office sales, and $0.99 per free-event ticket (waived with prior paid-event history). Card processing is **2.9% + $0.30** via Webconnex Payments, or a **1%** platform fee plus the processor's own fees for a custom processor. No setup fees, monthly fees, or contracts. See [plans/ticketspice-plans-pricing.yml](plans/ticketspice-plans-pricing.yml).

## Rate Limits

The shared Webconnex API enforces per-account limits: **10,000 requests/day** (reset 00:00 UTC) and **900 requests per 15-minute** burst window, with remaining capacity in `X-Daily-Remaining` / `X-Burst-Remaining` headers and HTTP 429 on overage. Search endpoints page with a `startingAfter` cursor and `limit` (default 50). See [rate-limits/ticketspice-rate-limits.yml](rate-limits/ticketspice-rate-limits.yml).

## Common Properties

- [GitHub Organization](https://github.com/webconnex)
- [LinkedIn](https://www.linkedin.com/company/webconnex)
- [Website](https://www.ticketspice.com)
- [Documentation](https://docs.webconnex.io/api/v2/)
- [Plans](plans/ticketspice-plans-pricing.yml)
- [Rate Limits](rate-limits/ticketspice-rate-limits.yml)
- [Fin Ops](finops/ticketspice-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
