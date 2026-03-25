# OpenClaw Cron Plan

Last updated: 2026-03-25
Owner: Luffy

## Principle
OpenClaw cron is the only scheduler we will actively build on here.

## Phase 1 cron targets

### Job 1. Nightly W3J Ops Briefing
Type:
- isolated agentTurn job

Intent:
- run around 22:00 MYT
- generate the nightly operating briefing using the 3-Agent loop contracts

Prerequisites:
- MailTriage contract ready
- TaskBoard contract ready
- Ops Chief contract ready
- output path ready under `ops/`

### Job 2. Google Drive Meeting Notes Poller
Type:
- isolated agentTurn job

Intent:
- run ~7 times nightly between 20:45 and 05:00 MYT
- detect transcripts in target folders
- extract AI action items
- dedupe against prior state
- push to Google Tasks via Composio

Prerequisites:
- verify Composio auth/config IDs
- define transcript state file
- define dedupe state file

### Job 3. Maintenance / memory hygiene
Type:
- isolated or main-session depending noise level

Intent:
- periodic state cleanup / review
- keep memory and ops files healthy

## Not yet scheduled
The following remain design targets until verification is done:
- QuickBooks Time browser automation
- LinkedIn generation cron
- Bijou daily blog cron

## Scheduling doctrine
- exact cron only when timing matters
- isolated runs by default for automation jobs
- write durable artifacts before announce/delivery
- verify outputs after creation and after first live run
