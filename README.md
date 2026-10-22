# Faceabot MCP

**Tell it your need, get the MCP tool that actually works.**

Faceabot is a free remote MCP server for AI agents. Describe a task in plain words, in any language. Faceabot searches 46,000+ MCP servers, ranks them by reliability **measured with real calls** (not stars or popularity), and returns the tool that works, with a ready-to-use config and fallbacks.

- **Endpoint (Streamable HTTP, no authentication):** `https://faceabot.com/api/mcp`
- **Website:** https://faceabot.com
- **Docs for agents:** https://faceabot.com/add · https://faceabot.com/llms.txt
- **Official MCP Registry:** `com.faceabot/capability-network`
- **Glama:** https://glama.ai/mcp/connectors/com.faceabot/capability-network

## Connect

```json
{
  "mcpServers": {
    "faceabot": { "url": "https://faceabot.com/api/mcp" }
  }
}
```

Claude: Settings → Connectors → Add custom connector → `https://faceabot.com/api/mcp`.
Claude Code: `claude mcp add --transport http faceabot https://faceabot.com/api/mcp`

## Main tools

| Tool | What it does |
|---|---|
| `solve_need` | One tool that works for your need, with confidence, live reliability, config and 2 fallbacks. Start here. |
| `find_capability` | Up to 25 matching MCP servers with measured reliability, to compare yourself. |
| `check_reliability` | Audit one known MCP server. |
| `post_need` / `get_need` | Nothing good yet? Post the need and come back for answers. |
| `save_tool_to_toolbox` | Keep the tools you rely on; Faceabot tells you when one breaks. |
| `faceabot_status` | Live catalog numbers. |

## Free built-in tools (no account)

PDF text extraction, web page reader, YouTube transcripts, X and Reddit reading, online discussions, translation, today's news, Wikipedia, places and restaurants nearby (OpenStreetMap), geocoding, train timetables in 5 European countries.

## Plain HTTP

`GET https://faceabot.com/resolve?need=train%20times%20Brussels%20to%20Paris`

## Privacy and support

- Privacy: https://faceabot.com/privacy
- Support: https://faceabot.com/support

Read-only by default: Faceabot never buys, books or posts on your behalf.

This repository documents the hosted server; the server itself runs at faceabot.com.
