---
# Generated file — do not edit by hand.
description: "Buy extra traffic for a residential or datacenter proxy, with a preview."
argument-hint: "<order_id> <gb>"
---

Buy extra traffic for a ProxyJam order with `buy_proxy_bandwidth`. If no order id is given, call `list_my_orders`, show the orders as a short table and ask which one to use; never guess an id. Call `get_order` and check it is a residential or datacenter proxy: mobile proxies cannot be topped up this way, so say so and stop. If the amount of GB is not given, call `get_order_traffic`, show the traffic used so far and ask how much to add. This spends the user's money. Generate one idempotency_key (a UUID4) and call the tool without confirm: that returns a dry-run preview and charges nothing. Show the preview — what is bought, the price, the payment method and the wallet balance — and ask the user to confirm. Only after an explicit yes, repeat the call with the same arguments, the same idempotency_key and confirm=True. If the user changes anything instead, preview again with a new key. Never retry a failed or timed-out call with a new key: the same key replays the stored result instead of charging twice. If the result contains a payment URL, show it.

Arguments: $ARGUMENTS

Expected: <order_id> <gb>. Read order_id, gb from that free-form text; anything it does not say counts as not given.
