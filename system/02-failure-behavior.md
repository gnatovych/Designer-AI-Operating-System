# System Step 02 — Failure Behavior

## Purpose

Specify what the system does when default behavior would produce the wrong output.

Failure behavior is not error handling. It is the system's correct response to states where the naive path fails — low confidence, conflicting signal, ambiguous intent, absent data, active exploration. These states are common, not exceptional. The system's behavior in them determines whether the product is trustworthy.

---

## Output

A specification that names each failure state, the default behavior rejected, the correct behavior, and why.

---

## The failure states

### State: Active exploration

The user is reading, comparing, thinking. They have not asked for help. The system has observations it could surface.

**Default rejected:** Proactive suggestions, inline prompts, assistant rails.
**Correct behavior:** Silence. Wait for the user's state to change — finished thread, returned after interruption, explicit request.
**Why:** Interruption during focused work reduces preference regardless of productivity lift. The agent's value is restraint, not presence. (See `/principles/agent-restraint.md`.)

### State: Cold start, no signal

The user is new or has no history. The system has nothing to personalize, recommend, or continue.

**Default rejected:** Empty state, silence, wait for organic behavior to accumulate.
**Correct behavior:** Generate minimal signal. Welcome content, lightweight intent prompts, small number of concrete next actions. Enough to produce the first useful interaction.
**Why:** Silence in cold start teaches the user the surface is empty. They do not return. Silence is correct during exploration and incorrect during cold start — the distinction is state, not preference.

### State: Low confidence

The system has something it could output but cannot verify it. Model uncertainty, stale data, conflicting sources, insufficient signal.

**Default rejected:** Output anyway, hedged with disclaimer language ("results may vary"). Generate a plausible answer and qualify it.
**Correct behavior:** Decline or defer. Surface what signal is missing and where it could be found. Hedging launders uncertainty into the same confident format and is worse than silence.
**Why:** Confident-sounding wrong answers degrade trust faster than declined answers. The hedge does not reach the user; the confidence does.

### State: Conflicting sources

The user asked a question where the underlying signal disagrees. Reviews split, experts disagree, community is divided.

**Default rejected:** Synthesize into a single confident answer. Hedge with "opinions vary."
**Correct behavior:** Surface the disagreement as the answer. Show the range, attribute the voices, preserve the tension. Let the user adjudicate. (See `/principles/community-disagreement.md`.)
**Why:** Synthesis strips the signal that made the sources valuable. The disagreement is the answer.

### State: Ambiguous intent

The user's request can be read multiple ways. The system could guess which reading to act on.

**Default rejected:** Infer the most likely meaning and proceed. Pattern-match to prior queries and assume.
**Correct behavior:** Ask one targeted clarification, or present the two to three readings with clear labels. Do not proceed until the path is explicit.
**Why:** Silent inference produces work the user did not ask for. The cost of a clarifying question is lower than the cost of undoing a wrong action.

### State: Return after interruption

The user was in the middle of an inquiry and left. Now they are back.

**Default rejected:** Reset to home feed. Start fresh. Treat the return as a new session.
**Correct behavior:** Reconstruct prior state — scroll position, inquiry context, related threads — before requiring any decision. Around 12 seconds of visual orientation before the next action prompt.
**Why:** Fast resumption correlates with higher error rates. Users need visual reconstruction, not decisions, at re-entry.

---

## How to use this

For any new AI behavior, enumerate which of these states it will encounter. For each state, specify the correct behavior and the default being rejected. Do not ship until every state has been addressed.

If a state is not on this list but applies to the product you are designing, add it. The list is a starting point, not a ceiling.

The test: can you describe the system's behavior in every state without using the word "hopefully"?
