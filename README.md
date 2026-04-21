# Designer AI Operating System

This is not a prompt library. This is not a guide to using AI tools.

A system for defining AI product behavior under uncertainty.

Most AI products optimize for what the system does when it works. This system defines what it does when it fails — and forces decisions before those failures happen.

---

## What this is

When confidence is low, when sources conflict, when the user is mid-inquiry, when the default behavior would be confidently wrong — these are the states that determine whether an AI product is trustworthy. They are common, not exceptional. The system's behavior in them is the product.

This repository is a behavioral model for those states. Each file enforces a rule that rejects a shipped default in the AI product category. The goal is not coverage. It is a small number of decisions that hold up under pressure.

---

## Who this is for

Product designers working on AI-native products. Teams defining system behavior before UI. Anyone designing at the boundary where interaction decisions become system constraints.

---

## Structure

**`/principles`** — Rules that reject a specific shipped default. Each principle names the failure mode if violated and the product currently shipping the opposing position.

**`/system`** — Repeatable steps for converting a vague product problem into a behavioral specification. Each step forces a decision, not a description.

**`/examples`** — Worked examples in spec form, showing the decisions made, the defaults rejected, and the resulting system behavior.

---

## Principles

| Principle | What it rejects |
|-----------|----------------|
| Constraint-First Design | Feature-first design with guardrails added later |
| Continuity | Explicit memory, named sessions, user-managed workspaces |
| Agent Restraint | Persistent proactive suggestions, always-on assistance |
| Community Disagreement | Synthesis of contested answers into a single AI voice |

---

## System steps

| Step | Output |
|------|--------|
| 01 — Reframe | The structural problem underneath the stated one |
| 02 — Failure Behavior | System response in every state where the default fails |

---

## How to read this repo

Principles constrain system behavior. System steps apply those constraints to real problems. Examples show the result.

If a principle does not appear in system behavior, it is not real.

Examples are de-identified representations of real system decisions. They preserve the decision logic without exposing product-specific details.

The bar for any file in this repo: does it reject a default currently shipping in the AI product category, and would a reasonable designer disagree with it? If a file reads like generic design advice that could apply to any era or any product, it does not belong here.

---

## Background

This system was developed through three years of designing AI-powered search and discovery products at scale — working directly with ML and engineering to specify system behavior under real constraints. The principles are not theoretical. They are what I actually apply before opening Figma.
