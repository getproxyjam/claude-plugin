---
# Generated file — do not edit by hand.
description: "List my proxy orders, optionally filtered by status."
argument-hint: "[status]"
---

Show the user's ProxyJam orders. Call `list_my_orders`, passing status when it is given below. Present a compact table: order id, status, proxy kind and country, expiry date, auto-renew. If there are more pages, say so and offer to load the next one.

Arguments: $ARGUMENTS

Expected: [status]. Read status from that free-form text; anything it does not say counts as not given.
