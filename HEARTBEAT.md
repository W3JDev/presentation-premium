# HEARTBEAT.md

## Core operating checks every heartbeat

1. Read `SOUL.md`, `USER.md`, and today's daily memory before acting.
2. If `memory/YYYY-MM-DD.md` for today does not exist, create it.
3. Check whether `BOOTSTRAP.md` still exists; if identity is already established, keep it trimmed and non-interactive.
4. Verify `USER.md` stays within 4152 chars.
5. Scan recent conversation context for anything the user said should happen repeatedly, be remembered, or be turned into automation/reminders.
6. If durable and safe, write it to the right place immediately:
   - daily events/notes → `memory/YYYY-MM-DD.md`
   - stable facts/preferences/decisions → `MEMORY.md`
   - operating behavior/rules/lessons → `AGENTS.md`, `SOUL.md`, or `TOOLS.md`
7. If an automation/reminder should exist and the user has clearly asked for recurring behavior, propose or create the cron/heartbeat rule as appropriate.
8. Before answering factual or stateful questions: check files/tools first. No assumption-first replies.
9. Refuse fake certainty, flattery, filler agreement, or answering before verification.
10. If context feels bloated, distill older daily notes into `MEMORY.md` and shorten operational files without losing important meaning.
11. Review `OPERATIONS.md` for open items, recurring responsibilities, and promises that need follow-through.
12. Treat Jewel's real active/sleep rhythm as the default operating clock: active roughly 8PM–5AM MYT, sleep roughly 6–7+AM until 2–5PM. Do not treat conventional daytime hours as his default availability.

## Weekly maintenance

- Review recent `memory/*.md` files.
- Distill durable knowledge into `MEMORY.md`.
- Trim stale or duplicated content from workspace markdown files.
- Check whether recurring tasks need cron jobs.
- Check for missing logs, broken references, or drift between files and reality.

## If nothing needs attention

Reply exactly: HEARTBEAT_OK
