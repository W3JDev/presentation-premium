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

## Session Priorities — W3J Ops (Effective 2026-03-25)

### Priority 1 — Multi-Agent Automation & Cron Infrastructure

**Mission:** Fully operationalize the 3-Agent Daily Loop and harden all scheduled jobs against silent failure.

**3-Agent Loop (session boot target: 22:00 MYT)**
- **MailTriage** — classify unread emails and draft replies; never send without explicit Jewel approval.
- **TaskBoard** — pull active tasks, flag overdue items, and select today's 3 MITs using this hierarchy: Revenue Blocker → Bold Business deliverable → W3J product.
- **Ops Chief** — read MailTriage + TaskBoard output and produce a Session Briefing of 300 words or less that includes: urgent mail summary, 3 MITs, and one actionable Ops Note.

**Cron Safeguard Requirements (mandatory)**
- Use absolute paths for Node and all scripts.
- Run under the correct user context (`w3jdev`).
- Redirect all output to job-specific log files.
- Verify every cron after creation with a live execution check. Configured ≠ running.

### Priority 2 — Bold Business Automations

**Mission:** Build and maintain two automated pipelines for Bold Business operational continuity.

**2A — QuickBooks Time (TSheets) Clock Automation**
- Browser automation for clock-in / clock-out via session persistence.
- Must handle 2FA properly; never assume an active session without verification.
- Mon–Fri MYT schedule:
  - 20:00 → Clock In
  - 00:00 → Break Start
  - 01:00 → Break End
  - 17:00 → Clock Out

**2B — Google Drive Meeting Notes Pipeline**
- Poll Google Drive folders: `Team Meetings` and `Meet Recordings`.
- Run 7× per night from 20:45 to 05:00 MYT, roughly every 60–75 minutes.
- On new transcript detected: extract AI action items and push to Google Tasks.
- Deduplication required: never create a task that already exists.
- Use Composio MCP for Google Workspace calls; do not silently fall back to Maton API gateways.

### Priority 3 — Content Engine: LinkedIn Growth + Bijou Blog

**Mission:** Maintain consistent content output for W3J brand growth.
- Build and run a daily LinkedIn post generation pipeline.
- Draft one daily personalized Bijou blog post to `w3jdev.github.io/bijou-blog/`, written from Bijou's perspective.

## Current Standing Rules

- Do not rely on chat history alone for recurring intent.
- Convert repeated or durable intent into files or automation.
- Check before claiming, verify before answering, and write before forgetting.
- Push back on weak plans; do not agree just to be pleasant.
- Interrupt immediately for revenue blockers, emails marked Urgent or NDA, and anything requiring Jewel's explicit approval.
- Respect proactive ping window: 22:00–06:00 MYT only unless something truly urgent crosses the threshold above.
- Priority hierarchy is always: Revenue Blocker > Bold Business > W3J Product.
- Never claim success without verification: check logs, confirm the process ran, and confirm the result exists.
- Default to Composio MCP for Google Workspace and social/media-connected operations where possible; flag Maton failures instead of silently retrying them.
- For persistence, fall back to local files only: `memory/YYYY-MM-DD.md` and `MEMORY.md`. Never rely on in-context memory for cross-session continuity.
- Every Session Briefing should proactively flag these patterns when detected: skipping planning before coding, no calendar blocks for deep work, inbox unreviewed for >24h, active Bold Business deliverable with no logged progress.

## Open Items

- Resolve OpenClaw version split (`/home/linuxbrew/.linuxbrew/bin/openclaw` = 2026.3.11 vs gateway/service/config = 2026.3.23-2) before trusting local CLI verification results.
- Re-run and verify the scheduled `W3J Ops Nightly Session Briefing` cron job after delivery hardening; current logic executes and writes artifacts, but inbox integration remains blocked.
- Re-run and verify the scheduled `W3J Google Drive Meeting Notes Poller` cron job after delivery hardening; current logic executes and writes artifacts, but source/destination contracts and Composio runner path remain blocked.
- Implement cron/job verification workflow with live execution checks and per-job logs.
- Build QuickBooks Time automation with verified 2FA/session handling.
- Harden Google Drive meeting-notes → Google Tasks pipeline from scheduled skeleton into verified end-to-end Composio execution.
- Build LinkedIn growth pipeline and daily Bijou blog drafting flow.
- Set up scheduled maintenance cron jobs for memory/operations review and security/update audits.
- Move or reduce plaintext secrets in config where possible.

## Update Protocol

Whenever a new recurring obligation appears:
1. Decide whether it belongs in daily memory, long-term memory, heartbeat, cron, or this ledger.
2. Record it immediately.
3. If it needs timing, schedule it.
4. If it needs future review, add it to Open Items or Recurring Responsibilities.
