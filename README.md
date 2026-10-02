# Klimber AI Marketplace

Official plugin marketplace by **Klimber** for [Claude Code](https://claude.com/claude-code) and [Codex](https://openai.com/codex).
Bring Klimber into your AI assistant: query products, quotations, policies and claims in natural language, read-only and secure.

![Plugins](https://img.shields.io/badge/plugins-1-blue)
![Works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Codex-black)
![Access](https://img.shields.io/badge/access-read--only-green)

## Quick start

Pick your tool. You only install once.

### Claude Code

```
claude plugin marketplace add KlimberLatam/klimber-ai-marketplace
claude plugin install klimber@klimber-ai-marketplace
```

Restart Claude Code, type `/mcp`, select `klimber` and choose **Authenticate**.

### Codex

```
codex plugin marketplace add KlimberLatam/klimber-ai-marketplace
codex plugin add klimber@klimber-ai-marketplace
```

Restart Codex and sign in with `codex mcp login klimber`.

In both tools you sign in on a Klimber page in your browser; your password never goes through the assistant. Then ask, for example:

> *"What products does Klimber offer?"*

You need a Klimber user account.

## Available plugins

| Plugin | What it does | Version |
|---|---|---|
| [`klimber`](plugins/klimber) | Query Klimber: products, quotations, policies and claims. Read-only. | 0.2.0 |

## How it works

```
Claude Code ┐
            ├─>  klimber plugin  ->  mcp.klimber.com/mcp
Codex       ┘    (skill + MCP)        (Klimber MCP server)
```

One plugin, one MCP server, two tools. The plugin bundles a skill and a remote [MCP](https://modelcontextprotocol.io) connection. Sign-in uses OAuth with PKCE: the assistant receives a short-lived access token, never your password.

## Repository layout

```
.claude-plugin/marketplace.json      Claude Code catalog
.agents/plugins/marketplace.json     Codex catalog
plugins/<plugin>/
  .claude-plugin/plugin.json         Claude Code manifest
  .codex-plugin/plugin.json          Codex manifest
  .mcp.json                          MCP server (shared by both)
  skills/                            skills (shared by both)
  README.md                          plugin documentation
.github/                             issue and PR templates
```

The MCP server and the skills are shared, so a change to a tool is made once, in the server. The two manifests only carry metadata and must keep the same version.

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) first.
To report a vulnerability, follow [SECURITY.md](SECURITY.md) and do not open a public issue.

## License

See [LICENSE](LICENSE).
