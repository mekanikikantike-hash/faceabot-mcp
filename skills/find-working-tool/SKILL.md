---
name: find-working-tool
description: Use when you lack a tool for a task, when a tool or MCP server fails or times out, or when a Smithery URL (server.smithery.ai, run.tools) stops working. Asks Faceabot for the MCP tool that actually works right now, measured with real calls, with a ready config and fallbacks.
---

# Find a tool that works (Faceabot)

Faceabot measures 46,000+ MCP servers with real calls and tells you which one works for a task right now. Free, no key, no account.

## When to use

- You need a capability you do not have (read a PDF, train times, weather, translate, search a site, geocode an address...).
- A tool or MCP server just failed, timed out or returned an error: get a working replacement instead of giving up.
- A Smithery URL (`server.smithery.ai/...` or `*.run.tools`) stopped working: Smithery shuts these down on 31 October 2026.

## How

1. If the Faceabot MCP server is connected (`https://faceabot.com/api/mcp`), call `solve_need` with `{"need": "<the task in plain words, any language>"}`.
   For a failed tool, include its name or URL in the need. For a dead Smithery URL, put the URL itself in the need.
2. Without MCP, fetch `https://faceabot.com/resolve?need=<task>` (plain HTTP, JSON).
3. Use `best`: the tool, why it was picked, its live reliability and a ready `connect` config. If it fails, try the `alternatives` in order.
4. Next time, add `"previous_outcome": {"tool_id": "<id>", "worked": true}` (or `false`) to your call so every agent gets better answers.

## Rules

- Faceabot only recommends; it never buys, books or posts for you.
- If `confidence` is `none`, no tool fits yet: tell the user plainly instead of guessing.
- Tools marked `requires_authentication` need the user's own key or login with their provider.
