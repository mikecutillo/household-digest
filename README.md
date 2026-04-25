# Household Digest Engine

An AI-powered daily digest pipeline that ingests email, calendar, news, household events, and internal system state, summarizes everything via Claude, and delivers a single readable briefing to a Discord channel every morning.

> *This repo is a public overview. The running code is private.*

---

## What it is

A household has too many information channels — email across three accounts, shared calendars, school notifications, news, delivery updates, family schedules. This pipeline collapses all of them into a single AI-composed briefing so the day can start with one five-minute read instead of fifteen different app checks.

## What it does

- **Ingests from multiple sources** — Gmail (multi-account), Google Calendar, Microsoft 365 calendar, news RSS, AIOS internal state, weather APIs
- **Classifies and filters** — drops noise (marketing, auto-notifications) and keeps signal (real messages, real events)
- **Composes the digest** via Claude with per-section prompts — "today's schedule", "what changed overnight", "who needs a reply", "weekend preview"
- **Delivers to Discord** at a scheduled time with a consistent house-style formatting
- **Archives past digests** to SQLite for retrospective review

## Software

| Layer | Tech |
|---|---|
| Ingestion | Python, Google APIs (Gmail, Calendar), Microsoft Graph, RSS parsers |
| Classification + summarization | Anthropic Claude |
| Storage | SQLite (digest archive) |
| Delivery | Discord webhooks |
| Scheduling | `launchd` |

## What this demonstrates

- **Multi-source AI summarization** — not a single-document summarizer, a cross-domain synthesis engine
- **Prompt engineering for structure** — reliable section formatting day after day
- **Practical LLM utility** — this replaces a real daily behavior (me checking 8 apps at 7am)

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Anthropic Claude](https://img.shields.io/badge/Anthropic_Claude-CC785C?style=flat&logoColor=white)
![Google APIs](https://img.shields.io/badge/Google_APIs-4285F4?style=flat&logo=google&logoColor=white)
![Microsoft Graph](https://img.shields.io/badge/Microsoft_Graph-0078D4?style=flat&logo=microsoft&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Discord](https://img.shields.io/badge/Discord-5865F2?style=flat&logo=discord&logoColor=white)

## Related in the AIOS Portfolio

- **[Google AI Toolkit](https://github.com/mikecutillo/google-ai-toolkit)** — Gmail + Drive AI toolkit; multi-account OAuth, email analysis, cleanup automation
- **[M365 AI Toolkit](https://github.com/mikecutillo/m365-ai-toolkit)** — Microsoft 365 AI toolkit; mailbox analysis, OneDrive management via Graph API
- **[BMO Discord Agent](https://github.com/mikecutillo/bmo-discord-agent)** — Discord-native family AI companion; the delivery channel for the morning brief

---

Part of the AIOS portfolio. See the [profile README](https://github.com/mikecutillo) for the full system map.
