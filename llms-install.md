# Installing the Valkiria MCP server (instructions for an AI agent)

Valkiria is a remote MCP server. There is nothing to download, build or run locally.

- Transport: Streamable HTTP
- URL: `https://valkiria.pro/mcp`
- Auth: OAuth 2.1 with PKCE (the client opens a browser sign-in on first use). No API key is required.
  Optional alternative: a developer key `vk_live_...` sent as `Authorization: Bearer <key>`.

## Cline

Add to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "valkiria": { "type": "streamableHttp", "url": "https://valkiria.pro/mcp" }
  }
}
```

Then ask the user to complete the browser sign-in with their Valkiria account. The user needs an existing
account at https://valkiria.pro with at least one ad account connected.

## Check

Call the `get_started` tool. It returns who is connected, the granted scopes and how many ad platforms are linked.

## What the server will not do

Launching or resuming a campaign, changing a budget and deleting campaigns or rules are refused for connected
assistants; the account owner does these in the Valkiria dashboard.
