# System Step 01 — Reframe

## Purpose

Find the real problem underneath the stated one.

Every brief contains a surface problem and a structural problem. The surface problem is what someone asked you to solve. The structural problem is why it keeps happening. Designing for the surface problem produces solutions that work once. Designing for the structural problem produces systems.

---

## Input

A brief, request, or problem statement in any form — a Slack message, a one-liner from leadership, a vague product direction, or a user complaint.

---

## Output

A reframed problem statement that:
- Names the structural cause, not the symptom
- Identifies who is actually affected and how
- States what changes if the problem is solved correctly versus superficially
- Specifies what success looks like at the system level

---

## The reframe structure

```
STATED PROBLEM:
[Paste the original brief or problem as given]

SURFACE READING:
[What most people would design for]

STRUCTURAL PROBLEM:
[What is actually broken at the system level]

WHO IS AFFECTED:
[Specific user in a specific moment — not a persona]

WHAT CHANGES IF SOLVED CORRECTLY:
[System-level outcome, not feature outcome]

WHAT CHANGES IF SOLVED SUPERFICIALLY:
[What a quick fix produces and why it fails]

REFRAMED PROBLEM STATEMENT:
[One sentence that captures the structural problem and the outcome required]
```

---

## Reframe as rejection

A correct reframe removes entire solution spaces.

If the reframed problem still allows the original solution, it is not a reframe — it is a restatement. The test is whether the new problem statement closes off the obvious first answer. If it doesn't, the structural problem hasn't been named yet.

---

## Example

**Brief received:** "Users aren't engaging with AI-generated answers. Make them more compelling."

**Surface reading:** The answers need better copywriting, better formatting, or more visual hierarchy.

**Structural problem:** Users don't engage with AI answers because they can't tell the difference between what the model generated and what real people said. The trust signal is absent. Engagement is a downstream symptom of a grounding problem.

**Who is affected:** A user who searches for a restaurant recommendation, receives an AI answer that sounds authoritative, but cannot verify whether it's based on recent reviews or training data from two years ago.

**Solved correctly:** Users can distinguish AI synthesis from human source material. They engage with answers they trust and appropriately discount answers they can't verify.

**Solved superficially:** Better formatting increases click-through in the short term. Trust erodes over time as users encounter confident-sounding wrong answers.

**Reframed problem statement:** Design a system that makes the difference between AI-generated synthesis and real human knowledge visible at the moment of reading — so users can calibrate trust before acting on the answer.

Note what this reframe closes off: it rejects better copy, better formatting, and better visual hierarchy as candidate solutions. Those would solve the surface problem and leave the structural one in place.

---

## What to do after reframing

Pass the reframed problem statement to Step 02 — Failure Behavior.

Do not start designing until the reframe is confirmed with a stakeholder or documented as a decision. The reframe is a commitment. Everything that follows is constrained by it.
