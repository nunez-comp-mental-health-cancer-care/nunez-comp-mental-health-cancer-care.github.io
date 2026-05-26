---
name: Always restart dev server and report URL
description: After making any changes, restart the Hugo dev server and tell the user the URL
type: feedback
originSessionId: 2a469388-0ab1-411a-a3e8-2bcc2c4ac539
---
After every set of changes, restart the Hugo dev server with `hugo server -D --disableFastRender` and tell the user the URL where the site is live.

**Why:** The user got frustrated having to ask where the site was after server restarts changed the port.

**How to apply:** End every response that changes content with a server restart and the live URL.
