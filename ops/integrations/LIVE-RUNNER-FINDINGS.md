# Live Runner Findings

Last updated: 2026-03-25
Owner: Luffy

## Verified local tooling
- `mcporter` present: `/usr/local/bin/mcporter`
- `gog` present: `/home/linuxbrew/.linuxbrew/bin/gog`

## Not present locally
- `composio` CLI: not found
- Python Composio SDK: not found
- Python Google API client libraries: not found

## Env evidence present
- Composio API key + org/project/user identifiers
- Composio Gmail/Drive/Calendar auth config IDs
- Gmail app-password entries

## Interpretation
The host has live Google/Composio-related credentials/config, but the obvious local runner is not a Composio SDK/CLI install.

Runtime results:
1. `mcporter` is installed, but currently reports **no MCP servers configured**.
2. `gog` is installed and exposes first-class commands for Gmail, Drive, Calendar, and Tasks.

Current best runner candidate:
- `gog` is the fastest verified local Google runner path.

Auth result:
- `gog status --json --no-input` reports no local credentials/config yet (`credentials_exists: false`, config missing)

## Immediate next actions
- authenticate `gog` if we choose it as the near-term Google runner
- or verify a different existing Google/Composio execution path
- keep Composio as the preferred long-term integration surface, but do not confuse configured env keys with live host access
