# Prime Age by AgeGen — for AI assistants

Prime Age is a self-assessment of twelve daily habits (sleep, movement, food,
stress, alcohol, smoking and more), expressed as an age. This repository
connects it to AI assistants: take the quiz in conversation, do your daily
check-in, see how your logged numbers moved, and get the sourced protocol for
the habit to work on next.

It works with any assistant that supports remote MCP servers — Claude,
ChatGPT and others — because the service itself is one server:
**`https://agegen.ai/mcp`**. This repository holds the server address, the
skills that teach an assistant how to run the quiz and the check-in, and the
Claude plugin manifest.

**Educational wellness content, not medical advice, and not a medical test.**
It describes habits you report; it never assesses your body.

## What's inside

| Part | What it does |
|---|---|
| MCP server `https://agegen.ai/mcp` | 12 tools (below) |
| Skill `prime-age-quiz` | runs the twelve questions one at a time and reports the result |
| Skill `daily-checkin` | today's morning or evening questions, saved to your account |
| Skill `weekly-review` | how your number and measurements moved, and one next step |

**Without an account:** `prime_age_questions`, `prime_age_calculate`,
`protocol_search`. Nothing is stored.

**With your Prime Age account** (sign in with Telegram the first time a tool
needs it): `get_my_prime_age`, `get_my_levers`, `get_checkin`,
`submit_checkin`, `get_my_trends`, `log_metrics`, `get_route`, `set_goal`,
`save_quiz_result`. The assistant writes to your account only when you ask it to.

## Connect

| Assistant | How |
|---|---|
| **Claude Code** | `/plugin marketplace add AgeGenAI/primeage`, then `/plugin install agegen-prime-age@agegen` |
| **Claude** (web, desktop, mobile) | Settings → Connectors → Add custom connector → `https://agegen.ai/mcp` |
| **ChatGPT** | Settings → Apps & Connectors → Advanced → Developer mode on; then Create → URL `https://agegen.ai/mcp`, authentication OAuth (paid plans) |
| **Any other MCP client** | Add a remote (Streamable HTTP) server at `https://agegen.ai/mcp`; sign-in is standard OAuth 2.1 with PKCE |

The skills in `skills/` are plain `SKILL.md` files and can be used by any
assistant that reads them.

## Try

- "What's my Prime Age? Ask me the questions."
- "Do my morning check-in."
- "Which habit is costing me the most, and what's the protocol for it?"
- "How did my weight and sleep move this month?"

## Free and Pro

The plugin is free. A free account sees its three weakest habits and 30 days
of logged numbers. Prime Age Pro (bought in the Prime Age app in Telegram)
adds all twelve habits with what each is worth, 400 days of history and more
metrics — and it works here as soon as it is active on your account. Nothing
is sold inside an assistant. Full comparison: https://agegen.ai/prime-age-pro/

## Your data

- Signing in uses Telegram's own login page. Your account is keyed on your
  Telegram id; nothing else from Telegram is stored.
- Your answers and measurements are stored in your Prime Age account (EU,
  Frankfurt) — the same account the Telegram app uses. The assistant receives
  only what a tool returns in that conversation.
- Body measurements are stored only after a one-time consent given in the
  Prime Age app.
- Disconnecting the connector stops access; deleting your account in the
  Prime Age app removes the data.

Privacy: https://agegen.ai/privacy/ · Terms: https://agegen.ai/terms/ ·
Method: https://agegen.ai/prime-age-methodology/ · Support: info@agegen.ai

## License

MIT for the contents of this repository (the manifests, skills and
documentation). The Prime Age service, its data and the AgeGen name are not
covered by it.
