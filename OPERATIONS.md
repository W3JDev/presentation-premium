# OPERATIONS.md

## Purpose

This is the durable operating ledger for commitments, recurring responsibilities, and systemized follow-through.
Use it when something should not rely on short-term chat context.

## Capture Rules

When the user expresses any of the following, record it here or convert it into heartbeat/cron:
- recurring tasks
- standing responsibilities
- repeated reminders
- things to monitor regularly
- habits the assistant should enforce
- promises the assistant makes about future follow-through

## Current Standing Rules

- Do not rely on chat history alone for recurring intent.
- Convert repeated or durable intent into files or automation.
- Check before claiming, verify before answering, and write before forgetting.
- Push back on weak plans; do not agree just to be pleasant.

## Recurring Responsibilities

| Area | Responsibility | Mechanism | Status | Notes |
|---|---|---|---|---|
| Memory hygiene | Prevent forgetting, context loss, hallucination-by-assumption, stale bootstrap, and markdown bloat | HEARTBEAT + MEMORY.md + daily memory | Active | Established 2026-03-25 |
| Recurring intent capture | Turn repeated user intent into durable records or automation | HEARTBEAT review + manual updates + cron when justified | Active | Established 2026-03-25 |
| Schedule-aware operating | Use Jewel's actual night-owl / US-hours-aligned rhythm when deciding timing, reminders, quiet hours, and urgency | USER.md + MEMORY.md + HEARTBEAT.md | Active | Established 2026-03-25 |

## Open Items

- Build a compact recurring-task / promise review loop.
- Decide which recurring checks deserve cron instead of heartbeat.
- Set up scheduled maintenance cron jobs for memory/operations review and security/update audits.
- Move or reduce plaintext secrets in config where possible.

## Update Protocol

Whenever a new recurring obligation appears:
1. Decide whether it belongs in daily memory, long-term memory, heartbeat, cron, or this ledger.
2. Record it immediately.
3. If it needs timing, schedule it.
4. If it needs future review, add it to Open Items or Recurring Responsibilities.
