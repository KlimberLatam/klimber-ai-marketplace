---
name: klimber
description: Use when the user asks to look up Klimber data: products, quotations, policies or claims.
---

# Klimber

Use the tools of the `klimber` MCP server. All of them are read-only.

1. Authentication is handled by the client in the browser. Never ask the user for a username or password in the chat, and never accept one if offered.
2. If a tool answers "Not authenticated" or "Session expired", tell the user to authenticate the `klimber` server again (Claude Code: `/mcp`; Codex: `codex mcp login klimber`) and sign in on the page that opens.
3. `list_products` lists the available catalog.
4. `get_quotation`, `get_policy`, `find_policies_by_id_number` and `get_policy_claims` query operations.
5. Never echo tokens or personal data back beyond what the user asked for.
