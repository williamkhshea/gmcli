# Changelog

## 0.1.1

- Fix `--reply-to` to accept both thread IDs and message IDs
  - Previously required a message ID; now also accepts thread IDs from search results
  - When given a thread ID, automatically uses the last message in the thread
- Fix `spawn start ENOENT` error on Windows when adding account
  - Use `cmd.exe /c start` instead of spawning `start` directly
- Fix `sendDraft` returning undefined and crashing on `.id` access
  - API returns Message directly in `response.data`, not `response.data.message`

## 0.1.0

Initial release.

- Account management (add, remove, list)
  - `--manual` flag for browserless OAuth (paste redirect URL)
- Search threads with Gmail query syntax
  - Returns thread ID, date, sender, subject, labels (human-readable names)
- View threads with message IDs and attachment info
- Download attachments
- Labels management
  - List all labels with `labels list`
  - Modify labels by name or ID (case-insensitive)
- Drafts (create, list, get, delete, send)
  - Support for replies (`--reply-to <messageId>`)
  - Support for attachments (`--attach <file>`)
- Send emails directly
  - Same options as draft creation
- Generate Gmail web URLs for threads (`url` command)
  - Uses canonical URL format with `authuser` parameter
