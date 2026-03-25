# 3-Agent Daily Loop

Last updated: 2026-03-25
Owner: Luffy

## Objective
Create a repeatable nightly command layer for W3J Ops that produces a concise session briefing before deeper work begins.

## Agents

### 1. MailTriage
Purpose:
- classify unread email
- identify urgent / NDA / approval-needed mail
- draft replies only (never send)

Output contract:
- `ops/state/mailtriage-latest.json`
- fields:
  - generatedAt
  - urgentCount
  - approvalNeededCount
  - ndaCount
  - summaries[]
  - draftSuggestions[]

### 2. TaskBoard
Purpose:
- collect active tasks
- flag overdue / stale items
- produce today's 3 MITs

Priority rule:
Revenue Blocker -> Bold Business deliverable -> W3J product

Output contract:
- `ops/state/taskboard-latest.json`
- fields:
  - generatedAt
  - overdue[]
  - stale[]
  - mits[]
  - notes[]

### 3. Ops Chief
Purpose:
- read MailTriage + TaskBoard outputs
- produce final session briefing

Output contract:
- `ops/briefings/YYYY-MM-DD-session-briefing.md`
- final briefing must include:
  - urgent mail summary
  - 3 MITs
  - one actionable Ops Note
- max length: 300 words

## Execution model
- Build internal file/output contracts first.
- Do not send outbound messages automatically except the final user-facing update path we explicitly choose.
- Treat approval-needed mail as draft-only.
- Persist state so the loop is restart-safe.

## Scheduling intent
Primary target:
- nightly session boot around 22:00 MYT

Follow-up jobs may include:
- pre-brief checks
- mid-shift task refresh
- transcript/task ingestion jobs

## Verification rules
- no success claims without file/output verification
- each stage should write a durable artifact
- if an upstream artifact is missing, Ops Chief should fail clearly instead of hallucinating a briefing
