# Changelog

## v2.0.0

Complete rewrite. Nothing from v1 survives except the name and the goal
(export your own Claude conversations to local Markdown).

**Why the rewrite:** v1 was a VS Code extension (TypeScript) plus a Python CLI
that parsed local Claude Code session transcripts. It never touched claude.ai
itself — it had no way to reach Desktop/Web conversations, only what was
already sitting in local JSONL files. v2 solves the actual problem: pulling
your full claude.ai account (conversations, project docs, memory) via the
same API the web/desktop client uses.

**How it works now:**
- Decrypts your own `sessionKey` from Claude Desktop's DPAPI-protected cookie
  store — replaces v1's "read local files only" approach.
- An earlier v2 iteration tried raw TLS/JA3 impersonation
  (`bogdanfinn/tls-client`) to talk to the claude.ai API directly. Cloudflare's
  managed JS challenge defeated it — `cf_clearance` is fingerprint-bound and a
  borrowed cookie doesn't validate. That whole path (~12 dependencies) was
  deleted, not kept as a fallback.
- Replaced it with driving a real, visible Chrome via CDP (`chromedp`): inject
  the cookie, navigate to claude.ai, let Chrome solve the challenge itself,
  then call the API same-origin from inside the page. This is the only
  approach that actually works and it's the one this release ships.

**New in this release, none of it existed in v1:**
- `harvest` — full export: conversations, project knowledge docs, memory.
- `probe` — dumps the raw API schema, useful for finding new surfaces claude.ai
  adds later without guessing.
- `watch` / `tray` — a live-sync daemon (headless or with a system-tray icon),
  gated on Claude Desktop being closed (DPAPI needs the cookie file unlocked).
- Windows installer (`installer/schroedinger-sync.iss`, Inno Setup) — per-user,
  no admin required, autostart via the app's own `install-task` command.
- `security.go` / `security_test.go` — the threat model in SECURITY.md is
  enforced by tests (redaction, hardcoded non-headless flag, claude.ai-only
  egress, no importable package), not just asserted in prose.
- `govulncheck` / `gosec` / `staticcheck` all clean; see SECURITY.md and the
  CI workflow for the specifics.

**Removed:**
- The VS Code extension. It solved a different, smaller problem (local JSONL
  → Markdown) that `harvest`'s `platform` field doesn't even distinguish
  anymore — Code/Cowork/Design conversations all live in the same
  `chat_conversations` API v1 never had access to.
- The Python CLI and its `curl_cffi` dependency — same reason, superseded by
  the Go/CDP approach above.
- Freemium pricing plan (free/Pro €5/Team €15) from the original 2026-03
  business plan. v2 is MIT-licensed and free, permanently — see SECURITY.md
  "Business model" for why.

## v1.0 (superseded, code removed)

VS Code extension + Python CLI. Converted local Claude Code session JSONL
files into readable Markdown summaries. Never had access to claude.ai
Desktop/Web conversations. Frozen since 2026-03-17.
