# Valkiria plugin for Claude Code

Connects Claude Code to the Valkiria remote MCP server (https://valkiria.pro/mcp) and adds the
`valkiria-ads-ops` skill. Authentication is OAuth (browser prompt on first use) or a developer API key
(`vk_live_...`) as Bearer.

## Install

```bash
claude plugin marketplace add notformal/valkiria-ai-plugins      # the GitHub repo that holds .claude-plugin/marketplace.json
claude plugin install valkiria@valkiria
```

Without the marketplace:

```bash
claude mcp add --transport http valkiria https://valkiria.pro/mcp
```

## Layout

```
.claude-plugin/plugin.json      plugin manifest
.mcp.json                       remote MCP server (type http)
skills/valkiria-ads-ops/SKILL.md
```

Validate before publishing: `claude plugin validate ./claude-code-plugin`.

The public repo is assembled by `node scripts/mcp/build-plugins-repo.mjs <dir>`; its root holds `.claude-plugin/marketplace.json` so that
`claude plugin marketplace add` finds the plugin at `./claude-code-plugin`.
