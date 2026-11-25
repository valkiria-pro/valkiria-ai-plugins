# Valkiria for AI assistants

Plugins and install instructions that connect an AI assistant to [Valkiria](https://valkiria.pro) - one workspace
for the ad accounts you run (Google Ads, Meta, TikTok, LinkedIn, Telegram Ads and more) with SMM, SEO and
app-store data.

The assistant talks to Valkiria's remote MCP server: **`https://valkiria.pro/mcp`** (Streamable HTTP, OAuth 2.1
with PKCE). You sign in with your Valkiria account in the browser; the assistant never sees your password or
your ad-platform tokens. Connected assistants can read and prepare drafts. Launching, resuming, budget changes
and deletion stay with you in the dashboard. You can revoke an assistant any time at
https://valkiria.pro/connect-ai/.

You need a Valkiria account with at least one ad account connected.

## Install

| Assistant | How |
| --- | --- |
| **Claude Code** (plugin with a skill) | `claude plugin marketplace add valkiria-pro/valkiria-ai-plugins` then `claude plugin install valkiria@valkiria` |
| Claude Code (server only) | `claude mcp add --transport http valkiria https://valkiria.pro/mcp` |
| **Claude.ai / Claude Desktop** | Settings -> Connectors -> Add custom connector -> `https://valkiria.pro/mcp` |
| **ChatGPT** | Settings -> Connectors -> Create (developer mode) -> MCP server URL `https://valkiria.pro/mcp`, OAuth |
| **Gemini CLI** | `gemini extensions install https://github.com/valkiria-pro/valkiria-ai-plugins` |
| **Codex CLI** | `codex mcp add valkiria --url https://valkiria.pro/mcp` then `codex mcp login valkiria` |
| **Cursor** | see [docs/cursor.md](docs/cursor.md), or `.cursor/mcp.json`: `{"mcpServers":{"valkiria":{"url":"https://valkiria.pro/mcp"}}}` |
| **VS Code / GitHub Copilot** | **MCP: Add Server** -> HTTP -> `https://valkiria.pro/mcp`, or `.vscode/mcp.json`: `{"servers":{"valkiria":{"type":"http","url":"https://valkiria.pro/mcp"}}}` |
| **Cline** | MCP Servers -> Configure: `{"mcpServers":{"valkiria":{"type":"streamableHttp","url":"https://valkiria.pro/mcp"}}}` (agents: [llms-install.md](llms-install.md)) |
| **Kimi Code CLI** | `/plugins install https://github.com/valkiria-pro/valkiria-ai-plugins` then `/reload` |
| Windsurf | `~/.codeium/windsurf/mcp_config.json`: `{"mcpServers":{"valkiria":{"serverUrl":"https://valkiria.pro/mcp"}}}` |
| Zed | `settings.json`: `{"context_servers":{"valkiria":{"url":"https://valkiria.pro/mcp"}}}` - Zed runs the OAuth sign-in itself |
| Goose | `goose configure` -> Add Extension -> Remote Extension (Streamable HTTP) -> `https://valkiria.pro/mcp`, or in `~/.config/goose/config.yaml`: `extensions: {valkiria: {type: streamable_http, name: valkiria, uri: "https://valkiria.pro/mcp", enabled: true, timeout: 300}}` |
| LM Studio (0.3.17+) | Program -> Install -> Edit `mcp.json`: `{"mcpServers":{"valkiria":{"url":"https://valkiria.pro/mcp"}}}` |
| Continue | `.continue/mcpServers/valkiria.yaml` with `type: streamable-http`, `url: https://valkiria.pro/mcp` and an `Authorization: Bearer vk_live_...` header (developer API key) |
| OpenClaw | `openclaw mcp add valkiria --url https://valkiria.pro/mcp --transport streamable-http` then `openclaw mcp login valkiria` |
| Perplexity (Mac app, Pro/Max) | Settings -> Connectors -> Add custom remote connector -> `https://valkiria.pro/mcp`, Streamable HTTP, OAuth |
| Manus | Connectors -> Add custom MCP -> by URL -> `https://valkiria.pro/mcp` |
| Any other MCP client | Streamable HTTP, URL `https://valkiria.pro/mcp`, OAuth discovery at `https://valkiria.pro/.well-known/oauth-protected-resource` |

## First prompt to try

> Call get_started, then audit the spend of my ad accounts for the last 30 days and show the top 3 money leaks in native currency.

## What is in this repository

- `.claude-plugin/marketplace.json`, `claude-code-plugin/` - Claude Code marketplace and plugin (MCP server + `valkiria-ads-ops` skill)
- `gemini-extension.json`, `GEMINI.md` - Gemini CLI extension
- `kimi.plugin.json` - Kimi Code CLI plugin
- `llms-install.md` - install instructions for agents (Cline marketplace)

## Links

Documentation: https://valkiria.pro/en/api-docs/ - Privacy: https://valkiria.pro/en/privacy/ -
Terms: https://valkiria.pro/en/terms/ - Support: support@valkiria.pro

Listed in the official MCP Registry as `pro.valkiria/valkiria`.

[![Valkiria MCP connector](https://glama.ai/mcp/connectors/pro.valkiria/valkiria/badges/score.svg)](https://glama.ai/mcp/connectors/pro.valkiria/valkiria)
[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/valkiria-pro/valkiria-ai-plugins)
