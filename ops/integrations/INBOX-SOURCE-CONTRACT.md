# Inbox Source Contract

Last updated: 2026-03-25
Owner: Luffy
Status: pending-verification

## Purpose
Define the verified inbox access path MailTriage is allowed to use.

## Current known options
- Gmail / Google-related auth exists in workspace `.env`
- Composio-related Gmail auth config IDs exist in workspace `.env`
- Gmail app-password entries exist in workspace `.env`
- `gog` is installed locally and may provide an alternate Google/Gmail inspection path

## Required verification before MailTriage can be considered live
- choose the primary inbox access path
- verify the runtime/tooling path actually works from this host
- document whether the source is:
  - Composio
  - Gmail app-password/IMAP path
  - another approved local mail path

## Primary candidates
1. `gog` Gmail access (near-term verification path)
2. Composio Gmail integration (preferred long-term integration surface)

## Runtime verification result
- `gog` is installed and supports Gmail, but is currently **not authenticated** on this host (`credentials_exists: false`, no configured account).

## Temporary status
MailTriage should continue writing `blocked-no-inbox-access` until one of the above paths is verified from this host/runtime.
