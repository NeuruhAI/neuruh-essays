# PHANTOM DECK: Why I Built a Phone-First Command Center

I manage 28 active builds from my iPhone.

**PHANTOM DECK** is a Next.js app that connects to my M1 Mac over Tailscale VPN. A WebSocket streams live terminal output. I dispatch allowlisted commands from my phone. No SSH client. No VPN app. Just a browser.

## API surface

- `GET /api/sessions` — discover tmux sessions + status
- `POST /api/command` — dispatch allowlisted command

## Security model

- `x-phantom-secret` header on every command request
- Tailscale VPN as the only transport — public internet can't reach the daemon
- Strict command allowlist — no arbitrary shell

## Phase 1 result

- Shipped in one session
- Phone → Mac → tmux → command → result → phone
- Production build clean

## What's next

- MOTHER batch writes every 5 minutes — reduces Notion API write pressure
- Voice transcription → command
- iOS audio capture for dictated commands

## The thesis

The future of development isn't sitting at a desk. It's orchestrating from anywhere. Dev tooling should follow.
