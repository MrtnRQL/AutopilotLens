# CLAUDE.md

## Design tokens
- Theme: "Paper / Deep teal". Neutral paper surfaces, ink (#23221f) header/sidebar, accent #0f766e.
- Always use CSS variables (--bg*, --text*, --border*, --wash*, --accent*, --ink*). Never hardcode rgba(255,255,255,…).
- Status colors carry meaning. Don't use them decoratively: green = targeted, amber = broad,
  red = excluded/unassigned, purple = "via group".
- On ink surfaces, use --accent-on-dark (#5eb8ab) instead of --accent.

## Testing
- Stub tests must register and BLOCK all calls to graph.microsoft.com and login.microsoftonline.com.
  Nothing may reach the network, even by accident.
- Restore stubs only after all pending requests, timers and retries have settled (wait for the pending sets/queues to drain).
- Never use real tokens in stub tests.
