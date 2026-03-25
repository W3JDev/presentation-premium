# Composio Runner Contract

Last updated: 2026-03-25
Owner: Luffy
Status: pending-runtime-verification

## Purpose
Define how this host/runtime is expected to execute Composio-backed actions.

## Known evidence
- COMPOSIO_API_KEY exists in workspace `.env`
- Multiple Composio auth config IDs exist in workspace `.env`

## Current runtime findings
- local `composio` CLI not found
- local Python Composio SDK not found
- local Google API client libraries not found
- `mcporter` is installed at `/usr/local/bin/mcporter`, but currently has no MCP servers configured
- `gog` is installed at `/home/linuxbrew/.linuxbrew/bin/gog`

## Missing verification
- confirmed Composio MCP/server path for Google Drive/Gmail/Tasks
- minimum working command or tool route for Drive/Gmail/Tasks calls
- whether `gog` is authenticated and useful as a near-term runner/fallback inspection path

## Policy
Configured env keys are not treated as proof of live execution.
The Google pipeline remains blocked until one verified runner path is documented.
