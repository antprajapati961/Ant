# TOOLS.md - Local Notes

## Environment Variables (in ~/.openclaw/env.sh)
- OPENAI_API_KEY → Cortex key (for codex, oracle, pi, opencode)
- OPENAI_BASE_URL → https://codex.claude.gg/v1 (for codex)
- ANTHROPIC_API_KEY → Cortex key (for claude code, pi)
- GOOGLE_API_KEY → Cortex key (for summarize, nano-pdf)

## Coding Agents
- **codex** → OPENAI_BASE_URL=https://codex.claude.gg/v1, model: gpt-5.3-codex (config: ~/.codex/config.toml)
- **claude** → settings at ~/.claude/settings.json, uses app.claude.gg
- **pi** → reads OPENAI_API_KEY / ANTHROPIC_API_KEY from env, default provider: google
- **opencode** → reads env, use `-m provider/model` flag

## Oracle
- Config: ~/.config/oracle/config.json
- Base URL: https://api.claude.gg/v1, model: gpt-5.1
- Usage: `oracle --prompt "question" -f file1.py file2.js`

## Image Generation (via curl)
- Endpoint: https://img.claude.gg
- Auth: Bearer sk-*** (same Cortex key)
- Models: nano-banana-pro, gpt-image-1-5-hd, flux-pro-ultra, flux-kontext-pro, seedream-4-5, google-imagen-4, ideogram-3-quality, etc.
- Usage: POST to /v1/models/{provider}/{model}/predictions

## Perplexity Search
- Available as model alias: `/model search` (sonar-pro) or `/model sonar`
- Also via sub-agent spawn with model override

## Model Providers & Endpoints
| Provider | Endpoint | Daily Limit | Models |
|----------|----------|-------------|--------|
| cortex | app.claude.gg | 1000 | Claude Opus 4.6/4.5, Sonnet 4.5/4/3.7, Haiku 4.5 |
| cortex-gate | api.claude.gg | 2500 | GPT o3, GPT 5.1, GPT 5, Grok 4, DeepSeek R1, Gemini 3 Pro, Gemini 2.5 Flash |
| cortex-search | perplexity.claude.gg | 3000 | Sonar Pro, Sonar |
| cortex-codex | codex.claude.gg | — | gpt-5.3-codex, gpt-5.2-codex, gpt-5.1-codex-max, gpt-5.1-codex |
| cortex-img | img.claude.gg | 1000/400hr | FLUX, Sora 2, Kling, Seedream, Ideogram, Nano Banana, SD 3.5, etc. |

## Model Aliases (for /model command)
opus, opus45, sonnet, sonnet4, sonnet37, haiku, o3, gpt51, gpt5, grok4, deepseek, gemini3, gemflash, search, sonar

## STT (Speech-to-Text) via Gemini
- Endpoint: beta.vertexapis.com (Gemini native API, NOT OpenAI-compatible)
- Auth: key=sk-*** as query param
- Models: gemini-3-flash-preview, gemini-2.5-flash, gemini-2.0-flash
- Daily limit: 3500 requests
- Usage: POST audio as base64 inline_data with mime_type
- Example:
  ```
  curl -s "https://beta.vertexapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=KEY" \
    -X POST -H "Content-Type: application/json" \
    -d '{"contents":[{"role":"user","parts":[{"inline_data":{"mime_type":"audio/wav","data":"BASE64"}},{"text":"Transcribe this audio accurately."}]}]}'
  ```
- Also works for: image analysis, general chat (Gemini native format)
- Note: gemini-3-flash (non-preview) NOT available yet

## Broken/Unavailable
- **sag** (ElevenLabs TTS) — needs GLIBC_2.34, Ubuntu 20.04 has 2.31
- **summarize** (steipete) — needs arm64, we're x64
