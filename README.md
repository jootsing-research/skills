# TapKit Skills

Skills that teach AI agents how to control iPhones and navigate iOS apps.

## Official Plugins

If you're using TapKit with **Claude Code** or **Codex**, use the official plugins instead — they bundle these skills with MCP tools for a seamless experience:

- [TapKit for Claude Code](https://github.com/Jootsing-Research/tapkit-plugins-claude)
- [TapKit for Codex](https://github.com/Jootsing-Research/tapkit-plugins-codex)

## When to Use This Repo

This repo is for agents and tools that **don't have an official plugin** — Cursor, OpenClaw, GitHub Copilot, and [35+ other agents](https://github.com/vercel-labs/skills) that support the open [Agent Skills](https://agentskills.io) standard.

Install the skills, then connect TapKit via the [MCP server](https://github.com/Jootsing-Research/tapkit-mcp).

## Install

```bash
npx skills add jootsing-research/skills
```

## Skills

### Core

| Skill | Description |
|-------|-------------|
| `tapkit` | How to use TapKit — coordinate system, screenshot loop, gestures, navigation patterns |
| `tapkit-cli` | How to use the TapKit CLI — terminal commands for iPhone control |

### App Skills

| Skill | App | What it covers |
|-------|-----|---------------|
| `clock` | Clock | Alarms, stopwatch, timers, world clock |
| `craigslist` | Craigslist | Classifieds search, filters, saved searches, replies, posting drafts |
| `facebook` | Facebook | Feed, reels, marketplace, groups, messaging, stories |
| `hinge` | Hinge | Profile browsing, likes, roses, messaging, preferences |
| `instagram` | Instagram | Feed, reels, stories, DMs, explore, profile |
| `linkedin` | LinkedIn | Feed, networking, jobs, reactions, messaging |
| `mail` | Apple Mail | Email search, Craigslist verification, compose, drafts |
| `telegram` | Telegram | Chat types, reactions, search, bots, groups, channels |
| `tiktok` | TikTok | Feed navigation, video actions, DMs, inbox, creator pages |
| `twitter` | Twitter / X | Feed, compose, DMs, search, interactions |
| `uber-eats` | Uber Eats | Restaurant search, ordering, checkout, reorders |
| `weather` | Weather | Forecasts, maps, air quality, detailed conditions |
| `whatsapp` | WhatsApp | Chats, unsaved numbers, search, calls, statuses, channels |

## How Skills Work

Skills are Markdown files (`SKILL.md`) that follow the open [Agent Skills](https://agentskills.io) standard. They teach AI agents:

- **App knowledge** — what the app looks like (tabs, buttons, navigation patterns, gotchas)
- **Task strategy** — what to do with the app (workflows, engagement playbooks)

The agent reads the skill, then uses TapKit tools (via MCP or CLI) to execute actions on the phone.

## MCP/API Call References

When an agent starts a phone task through MCP, the skills should point it at this setup flow:

```text
list_phones({})
get_phone_status({"phone_id": "..."})
```

REST API equivalents use `https://api.tapkit.ai/v1` with the `X-API-Key` header:

| Intent | MCP tool | REST endpoint |
|--------|----------|---------------|
| List phones | `list_phones` | `GET /phones` |
| Check connection state | `get_phone_status` | `GET /phones/{phone_id}/status` |

## Requirements

- [TapKit](https://tapkit.ai) account with a connected iPhone
- TapKit [MCP server](https://github.com/Jootsing-Research/tapkit-mcp)

## Links

- [TapKit](https://tapkit.ai) — Get started
- [TapKit MCP](https://github.com/Jootsing-Research/tapkit-mcp) — MCP server for AI agents
- [Documentation](https://docs.tapkit.ai) — Full docs
