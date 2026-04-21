# Principle — Continuity

## The rule

The system tracks inquiry continuity without requiring the user to name, save, or organize anything.

Memory is implicit. Sessions are inferred. Resume replaces restart.

---

## Why this exists

Every major AI product ships explicit memory as a headline feature: ChatGPT Projects, Claude Projects, Perplexity Spaces, Notion workspaces, Arc Spaces. All of them require setup, naming, and organization. All of them have the same adoption shape — high visibility among power users, low reach across the actual user base.

The setup cost is not a marketing problem. It is the product. Asking a user to create and name a container before they do the thing is asking them to become an operator of the system. On mobile, where casual seeking dominates, that ask collapses use.

Implicit continuity inverts this. The system observes behavior and reconstructs context on return. The user never organizes. The system does the organizing work invisibly, and only surfaces structure when the user's state warrants it.

---

## What continuity requires

**No setup.** No "create a new session" CTAs. No onboarding that teaches a new mental model. The first interaction is the same as the hundredth.

**No naming.** The system never asks the user to label an inquiry. Labels, when they exist, are generated from content and are editable — but never required.

**No organization.** No folder trees, no manual tagging, no workspace selection. Grouping is automatic. If the user wants to find a past inquiry, the system's search and surfacing behavior handles it.

**Resume over restart.** When the user returns, the system reconstructs prior state — scroll position, inquiry context, related threads — before requiring any decision. Around 12 seconds of visual orientation, not an immediate action prompt.

---

## What continuity is not

Continuity is not long-term behavioral personalization. It is not a recommender profile. It does not predict what the user will want based on historical patterns across months.

Continuity is about the current inquiry and recent return state. Short horizon. High specificity. The system remembers what the user was doing, not who the user is.

This distinction matters because long-term profile-based personalization triggers a different set of costs — trust erosion, privacy concerns, account-switching friction. Keeping continuity short-horizon avoids all of them while solving the actual problem.

---

## Failure mode if violated

Adoption stalls at the power-user tier. The feature looks successful in dashboards that count power users. It fails to move the metrics that matter — reach, retention across cohorts, return rate for casual users.

This is the documented failure shape of every explicit-memory product in the category. The pattern is not hypothetical.

---

## Opposing view (shipped)

- ChatGPT Projects: user-created, user-named, user-managed
- Claude Projects: explicit containers with setup flow
- Perplexity Spaces: named workspaces as headline feature
- Notion AI: workspace-first organization
- Arc Spaces: explicit space creation and switching

The entire category ships explicit memory. Implicit continuity is the minority position.
