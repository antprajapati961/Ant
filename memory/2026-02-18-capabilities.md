# 2026-02-18 Capabilities Audit

## System
- Ubuntu 20.04.6 LTS (AWS, kernel 5.15.0-1084-aws, x64)
- 4 cores, 15GB RAM, 117GB disk (71GB free)
- Python 3.14.3, Node v25.6.1
- Model: claude-opus-4-6-20260101

## ✅ Working & Ready

### Built-in (no CLI needed)
| Tool | What it does |
|------|-------------|
| web_search | Brave Search API — web research |
| web_fetch | Fetch & extract readable content from URLs |
| browser | Full browser automation (screenshots, clicks, navigation) |
| canvas | Present HTML/UI to user |
| cron | Scheduled jobs, reminders, recurring tasks |
| message | Send WhatsApp messages, polls, reactions |
| tts | Text-to-speech (built-in, no CLI) |
| memory_search/get | Semantic search across memory files |
| sessions_spawn | Spawn sub-agents for parallel/complex work |
| exec | Run any shell command |

### CLI Tools
| Tool | Version | What it does | Auth Status |
|------|---------|-------------|-------------|
| gh | — | GitHub: issues, PRs, CI, code review | ✅ Logged in (antprajapati961) |
| gifgrep | 0.2.1 | Search & download GIFs | ✅ Ready |
| nano-pdf | — | Edit PDFs with natural language | ✅ Ready |
| oracle | 0.8.6 | One-shot GPT-5.2 Pro for hard questions with file context | ✅ Ready |
| whisper | — | Local speech-to-text (OpenAI Whisper) | ✅ Ready |
| songsee | — | Audio spectrograms & visualizations | ✅ Ready |
| clawhub | 0.7.0 | Search/install/publish agent skills | ✅ Ready |
| ffmpeg/ffprobe | — | Media processing, video frames, conversion | ✅ Ready |
| jq | — | JSON processing | ✅ Ready |
| git | — | Version control | ✅ Ready |
| node/npm | v25.6.1 | JavaScript runtime | ✅ Ready |
| python3/pip3 | 3.14.3 | Python runtime | ✅ Ready |
| curl/wget | — | HTTP requests | ✅ Ready |

## ⚠️ Installed but Need Setup

| Tool | Issue | Fix |
|------|-------|-----|
| himalaya | IMAP credentials invalid ("Invalid credentials") | Need correct email password/app password |
| gog | OAuth client disabled | Need to re-auth or fix OAuth client |
| spogo | No cookies found | Need Spotify web cookies |
| wacli | Not authenticated (no QR done) | Run `wacli auth` for QR pairing |
| op (1Password) | No accounts configured | Need `op account add` |
| mcporter | No MCP servers configured | Need to add server configs |
| blu (BluOS) | Installed, no devices tested | Need BluOS speakers on network |

## ❌ Broken

| Tool | Issue |
|------|-------|
| sag (ElevenLabs TTS) | GLIBC_2.34 required, system has GLIBC_2.31 (Ubuntu 20.04 too old) |

## 📦 52 Skills Available (in ~/Downloads/01/openclaw/skills/)
Key ones: coding-agent, github, gog, himalaya, weather, summarize, spotify-player, wacli, 1password, mcporter, nano-pdf, gifgrep, session-logs, skill-creator, healthcheck, obsidian, oracle, video-frames, whisper, songsee, blogwatcher

## GitHub
- Account: antprajapati961
- 1 repo: antprajapati961/Ant (public, created 2026-02-16)

## What I Can Do Right Now (no extra setup)
1. **Web research** — search, fetch pages, browser automation
2. **Coding** — write, edit, run code in Python/JS/bash; spawn coding agents
3. **GitHub** — manage repos, issues, PRs, CI
4. **GIFs** — search and send GIFs
5. **PDF editing** — edit PDFs with natural language
6. **Audio/Video** — transcribe audio (whisper), extract video frames, spectrograms
7. **Reminders & scheduling** — cron jobs, timed alerts
8. **WhatsApp** — send messages, polls, reactions
9. **Text-to-speech** — built-in TTS
10. **File management** — read, write, organize files
11. **Hard questions** — oracle CLI for GPT-5.2 Pro with file context
12. **Skill discovery** — search & install new skills from ClawHub

## What Needs Bhai's Help to Unlock
1. **Email** (himalaya) — need valid IMAP credentials
2. **Google Workspace** (gog) — OAuth client needs fixing
3. **Spotify** (spogo) — need web cookies
4. **WhatsApp history** (wacli) — need QR auth
5. **1Password** (op) — need account setup
6. **MCP servers** (mcporter) — need server configs
7. **Voice TTS** (sag) — needs newer OS or rebuilt binary
