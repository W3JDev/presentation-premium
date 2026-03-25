# Google Drive Source Contract

Last updated: 2026-03-25
Owner: Luffy
Status: missing-identifiers

## Purpose
Define the exact Google Drive transcript/meeting-note sources the poller is allowed to inspect.

## Required fields
- source type (folder/shared drive/query)
- folder IDs or shared drive IDs
- filename/query rules for transcript detection
- whether "Team Meetings" and "Meet Recordings" are folder names only or mapped to specific IDs

## Current state
No verified folder IDs, shared drive IDs, or query rules are documented yet.
- `gog` is installed and supports Drive/shared-drive listing, but is currently not authenticated on this host.

## Policy
The poller must not guess source identifiers.
