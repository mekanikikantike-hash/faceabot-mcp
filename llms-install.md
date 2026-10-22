# Installing Faceabot (for AI agents such as Cline)

Faceabot is a **remote** MCP server. Nothing to clone, build or install, and no API key.

Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "faceabot": {
      "type": "streamableHttp",
      "url": "https://faceabot.com/api/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

Then check it works by calling the tool `faceabot_status` (it returns live catalog numbers), or `solve_need` with `{"need": "weather forecast"}`.

If the client only supports local (stdio) servers, use the bridge:

```json
{
  "mcpServers": {
    "faceabot": { "command": "npx", "args": ["-y", "mcp-remote", "https://faceabot.com/api/mcp"] }
  }
}
```
