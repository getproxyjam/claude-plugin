---
# Generated file — do not edit by hand.
description: "Show one order: its proxy, credentials, expiry and 7-day traffic."
argument-hint: "<order_id>"
---

Show one ProxyJam order in full. If no order id is given, call `list_my_orders`, show the orders as a short table and ask which one to use; never guess an id. Call `get_order` and `get_order_traffic` for it. Show the status, the proxy connection details (host, port, protocol, credentials), the expiry date, auto-renew, the IP whitelist and the traffic used over the last 7 days. If the order is close to expiry or out of traffic, mention that it can be extended or topped up.

Arguments: $ARGUMENTS

Expected: <order_id>. Read order_id from that free-form text; anything it does not say counts as not given.
