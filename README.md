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
| `get_verdict(symbol)` | Today's research verdict for a coin (e.g. `BTC`, `ETH`, `SOL`): stance, graded dimensions (technical · sentiment · funding · KOL), key support/resistance, invalidation, risks, and a link to the full dossier. |
| `list_coins()` | Every coin symbol covered by a daily verdict (100 major assets). Use it to discover which symbols the other tools accept. |
| `get_track_record(symbol)` | The **settled** track record for a coin — CoinVerdict's differentiator. Every past daily verdict is scored 7 days later against BTC (win / loss / push). Returns the coin's W/L/P scoreboard plus recent settled calls. |
| `get_receipts()` | The overall settled scoreboard across all coins: directional win rate, wins/losses/pushes, neutral count, and the settlement rule. The public accountability record. |
| `get_market_overview()` | Today's verdict for **all** covered coins in one call — the full docket: each coin's current stance and headline. |
| `get_kol_leaderboard()` | The KOL settlement leaderboard: crypto influencers ranked by their **settled** hit rate (from VeraMind's ledger), with sample size. |

## Example

> "What's CoinVerdict's take on BTC today?"

The assistant calls `get_verdict("BTC")` and gets a compact JSON verdict with a link to the full dossier at [coinverdict.io/coin/BTC](https://coinverdict.io/coin/BTC).

## Notes

- **Free, read-only, no API key.** Verdicts are pre-generated daily and served from cache.
- Research information, **not investment advice**.
- Full dossiers (bull/bear cross-examination, risk committee ruling, KOL settlement records, charts): [coinverdict.io](https://coinverdict.io) · 中文版: [coinverdict.io/zh](https://coinverdict.io/zh)
- Community: [Telegram channel](https://t.me/CoinVerDict) · [chat](https://t.me/CoinVerDict_Chat)
