# Changelog

Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). Versioning follows [SemVer](https://semver.org/).

## [0.2.0]

### Added
- `klimber-ai-marketplace` marketplace with the `klimber` plugin.
- Remote MCP server with 5 read-only tools: `list_products`, `get_quotation`, `get_policy`, `find_policies_by_id_number`, `get_policy_claims`.
- Codex support: the same plugin, MCP server and skills now install from Codex too.
- Browser sign-in with OAuth and PKCE: the password is typed on a Klimber page and never goes through the assistant.
- Repository documentation and issue/PR templates.
