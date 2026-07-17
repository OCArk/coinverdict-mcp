# CoinVerdict MCP Server

Free remote [MCP](https://modelcontextprotocol.io) server for [CoinVerdict](https://coinverdict.io) — AI crypto research verdicts, refreshed daily.

An AI analyst panel debates each major coin every day and issues a graded research verdict: stance (overweight / neutral / underweight), graded dimensions (technical · sentiment · funding · KOL consensus), key levels, and risk framing. This server gives AI assistants direct read access to today's verdicts.

**Endpoint (Streamable HTTP, no auth):**

```
https://mcp.coinverdict.io/mcp
```

## Install

**Claude Code**

```bash
claude mcp add --transport http coinverdict https://mcp.coinverdict.io/mcp
```

**Cursor / other MCP clients** — add a remote server with the URL above (transport: `http` / `streamable-http`).

## Tools

| Tool | Description |
|---|---|
| `get_verdict(symbol)` | Today's research verdict for a coin (e.g. `BTC`, `ETH`, `SOL`): stance, graded dimensions, key support/resistance, invalidation, risks, and a link to the full dossier. |
| `list_coins()` | All coins covered by daily verdicts (67+). |

## Example

> "What's CoinVerdict's take on BTC today?"

The assistant calls `get_verdict("BTC")` and gets a compact JSON verdict with a link to the full dossier at [coinverdict.io/coin/BTC](https://coinverdict.io/coin/BTC).

## Notes

- **Free, read-only, no API key.** Verdicts are pre-generated daily and served from cache.
- Research information, **not investment advice**.
- Full dossiers (bull/bear cross-examination, risk committee ruling, KOL settlement records, charts): [coinverdict.io](https://coinverdict.io) · 中文版: [coinverdict.io/zh](https://coinverdict.io/zh)
- Community: [Telegram channel](https://t.me/CoinVerDict) · [chat](https://t.me/CoinVerDict_Chat)
