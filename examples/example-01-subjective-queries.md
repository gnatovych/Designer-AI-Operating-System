# Example 01 — AI Answer for Subjective Queries

## Context

A user asks a question where the answer is community-attested opinion, not verifiable fact — restaurant recommendations, product reviews, experience reports. The shipped default across AI answer products is synthesis: generate a single confident recommendation by averaging across sources. The user receives an authoritative-sounding answer with no way to evaluate the underlying signal.

---

## Decision

Do not synthesize. Surface structured community signal — attributed quotes, recency, source context. Preserve disagreement rather than resolving it.

---

## Rejected

- Single AI-generated recommendation
- Synthesis with "according to reviewers" prefix
- Averaged consensus across divided sources
- Recommendations drawn from training data without live source verification
- Source attribution buried in a footnotes drawer

---

## System behavior

**When query is subjective and community signal is available:**
- Surface attributed quotes from real sources
- Show recency of each source
- Preserve range of opinion
- Do not synthesize into a single recommendation

**When signal is thin or divided:**
- Surface the disagreement explicitly
- Show range of opinion, not a midpoint
- Attribute individual voices

**When signal is absent:**
- Decline to recommend
- Explain what signal is missing and where to find it
- Do not fill the gap with model inference

**When signal is stale (>18 months):**
- Disclose recency on every surfaced recommendation
- Do not treat old sources as current

---

## Failure handling

| State | Behavior |
|-------|----------|
| Model could fill gap with inference | Hard constraint: no recommendation without source signal |
| Community signal is old | Recency disclosure required on all surfaced opinions |
| Sources genuinely disagree | Surface range, do not collapse to midpoint |
| Source attribution cannot be verified | Decline — no hallucinated attribution |
| Query is factual, not subjective | Principle does not apply; synthesis permitted |

---

## Principles engaged

- `community-disagreement.md` — preserve contested signal, decline when signal is absent
- `constraint-first-design.md` — explicit ❌ on unverified recommendation
- `agent-restraint.md` — silence when low confidence adds no signal
