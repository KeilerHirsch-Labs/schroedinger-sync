# Schroedinger Sync

**Readable Markdown summaries from your Claude Code sessions.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![VS Code](https://img.shields.io/badge/VS%20Code-Extension-007ACC?logo=visualstudiocode)](extension/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)](cli/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/KeilerHirsch/schroedinger-sync/pulls)

---

## What Does This Do?

Schroedinger Sync reads your Claude Code JSONL session transcripts and generates clean, searchable Markdown summaries. Track what you discussed, which tools were used, and what decisions were made — across all your sessions.

**100% private.** Everything stays on your computer. No cloud. No account. No server.

---

## Quick Start

### VS Code Extension (Recommended)

```bash
git clone https://github.com/KeilerHirsch/schroedinger-sync.git
cd schroedinger-sync/extension
npm install && npm run compile && npx vsce package
# Install the generated .vsix via VS Code: Extensions → "..." → Install from VSIX
```

Works out of the box — statusbar button appears, auto-sync watches for new sessions.

### Python CLI

```bash
git clone https://github.com/KeilerHirsch/schroedinger-sync.git
cd schroedinger-sync/cli

# Run (zero dependencies — pure Python 3.10+)
python sync_schroedinger.py

# Options
python sync_schroedinger.py --max 5        # Process max 5 sessions
python sync_schroedinger.py --git           # Auto-commit after sync
python sync_schroedinger.py --output ./out  # Custom output directory
```

---

## Features (v0.3)

1. Finds all Claude Code JSONL session transcripts in `~/.claude/projects/`
2. Parses conversations: user messages, assistant responses, tool usage
3. Generates clean Markdown summaries per session
4. Tracks sync state (only processes new/changed sessions)
5. Optionally auto-commits to Git
6. Reports project diagnostics (settings bloat, permissions bypass detection)

### Output Example

Each session becomes a Markdown file like `20260305_parsed-booping-ullman.md`:

```markdown
# Session: parsed-booping-ullman

**Session ID:** e1835fc4-dc62-444a-b908-70c61fb79825
**Date:** 2026-03-05 07:28 UTC
**Turns:** 88

## Tool Usage
- Bash: 237x
- Read: 146x
- Edit: 113x
- Agent: 73x

## Conversation Flow
1. **User:** Fix the LTeX extension...
2. **User:** Check all extensions...
...
```

---

## Configuration

Environment variables:

| Variable | Default | Description |
|----------|---------|-------------|
| `SCHROEDINGER_OUTPUT` | `./sync` | Output directory for summaries |
| `SCHROEDINGER_GIT_COMMIT` | `false` | Auto-commit after sync |
| `SCHROEDINGER_MAX_SESSIONS` | `0` (all) | Max sessions to process |

---

## Roadmap

| Version | Status | What |
|---------|--------|------|
| **v0.1** | Done | Python CLI — session parsing and Markdown export |
| **v0.2** | Done | VS Code Extension — auto-sync, statusbar integration |
| **v0.3** | Done | Project diagnostics, settings bloat detection |
| **v1.0** | Planned | Multi-AI session parsing (Gemini, ChatGPT, DeepSeek) |
| **v2.0** | Planned | Knowledge graph, fact extraction, conflict detection |

---

## Requirements

- **VS Code Extension:** VS Code 1.85+
- **Python CLI:** Python 3.10+ (zero external dependencies)
- **Platform:** Windows, macOS, Linux

---

## Contributing

PRs are welcome. Check the [issues](https://github.com/KeilerHirsch/schroedinger-sync/issues) for open tasks or propose new features.

---

## License

MIT — see [LICENSE](LICENSE)

## Author

**KeilerHirsch** ([@KeilerHirsch](https://github.com/KeilerHirsch))
