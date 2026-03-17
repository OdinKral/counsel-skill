# Meta Review Workflow (Sage)

## Trigger

User says: "meta review", "sage review", or scheduled periodic review.
Optional scope: "meta review --project [name]" for project-scoped analysis.

## Desired Outcome

The Sage produces an honest assessment of cognitive patterns, archetype health, and system effectiveness across recent sessions. It analyzes Session Value retro data to identify which team compositions work best for which problem types. If multiple projects are active, it distinguishes project-specific patterns from universal principles.

BLE note: The sections below define what the review must address, not how to address it. The Sage should emphasize what matters most for the current period.

## Execution Steps

### 1. Load Sage Archetype

Read: `archetypes/Sage.md`

### 2. Gather Recent Sessions

Read the most recent session files:
- Last 5-10 council/flex-team/pipe sessions
- Last 3-5 war council sessions
- Any documented principles or lessons learned

### 3. Determine Scope

If `--project [name]` specified: filter sessions to that project only.
If no scope specified: analyze all sessions, with attention to both project-specific and cross-project patterns.

### 4. Sage Analysis

Core concerns:

1. **Recurring cognitive biases** — what patterns of bad thinking keep appearing?
2. **Overcomplication trends** — are solutions getting needlessly complex?
3. **Avoidance patterns** — what topics or decisions keep getting dodged?
4. **Risk calibration errors** — is risk being over-weighted or under-weighted?
5. **Execution vs ideation ratio** — how much thinking vs. how much doing?
6. **Identity drift** — are any archetypes losing coherence or becoming too similar?
7. **Cross-project patterns** — what principles have appeared across multiple project contexts?
8. **BLE compliance** — is the Council system itself over-scaffolded?
9. **Team composition effectiveness** — analyze Session Value retro data:
   - Which team compositions produce the highest action rate?
   - Which problem types benefit from more voices vs. fewer?
   - Are sessions being over-staffed (team too large) or under-staffed (missing voices)?
   - Are Pre-Brief team recommendations accurate?

### 5. Produce Output

```markdown
# Sage Meta-Review

**Date:** YYYY-MM-DD
**Sessions Reviewed:** [count]
**Period:** [date range]
**Scope:** [all projects / specific project name]

## Pattern Summary
[What themes and patterns keep appearing across sessions]

## Team Composition Analysis
[From Session Value retro data: which teams work best for which problems]
[Action rates by mode: pipe vs. flex team vs. council vs. war council]
[Most effective pairings. Least effective pairings.]

## Recurring Biases
[Named biases that appear repeatedly, with examples from specific sessions]

## Overcomplication Check
[Is the system or the thinker adding unnecessary complexity?]

## Execution Ratio
- Sessions reviewed: X
- Actions identified: Y
- Actions completed: Z
- Ratio: Z/Y

## Archetype Health

| Archetype | Status | Observation |
|-----------|--------|-------------|
| Critic | [healthy/drifting/overactive/underactive] | [note] |
| Coach | [healthy/drifting/overactive/underactive] | [note] |
| Oracle | [healthy/drifting/overactive/underactive] | [note] |
| Engineer | [healthy/drifting/overactive/underactive] | [note] |
| Sage | [healthy/drifting/overactive/underactive] | [note] |
| Strategist | [healthy/drifting/overactive/underactive] | [note] |

## Cross-Project Principles
[Universal patterns observed across multiple project contexts]
[Which are new — candidates for your principles list]

## BLE Check
[Is any workflow or archetype constraining rather than enabling?]

## Simplification Recommendation
[What to remove, reduce, or simplify]

## One Foundational Principle
> [The single most important thing to focus on in the next period]
```

### 6. Auto-Save

Save to your preferred meta-reviews directory:
```
meta-reviews/YYYY-MM-DD_meta-review.md
```

## Notes

- The Sage is calm, minimal, precise — no arguing, no persuading
- The Sage reports patterns — the human decides what to do about them
- Meta-reviews should be honest, even uncomfortable
- The complexity guardrail: if too much thinking and not enough action, say so
- Cross-project principles must be genuinely universal — don't force false patterns
