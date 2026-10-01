# Whop ecommerce Grok Bots

Five Grok Bot templates that run a physical-goods store on Whop through the
Whop connector: build the store, migrate an existing catalog, run the ads, ship
every order, handle refunds and disputes. Nothing spends money, changes the
store, or contacts a customer without the owner's approval in chat.

| # | Bot | Job | Install |
| --- | --- | --- | --- |
| 1 | Ecom store builder | Products with shipping and tax, size and colour variants with stock and SKU, images, checkout links, storefront | coming |
| 2 | Store migrator | Shopify URL or product CSV to Whop products and variants, images included, with a redirect list | coming |
| 3 | Product ads | Launch Whop Ads for a product from its own gallery, daily triage with kill and scale rules, fixed daily cap | coming |
| 4 | Order desk | Hourly sweep of paid orders, pick list with addresses, shipments from tracking numbers, delivery tracking, low-stock alerts | coming |
| 5 | Customer care | Refunds by your written policy, dispute evidence from shipment tracking, weekly refund and dispute rates | coming |

Pairs with [Whop Economic Intelligence](https://x.ai/bot/M2ZLrLAUFFU0fFf6Aq28c)
for what to do next, and the [business starterpack](https://grok-bot-starterpack.whop.site)
for everything that is not ecommerce.

## How physical goods work on Whop, in one paragraph

A product carries `collect_shipping_address: true` and a tax category. Each
purchasable configuration (size, colour) is a variant with `attributes`,
`stock`, `sku`, and a one-time price. A paid order is a payment with
`shipping_address` and `line_items`. Fulfilment is a shipment attached to that
payment by tracking number; Whop detects the carrier and tracks delivery to the
door, with checkpoints. Refunds are issued against the payment. Disputes are
answered with the payment and the shipment's delivered checkpoint as evidence.
Every one of those is a tool in the Whop connector, and the bots call them by
name.

## Create a bot

1. In Grok Bot, open Marketplace and add the Whop connector. Sign in when asked.
2. New Bot, name it as the file says, paste the file's contents below the line as one message.
3. When it reports done, follow the first instruction at the top of the file.
4. Share → Create template → Public link.

Files are in `grok-bot/`, numbered in install order. `_shared-rules.md` is the
rule block every bot carries.

## What the bots cannot do, and say so

- Message a customer. Direct messages are Whop AI only. Customer care drafts replies for the owner to send.
- Ship a parcel. Order desk builds the pick list and records the tracking number you or your 3PL give it.
- Clone a theme. Store migrator moves the catalog; the website itself moves with Whop's "Clone an existing site" in the dashboard.

MIT.
