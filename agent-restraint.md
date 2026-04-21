# Principle — Agent Restraint

## The rule

An AI agent's job is restraint, not helpfulness.

Do not interrupt active exploration. Do not generate output when low confidence adds no new signal. Act only when the user's state has changed.

---

## Why this exists

Proactive assistance is the shipped default across the category. Cursor, Copilot, Notion AI, ChatGPT's suggestion rails — all of them optimize for presence. The assumption is that more help is better help.

CHI 2025 data contradicts this. Persistent proactive suggestions raise task completion 12–18% and cut user preference roughly in half. Short-term productivity lift, long-term attrition. This is Clippy's failure mode, rediscovered with better models.

Restraint is harder to ship because it doesn't demo well. A restrained agent looks like it's doing nothing. A helpful agent looks like it's working. The metric that matters — sustained use over weeks, not sessions over days — only distinguishes them later, when the intrusive agent has already trained users to dismiss it.

---

## What restraint requires

**During active exploration:** silence. The user is reading, thinking, comparing. New suggestions, summaries, or "next step" prompts break concentration. The agent stays out of the way until the user's state changes — they finish a thread, return after interruption, or explicitly ask.

**When the system has low confidence:** silence. If the agent cannot add new signal, generating output anyway is noise disguised as helpfulness. Hedged language ("results may vary") does not fix this. It launders uncertainty into the same confident format.

**When the user has not asked:** silence. Unsolicited suggestions are a tax on attention. The tax compounds. Users eventually stop looking at the surface where suggestions appear.

---

## Where restraint does not apply

Silence is the wrong behavior in one specific state: cold start, when the system has no signal because the user is new. Staying silent there teaches the user the surface is empty. That failure mode is addressed in `/system/02-failure-behavior.md` — it is a state distinction, not a contradiction.

Restraint governs active states. It does not govern absence of state.

---

## Failure mode if violated

The agent becomes ambient noise. Users develop automatic dismissal — they stop reading suggestions before deciding whether to read them. The surface the agent occupies becomes dead space. Recovering from this is harder than never occupying it.

---

## Opposing view (shipped)

- GitHub Copilot: inline suggestions on every pause in typing
- Cursor: proactive completion across the editor
- Notion AI: suggestion rails persistent in the UI
- ChatGPT: follow-up prompts appended to every response
- Perplexity: related queries surfaced by default

All five ship the opposite default. The disagreement is real and current.
