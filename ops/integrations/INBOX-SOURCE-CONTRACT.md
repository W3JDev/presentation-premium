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

## Required verification before MailTriage can be considered live
- choose the primary inbox access path
- verify the runtime/tooling path actually works from this host
- document whether the source is:
  - Composio
  - Gmail app-password/IMAP path
  - another approved local mail path

## Primary candidate
- Composio Gmail integration

## Temporary status
MailTriage should continue writing `blocked-no-inbox-access` until this contract is verified.
