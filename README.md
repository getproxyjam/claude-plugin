# ProxyJam for Claude Code

Buy and manage [ProxyJam](https://proxyjam.com) proxies without leaving Claude Code.
The plugin connects Claude Code to the hosted ProxyJam MCP server and adds slash commands
for the everyday tasks.

## Install

```text
/plugin marketplace add getproxyjam/claude-plugin
/plugin install proxyjam@proxyjam
```

Then run `/mcp`, pick **proxyjam** and sign in with your ProxyJam account in the browser.
No API key is needed.

## Commands

| Command | What it does |
|---|---|
| `/proxyjam:offers [kind] [country]` | Proxy offers on sale — `kind` is residential, datacenter or mobile |
| `/proxyjam:orders [status]` | Your orders |
| `/proxyjam:order <order_id>` | One order: connection details, expiry, 7-day traffic |
| `/proxyjam:balance` | Wallet balances |
| `/proxyjam:buy <offer_id> [quantity] [period] [payment_method] [promo_code]` | Buy proxies |
| `/proxyjam:extend <order_id> [months]` | Extend a subscription |
| `/proxyjam:bandwidth <order_id> <gb>` | Buy extra traffic for a residential or datacenter proxy |

Arguments are free-form: `/proxyjam:buy 12 x3 crypto` works. Anything missing is asked for —
an id is never guessed.

`buy`, `extend` and `bandwidth` start with a free preview showing the price and your balance,
and Claude asks for your confirmation before the paid call. A retried purchase reuses its
idempotency key, so a retry does not charge twice.

Everything else the MCP server can do (IP whitelist, protocol, auto-renew, transactions …)
works by just asking Claude.

## Other MCP clients

The same commands are served as MCP prompts by `https://proxyjam.com/mcp`, so Claude
Desktop, Cursor and other clients list them too. See the
[MCP documentation](https://docs.proxyjam.com/mcp-server).

## License

MIT
