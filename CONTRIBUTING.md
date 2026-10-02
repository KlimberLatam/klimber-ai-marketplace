# Contributing

Thanks for helping improve the Klimber AI Marketplace.

## Workflow

1. Create a branch from `main`: `feat/<topic>`, `fix/<topic>` or `docs/<topic>`.
2. Make your change and test it locally: `claude --plugin-dir ./plugins/<plugin>` or add the folder as a Codex marketplace with `codex plugin marketplace add .`.
3. Validate: `claude plugin validate . --strict`.
4. Open a Pull Request. `main` is protected: it requires a PR and one approval.

## Commits

Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `docs:`, `chore:`, `ci:`, `refactor:`.

## Plugin rules

- **No secrets in the repo**: no tokens, keys, passwords or connection strings. A remote MCP server authenticates with OAuth or `headersHelper`. An environment variable containing `TOKEN`, `KEY` or `SECRET` in the `.mcp.json` of a remote server is read as empty.
- **Read-only by default.** A tool that modifies data needs a justification in the PR and an explicit confirmation step in its skill.
- Every user-visible change bumps the version in the three places that carry it (`.claude-plugin/plugin.json`, `.codex-plugin/plugin.json` and the Claude catalog) using semver, and is recorded in [CHANGELOG.md](CHANGELOG.md).
- Every plugin ships its own `README.md` with install steps, tools and security notes.
- Plugin, skill and folder names use `kebab-case`.
- Everything in this repository is written in English.

## Adding a plugin

1. Copy `plugins/klimber` as a starting point to `plugins/<new-plugin>`.
2. Adjust `plugin.json`, `.mcp.json`, `skills/` and `README.md`.
3. Register it in `.claude-plugin/marketplace.json` and `.agents/plugins/marketplace.json`.
