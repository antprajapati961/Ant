# 2026-02-18 Capabilities Audit

## System
- Ubuntu 20.04.6 LTS (AWS, kernel 5.15.0-1084-aws, x64)
- 4 cores, 15GB RAM, 117GB disk (71GB free)
- Python 3.14.3, Node v25.6.1
- Model: claude-opus-4-6-20260101

## ✅ Working & Ready

### Built-in Tools (no CLI needed)
| Tool | What it does | Status |
|------|-------------|--------|
| web_fetch | Fetch & extract readable content from URLs | ✅ Ready |
| browser | Full browser automation (screenshots, clicks, navigation) | ✅ Ready |
| canvas | Present HTML/UI to user | ✅ Ready |
| cron | Scheduled jobs, reminders, recurring tasks | ✅ Ready |
| message | Send WhatsApp messages, polls, reactions | ✅ Ready |
| tts | Text-to-speech (built-in) | ✅ Ready |
| memory_search/get | Semantic search across memory files | ✅ Ready |
| sessions_spawn | Spawn sub-agents for parallel/complex work | ✅ Ready |
| exec | Run any shell command | ✅ Ready |

### CLI Tools — Ready to Use
| Tool | Version | What it does |
|------|---------|-------------|
| gh | — | GitHub: issues, PRs, CI, code review (logged in: antprajapati961) |
| codex | 0.101.0 | OpenAI Codex coding agent (GPT-5.2-codex) |
| claude | 2.1.42 | Claude Code coding agent |
| pi | 0.52.9 | Pi coding agent (multi-provider) |
| opencode | 1.2.0 | OpenCode coding agent |
| oracle | 0.8.6 | One-shot GPT-5.2 Pro for hard questions with file context |
| gifgrep | 0.2.1 | Search & download GIFs |
| nano-pdf | — | Edit PDFs with natural language (Gemini 3 Pro) |
| whisper | — | Local speech-to-text (OpenAI Whisper) |
| songsee | — | Audio spectrograms & visualizations |
| blogwatcher | — | Track blogs/RSS feeds for new articles |
| clawhub | 0.7.0 | Search/install/publish agent skills |
| ffmpeg/ffprobe | — | Media processing, video frames, conversion |
| tmux/screen | — | Terminal multiplexing |
| jq | — | JSON processing |
| git | — | Version control |
| node/npm | v25.6.1 | JavaScript runtime |
| python3/pip3 | 3.14.3 | Python runtime (numpy, pyyaml installed) |
| curl/wget | — | HTTP requests |

### API Keys Available
- GOOGLE_API_KEY — used by nano-pdf (Gemini), oracle, etc.
- (No Brave API key — web_search disabled, use web_fetch instead)

## ⚠️ Installed but Need Setup

| Tool | Issue | Fix |
|------|-------|-----|
| himalaya | IMAP auth fails ("Invalid credentials") | Need correct email app password |
| gog (Google) | OAuth client disabled | Need to re-auth or fix OAuth client |
| spogo (Spotify) | No cookies found | Need Spotify web cookies |
| wacli (WhatsApp history) | Not authenticated | Run `wacli auth` for QR pairing |
| op (1Password) | No accounts configured | Need `op account add` |
| mcporter (MCP) | No servers configured | Need to add server configs |
| blu (BluOS) | No devices on network | Need BluOS speakers |
| web_search (Brave) | No API key | Run `openclaw configure --section web` or set BRAVE_API_KEY |
| summarize (steipete) | Not installed (sumy is installed instead, basic) | `brew install steipete/tap/summarize` for full version |

## ❌ Broken

| Tool | Issue |
|------|-------|
| sag (ElevenLabs TTS) | GLIBC_2.34 required, system has GLIBC_2.31 (Ubuntu 20.04 too old) |

## 📦 52 Skills Available (in ~/Downloads/01/openclaw/skills/)
Key ones: coding-agent, github, gog, himalaya, weather, summarize, spotify-player, wacli, 1password, mcporter, nano-pdf, gifgrep, session-logs, skill-creator, healthcheck, obsidian, oracle, video-frames, whisper, songsee, blogwatcher

## GitHub
- Account: antprajapati961
- 1 repo: antprajapati961/Ant (public, created 2026-02-16)

## Coding Agents (all 4 installed, all need pty:true)
- **codex** 0.101.0 — OpenAI, needs git repo, `--full-auto` or `--yolo` for auto-approve
- **claude** 2.1.42 — Anthropic Claude Code
- **pi** 0.52.9 — Multi-provider, supports Anthropic prompt caching
- **opencode** 1.2.0 — Alternative coding agent

## Weather
- wttr.in via curl — no API key needed, tested working (Ahmedabad: ☁️ +22°C)

## What I Can Do Right Now (no extra setup)
1. **Web research** — web_fetch for URLs, browser automation for complex sites
2. **Coding** — write/edit/run code + 4 coding agents (codex, claude, pi, opencode)
3. **GitHub** — full access: repos, issues, PRs, CI, code review
4. **GIFs** — search and send via gifgrep
5. **PDF editing** — natural language PDF edits via nano-pdf
6. **Audio/Video** — transcribe (whisper), extract frames (ffmpeg), spectrograms (songsee)
7. **Reminders & scheduling** — cron jobs, timed alerts
8. **WhatsApp** — send messages, polls, reactions
9. **Text-to-speech** — built-in TTS tool
10. **File management** — read, write, organize, git commit
11. **Hard questions** — oracle CLI (GPT-5.2 Pro with file context)
12. **Skill discovery** — clawhub search & install
13. **Blog monitoring** — blogwatcher for RSS/blog tracking
14. **Weather** — wttr.in, no key needed
15. **Security audit** — healthcheck skill for host hardening
16. **Terminal automation** — tmux/screen for interactive CLIs

## What Needs Bhai's Help to Unlock
1. **Email** (himalaya) — need valid IMAP app password
2. **Google Workspace** (gog: Gmail, Calendar, Drive, Docs, Sheets) — OAuth client needs fixing
3. **Spotify** (spogo) — need web cookies
4. **WhatsApp history search** (wacli) — need QR auth
5. **1Password** (op) — need account setup
6. **MCP servers** (mcporter) — need server configs
7. **Web search** (Brave) — need API key
8. **Voice TTS** (sag/ElevenLabs) — needs newer OS or rebuilt binary
9. **Summarize** (steipete version) — needs brew install for full YouTube/URL summarization
