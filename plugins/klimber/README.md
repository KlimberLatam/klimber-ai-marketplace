# `klimber` plugin

Connects Claude Code and Codex to the Klimber MCP server (`https://mcp.klimber.com/mcp`).
Every tool is **read-only**.

## Install

### Claude Code

```
claude plugin marketplace add KlimberLatam/klimber-ai-marketplace
claude plugin install klimber@klimber-ai-marketplace
```

### Codex

```
codex plugin marketplace add KlimberLatam/klimber-ai-marketplace
codex plugin add klimber@klimber-ai-marketplace
```

## Sign in

| Tool | How |
|---|---|
| Claude Code | Open `/mcp`, select `klimber` and choose **Authenticate** |
| Codex | Run `codex mcp login klimber` |

Your browser opens a Klimber sign-in page. Type your credentials **there**, then go back to your assistant.

Your password is typed only on the Klimber page. It never passes through the assistant, the chat or the plugin.

## Tools

| Tool | What it does |
|---|---|
| `list_products` | Lists the available products |
| `get_quotation` | Gets a quotation by hash |
| `get_policy` | Gets policy details by id |
| `find_policies_by_id_number` | Finds a person's policies by national id and country |
| `get_policy_claims` | Gets the claims of a policy |

## Security

- Sign-in uses OAuth with PKCE. The assistant only receives a short-lived access token, never your password.
- The plugin does not store or read credentials on disk.
- Access tokens expire; when that happens you sign in again.

## Try it without installing

```
claude --plugin-dir ./plugins/klimber
```

## Troubleshooting

| Symptom | Fix |
|---|---|
| `Not authenticated` | Sign in again (see above). |
| `Session expired` | Your access expired; sign in again. |
| The sign-in page says invalid credentials | Check your username and password. |
| `The service is not reachable` | The backend is down; retry later. |
| `codex` is not recognized | Open the terminal from the Codex app or add it to your PATH. |
