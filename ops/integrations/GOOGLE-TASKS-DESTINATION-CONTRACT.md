# Google Tasks Destination Contract

Last updated: 2026-03-25
Owner: Luffy
Status: missing-destination

## Purpose
Define the exact Google Tasks destination for meeting-note action items.

## Required fields
- target account
- target task list ID or equivalent stable destination identifier
- task naming/dedupe rules

## Current state
No verified Google Tasks destination identifier is documented yet.
- `gog` is installed and supports task-list inspection, but is currently not authenticated on this host.

## Policy
The poller must not create tasks until the destination contract is verified.
