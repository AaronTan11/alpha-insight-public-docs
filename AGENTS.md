# Documentation project instructions

## About this project

- Public documentation for the Alpha Insight MCP server and API, built on
  [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter. Configuration lives in `docs.json`.
- The product code this documents lives in a separate, read-only monorepo. Never edit it from here.
- Every statement about behaviour, a field, a limit, or a URL must come from the product code or a
  live probe. When in doubt, leave it out and mark it `{/* TODO-OWNER */}`.

## Terminology

Use these words consistently:

- **wallet** — a Hyperliquid address. A wallet is looked up publicly; it is not the same as the
  signed-in account.
- **trader** — a person who trades. Use it for the human; use **wallet** for the address.
- **book** — the order book. Say "order book" in full on first use, "book" after.
- **watchlist** — a saved group of wallets.
- **permission** (not "scope") in user-facing prose; `data:read`, `trade:read`, `trade:write` are
  the permission names.

Say "tool" for a callable MCP/API tool, and "refusal" for an error result. Use "Alpha Insight" for
the product.

## Style preferences

- Use active voice and second person ("you").
- Keep sentences concise — one idea per sentence.
- Use sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Code formatting for file names, commands, paths, and code references.
- Never state a price.
- Product voice: we are the product. Write "Create a key in Settings", not "the system allows…".
- No internal names. Don't write "brick", "ORPC", "Privy", "Cloud Run", "ClickHouse", or "fold".
- Mark example values as examples. Never include a real user's data.
- Never put a real key, token, or password in a page. Never put a credential in a URL.

## Content boundaries

- Document only the public MCP server at `https://api.alphainsight.xyz/mcp` and the public tools.
- Never document `internal.*` or `admin.*` endpoints, or the web app's own RPC procedures.
- Never document not-yet-live surfaces: `/v1/*` REST routes, a streaming relay, trading through the
  API, or webhooks.
- Never invent a tool. There are 14, listed in `tools/overview.mdx`.
- TODO-OWNER items are for the product owner. Keep them as `{/* TODO-OWNER: … */}` and never resolve
  them yourself.

## Checks

Before finishing a change:

```bash
export PATH="$HOME/.bun/bin:$PATH"
mint broken-links
```

And confirm the site builds by running `mint dev` and loading the changed pages.
