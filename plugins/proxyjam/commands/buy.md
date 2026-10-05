---
# Generated file — do not edit by hand.
description: "Buy proxies from an offer, with a preview before any charge."
argument-hint: "<offer_id> [quantity] [period] [payment_method] [promo_code]"
---

Buy ProxyJam proxies with `create_proxy_order`. If no offer id is given, call `list_offers`, show the offers and ask which one to buy; never guess an id. Quantity defaults to 1 and the payment method to wallet. The period is chosen with tarification_index, the index into the offer's options; if no period is given, show the offer's options with their prices (`list_offers` lists them) and ask which one. This spends the user's money. Generate one idempotency_key (a UUID4) and call the tool without confirm: that returns a dry-run preview and charges nothing. Show the preview — what is bought, the price, the payment method and the wallet balance — and ask the user to confirm. Only after an explicit yes, repeat the call with the same arguments, the same idempotency_key and confirm=True. If the user changes anything instead, preview again with a new key. Never retry a failed or timed-out call with a new key: the same key replays the stored result instead of charging twice. If the result contains a payment URL, show it.

Arguments: $ARGUMENTS

Expected: <offer_id> [quantity] [period] [payment_method] [promo_code]. Read offer_id, quantity, period, payment_method, promo_code from that free-form text; anything it does not say counts as not given.
