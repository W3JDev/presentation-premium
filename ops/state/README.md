# Ops State

This folder stores durable state for automations.

Examples:
- last processed transcript IDs
- dedupe markers for task creation
- last successful run metadata
- mail triage checkpoints

Rules:
- machine-readable first
- no unnecessary secret duplication
- state files should support restart-safe automation
