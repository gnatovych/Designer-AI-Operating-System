# Principle — Constraint-First Design

## The rule

Define what the system is NOT before defining what it is.

Anti-goals before goals. Boundaries before behaviors.

---

## Why this exists

In AI product design, the failure modes are more important than the features. A system that does the right thing 90% of the time and the wrong thing 10% of the time in high-stakes moments is not a good system. It is a liability.

Designers who start with what a system should do produce systems optimized for the happy path. Designers who start with what a system should never do produce systems that hold up under real conditions.

Constraints also prevent scope creep more reliably than roadmaps. When a team has agreed on what the system will not do, every feature proposal can be evaluated against that boundary. The constraint does governance work.

---

## What changes in practice

**Without constraint-first thinking:**

> "The AI should answer questions about health topics helpfully and accurately."

This produces a system that tries to be maximally helpful. It answers confidently. It fills gaps. It sounds authoritative. Users trust it more than they should.

**With constraint-first thinking:**

> "The system will NOT: provide specific dosage recommendations, diagnose conditions, or present synthesized content as equivalent to professional advice. Given these constraints, what should it do?"

This produces a system that knows where its boundaries are. It can be helpful within those boundaries without pretending to be something it isn't.

---

## How to apply it

Before designing any AI behavior, complete this structure:

**This system will never:**
[List 3-5 hard constraints — things the system must not do regardless of user request]

**This system will not try to:**
[List 2-3 soft constraints — things outside the system's intended scope]

**Given these constraints, this system will:**
[Now define the positive behaviors]

---

## The constraint artifact

Constraints only do governance work if they are written down and referenced. A verbal commitment to what the system will not do is not a constraint — it is a preference.

The artifact looks like this:

**❌ The system will not:**
- Generate dosage recommendations
- Present synthesis as equivalent to professional advice
- Answer questions requiring real-time data from training knowledge

**✅ The system will:**
- Surface professional sources with attribution
- Route to verified information when specificity is required
- Decline and explain when the question exceeds reliable scope

This artifact is referenced in every feature review. When a proposal violates a ❌, the proposal changes or the ❌ changes — never both silently.

---

## Constraint as veto

Constraints are not guidelines. They are decision boundaries.

**Example:**

*Constraint:* The system will not synthesize opinion without visible attribution.

*Feature proposal:* "Show a single AI recommendation for restaurants."

*Decision:* Rejected — violates attribution constraint.

*Outcome:* System surfaces multiple attributed opinions instead.

If a constraint cannot reject a feature, it is not a constraint.

The veto is also a redirect of responsibility. When the constraint does the work of saying no, the conversation shifts from "I don't think we should" to "this violates a commitment we made." That shift is the entire reason constraints exist as an artifact.

---

## The constraint types

**Safety constraints** — what the system must not do because harm results if it does
Example: never present AI-generated content as equivalent to expert professional advice

**Trust constraints** — what the system must not do because trust breaks if it does
Example: never surface a synthesized answer without visible attribution to source material

**Scope constraints** — what the system must not attempt because it cannot do it reliably
Example: never answer questions requiring real-time data using only training knowledge

**Organizational constraints** — what the system must not do because of business, legal, or policy reasons
Example: never surface competitor content in a branded discovery experience

---

## When to use this

- Defining behavioral rules for any AI system
- Scoping a new product area where the boundaries are unclear
- Evaluating a feature request against existing system commitments
- Alignment conversations with engineering and ML about what the system will and won't do

