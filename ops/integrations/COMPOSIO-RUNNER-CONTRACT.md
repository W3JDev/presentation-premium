# Composio Runner Contract

Last updated: 2026-03-25
Owner: Luffy
Status: pending-runtime-verification

## Purpose
Define how this host/runtime is expected to execute Composio-backed actions.

## Known evidence
- COMPOSIO_API_KEY exists in workspace `.env`
- Multiple Composio auth config IDs exist in workspace `.env`

## Missing verification
- confirmed local SDK path
- confirmed CLI path
- confirmed MCP/server path for this runtime
- minimum working command or tool route for Drive/Gmail/Tasks calls

## Policy
Configured env keys are not treated as proof of live execution.
The Google pipeline remains blocked until one verified runner path is documented.
