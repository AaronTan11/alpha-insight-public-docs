# Alpha Insight public docs

Public documentation for the Alpha Insight MCP server and API, built with
[Mintlify](https://mintlify.com). It documents the public MCP server at
`https://api.alphainsight.xyz/mcp` and nothing else.

## Structure

- `docs.json` — site configuration and navigation.
- `index.mdx`, `quickstart.mdx` — landing page and first-call guide.
- `connect/` — client setup (claude.ai, Claude Code, Claude Desktop, Cursor and VS Code, plain HTTP).
- `auth/` — API keys, OAuth, and permissions.
- `tools/` — the 14 read-only tools, one page each, plus the overview.
- `limits.mdx`, `errors.mdx`, `changelog.mdx` — reference.

## Preview

Install the [Mintlify CLI](https://www.npmjs.com/package/mint), then run this
from the repository root (where `docs.json` lives):

```bash
mint dev
```

The preview is served at `http://localhost:3000`.

## Checks

```bash
mint validate
mint broken-links
```

## Editing rules

See `AGENTS.md`. Every statement about behaviour, a field, a limit, or a URL
must come from the product code or a live probe.
