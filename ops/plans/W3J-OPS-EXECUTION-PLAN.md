# W3J Ops Execution Plan

Last updated: 2026-03-25
Owner: Luffy

## Current verified substrate
- OpenClaw is the control plane.
- Gateway is running and reachable locally.
- Elevated execution works via approval flow.
- Memory search is operational with local embeddings.
- Workspace `.env` exists and contains live integration keys/config references.
- There are currently 0 OpenClaw cron jobs.

## Priority execution order

### 1. 3-Agent Daily Loop
Goal: create the internal operating system before external side effects.

Agents:
- MailTriage
- TaskBoard
- Ops Chief

Required outputs:
- urgent mail summary
- 3 MITs
- one actionable Ops Note
- final briefing <= 300 words

Implementation notes:
- persist outputs under `ops/briefings/` and `ops/state/`
- keep send/no-send boundaries explicit
- never send drafted replies without explicit approval

### 2. Bold Business Automations
#### 2A. QuickBooks Time
- verify live access path
- verify session persistence / 2FA handling
- design check-in / break / check-out job flow

#### 2B. Google Drive -> Google Tasks via Composio
- use Composio as the primary integration surface
- verify auth config IDs and access assumptions
- design dedupe state file under `ops/state/`

### 3. Content Engine
- LinkedIn generation pipeline
- Bijou daily blog drafting workflow

## Immediate next build steps
1. Integration map from workspace `.env`
2. 3-Agent loop file/contracts
3. first cron plan (not yet applied)
4. Composio/Google pathway verification design
5. content engine dependency map
