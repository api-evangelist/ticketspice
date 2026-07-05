# TicketSpice (ticketspice)

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
