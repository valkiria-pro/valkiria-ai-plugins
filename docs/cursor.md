# Valkiria in Cursor

One-click install (paste in the browser address bar or use as a link):

```
cursor://anysphere.cursor-deeplink/mcp/install?name=valkiria&config=eyJ1cmwiOiJodHRwczovL3ZhbGtpcmlhLnByby9tY3AifQ==
```

Markdown button for a README:

```markdown
[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](cursor://anysphere.cursor-deeplink/mcp/install?name=valkiria&config=eyJ1cmwiOiJodHRwczovL3ZhbGtpcmlhLnByby9tY3AifQ==)
```

Manual: `~/.cursor/mcp.json` (global) or `.cursor/mcp.json` (project):

```json
{
  "mcpServers": {
    "valkiria": { "url": "https://valkiria.pro/mcp" }
  }
}
```

Cursor opens the OAuth login on first use; a `vk_live_...` developer key can be passed instead via
`"headers": { "Authorization": "Bearer vk_live_..." }`.

The `config` value is base64 of `{"url":"https://valkiria.pro/mcp"}`; regenerate with
`node scripts/mcp/make-install-links.mjs` from the Valkiria repo.
