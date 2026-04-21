# Example 02 — Continuity Across Fragmented Inquiry

## Context

A large-scale consumer product explored adding multitasking to support users navigating multiple discovery paths over time. Initial direction modeled the feature on browser tabs. Observable behavior: mobile users were restarting research-heavy inquiries instead of resuming them.

---

## Decision

Reject the browser paradigm. Build an implicit continuity layer. Track inquiry state invisibly. Restore context on return. Surface structure only when the user's state changes.

---

## Rejected

- Tabs, tab groups, window management. Require active management. Do not fit mobile surface or casual seeking intent.
- Named sessions, saved workspaces, explicit projects. Setup cost collapses adoption on mobile.
- Long-term behavioral personalization. Triggers trust and privacy costs while solving the wrong problem.
- Persistent UI chrome, always-on assistant rails, side panels. Punish simple use cases to serve a minority of research-heavy sessions.
- Auto-advance on return. Fast resumption correlates with higher error rates.

---

## System behavior

**On first use:** No setup. No onboarding that teaches session management. The first inquiry is indistinguishable from any other search.

**During an inquiry:** The system observes posts visited, topics consulted, search paths taken, scroll depth. No visible state accumulates in the UI. The user is not aware the system is tracking anything.

**On interruption:** The user leaves. The system retains inquiry context with no action required from the user.

**On return:** The system reconstructs orientation before requiring a decision. Prior scroll position, inquiry context, related threads visible. Around 12 seconds of visual orientation — no auto-advance, no "next step" prompt.

**On exploration continuation:** Silence. No suggestions, no inline prompts. The user reads, compares, decides their own next move.

**On state change:** When the user finishes a thread, explicitly asks for more, or returns after long interruption, the system may surface a relevant next step. Only then.

**On cold start:** Minimal guided prompts. Small number of concrete options. Just enough signal for the first useful interaction.

**On contested information:** Disagreement surfaced as disagreement. Attribution preserved. No synthesis.

---

## Failure handling

| State | Behavior |
|-------|----------|
| User returns mid-inquiry | Reconstruct state. No action prompt for 12 seconds. |
| User actively reading | Silence. No proactive suggestions. |
| System has low confidence | Decline. Do not generate hedged answer. |
| Sources are divided | Surface range. Do not synthesize. |
| User new, no signal | Minimal welcome prompts. Not empty state. |
| Proposal to add explicit "Spaces" or "Projects" | Rejected — violates implicit-memory constraint. |

---

## Principles engaged

- `continuity.md` — implicit memory, resume over restart
- `agent-restraint.md` — silence during active exploration
- `community-disagreement.md` — preserve contested signal
- `constraint-first-design.md` — explicit rejection of browser paradigms
