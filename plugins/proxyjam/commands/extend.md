---
# Generated file — do not edit by hand.
description: "Extend an order's subscription, with a preview before any charge."
argument-hint: "<order_id> [months]"
---

Extend a ProxyJam order with `extend_proxy_period`. If no order id is given, call `list_my_orders`, show the orders as a short table and ask which one to use; never guess an id. Call `get_order` to see its kind. A residential or datacenter proxy is extended by months (1-24; ask if not given). A mobile proxy is extended by one tariff option instead: show the options of the order's offer (find it with `list_offers`, kind mobile) and ask which one, then pass its tarification_index and no months. This spends the user's money. Generate one idempotency_key (a UUID4) and call the tool without confirm: that returns a dry-run preview and charges nothing. Show the preview — what is bought, the price, the payment method and the wallet balance — and ask the user to confirm. Only after an explicit yes, repeat the call with the same arguments, the same idempotency_key and confirm=True. If the user changes anything instead, preview again with a new key. Never retry a failed or timed-out call with a new key: the same key replays the stored result instead of charging twice. If the result contains a payment URL, show it.

Arguments: $ARGUMENTS

Expected: <order_id> [months]. Read order_id, months from that free-form text; anything it does not say counts as not given.
