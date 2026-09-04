# Aliw Host V10.7.7 — Referral Stability + Reliability Edition

A premium Telegram-based multi-runtime project hosting manager with GitHub public/private repository deployment, Git-less fallback, force-join access, real backup vault, ENV isolation, per-project editing, GitHub runtime-data backups, and reliability tooling.

## V10.7.7 highlights

- Smart Project Setup Wizard + Required ENV Wizard
- Advanced File Manager with create/view/download/edit/replace/rename/delete
- Automatic per-file version history and undo
- Test-before-restart and Smart Error Center
- Project activity timeline + notification preferences
- Python/Node dependency manager UI commands
- GitHub Data Sync V2 with timestamped backup versions
- GitHub Data Sync conflict protection
- Admin Project Explorer
- Owner Data Sync Center + Sync All
- Project Lock
- Project names containing spaces supported with `|` separators
- Existing GitHub private-repo tokens, Git-less archive deployment, auto-deploy, rollback, backups, trash, templates, plans, tickets and premium UX retained
- Referral deep-link capture + pending referral verification fix retained from V10.7.6
- Fast callback/input reliability layer retained
- GitHub pipe/SHA 422 parser fix retained

## Project names with spaces

Use `|` when one command contains more than one argument:

```text
/rename Aliw Like | Aliw Like2
/replacefile Aliw Like | bot.py
/setenv Aliw Like | BOT_TOKEN | your_value
/scheduleaction Aliw Like | restart | 6h
```

Commands that only need a project name can still accept the full project name normally, e.g. `/health Aliw Like`.

## Isolation note

V10.7 strips manager secrets from hosted child-process environments and validates archive paths/symlinks. True per-project OS/container isolation requires Docker/cgroups or equivalent support from the hosting provider and cannot be guaranteed by Python application code alone.

## V10.7.3 GitHub Remember + Manual Redeploy Fix
- Per-user GitHub token is remembered and reused for future repositories.
- Token is mirrored into SQLite and local 0600 token store; manager global token does not override normal users.
- New GitHub ENV block opens ENV Wizard directly.
- Skip ENV once or remember auto-skip for future GitHub projects.
- GitHub buttons: Check Updates, Pull Latest, Force Redeploy, Auto Deploy ON/OFF.
- Commands: /githubcheck, /forceredeploy, /envskipdefault.

## V10.7.4 Fast Response Patch
- Force Join membership verification is cached for 10 minutes; Verify Membership always performs a fresh check.
- Channel/group membership checks run concurrently instead of one-by-one.
- SQLite mirror writes are coalesced and moved off the Telegram event loop.
- Telegram HTTP connection pool increased for busy multi-user usage.
- Callback concurrency increased and heavy project/GitHub actions show immediate processing feedback.
- Start/stop process work is moved off the event loop where safe.
