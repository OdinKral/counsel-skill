# Council — Composable AI Thinking Partners

A structured thinking partner framework using 5 AI archetypes that can be invoked individually, in flexible teams, or as a full council. Works with any LLM.

**The core idea:** You have 5 coworkers with distinct expertise. You don't invite all 5 to every meeting. You pick the right people for the problem.

## The Archetypes

| Archetype | Voice | What They Do |
|-----------|-------|-------------|
| **Critic** | Murderbot (Martha Wells) | Detects delusion, bias, and weak thinking. Surgical, not cruel. |
| **Coach** | Mr. Money Mustache | Finds leverage, strips complexity, demands action. Tough love with humor. |
| **Oracle** | The Bobs (Bobiverse) | Models futures, maps trade-offs, reveals second-order effects. Probabilistic, not prophetic. |
| **Engineer** | Mark Watney (The Martian) | Decomposes problems, inventories resources, builds from constraints. |
| **Strategist** | Jocko Willink | Maps terrain, identifies decisive points, enforces ownership. |
| **Sage** | *(unassigned)* | Meta-cognitive regulator. Detects drift, overcomplication, and pattern decay across sessions. |

Each archetype has a **Protocol** (what they do structurally) and a **Persona** (how they sound). The protocol is the function. The persona makes it memorable and distinct.

## Invocation Modes

From lightweight to heavyweight:

| Mode | Team Size | When to Use |
|------|-----------|-------------|
| **Pipe** | 1 voice | You know exactly what kind of thinking you need |
| **Flex Team** | 2-4 voices | Multi-dimensional problem, but you don't need everyone |
| **Council** | 4 voices | Open exploration — you're not sure what you don't know |
| **War Council** | 5-6 voices | Irreversible, high-stakes, emotionally charged |

## Three-Phase Session Cycle

```
PRE-BRIEF → SESSION → RETRO
   ↓           ↓         ↓
Scan topic   Voices     "Was this
& recommend  work the   worth it?"
the team     problem    3 questions
```

1. **Pre-Brief** (optional): The Oracle scans the situation and recommends which archetypes to involve
2. **Session**: The selected voices work the problem — individually (pipe), conversationally (flex team), or in sequence (council)
3. **Retro** (48 hours later): Three yes/no questions that track whether the session produced value

The retro data feeds back into future pre-briefs, improving team selection over time.

## Quick Start

### Option 1: Copy-paste (any LLM)

1. Pick an archetype from `archetypes/` that matches your question
2. Paste its contents into your LLM's system prompt or context
3. Ask your question
4. That's it

### Option 2: Full session (any LLM)

1. Paste the archetype files you want into context
2. Add the workflow instructions from `workflows/` for your chosen mode
3. Frame your question with: what it is, what you already know, what kind of help you need
4. Let the voices work

### Option 3: Platform integration

See `integrations/` for platform-specific setup:
- **Claude Code**: Full skill integration with auto-save and memory
- **ChatGPT**: Custom GPT configuration
- **Ollama / Local LLMs**: Shell scripts for CLI piping

## The Session Value Retro

Every session ends with three questions:

```
## Session Value (fill within 48 hours)

- Action taken: [yes/no]
- Insight I wouldn't have reached alone: [yes/no]
- Right team for this question: [yes/no] (who was missing / who wasn't needed?)
```

This is the system's learning mechanism. After 5-6 sessions, patterns emerge: which team compositions produce action vs. theater, which problem types need more voices vs. fewer. The Sage consumes this data during Meta Reviews.

## File Structure

```
counsel-skill/
├── README.md              ← You are here
├── PHILOSOPHY.md          ← Why this system exists and how it thinks
├── OperatorsManual.md     ← How to be a good session host
├── archetypes/
│   ├── Critic.md          ← Murderbot — epistemic defense
│   ├── Coach.md           ← Mr. Money Mustache — activation energy
│   ├── Oracle.md          ← The Bobs — probabilistic foresight
│   ├── Engineer.md        ← Mark Watney — practical decomposition
│   ├── Sage.md            ← Meta-cognitive regulator
│   └── Strategist.md      ← Jocko Willink — external maneuver
├── workflows/
│   ├── FlexTeam.md        ← Custom team composition
│   ├── CouncilSession.md  ← Standard 4-voice council
│   ├── WarCouncil.md      ← High-stakes 5-6 voice council
│   ├── PreBrief.md        ← Situational scan + team recommendation
│   ├── MetaReview.md      ← Pattern analysis across sessions
│   ├── ValuesAlignmentReview.md
│   └── OperationsReview.md
├── integrations/
│   ├── claude-code/       ← SKILL.md for Claude Code users
│   ├── chatgpt/           ← Custom GPT setup guide
│   └── ollama/            ← Local LLM shell scripts
└── examples/
    └── oracle-pipe-session.md
```

## Design Principles

1. **Archetypes are data, not code.** Markdown files that any LLM can read. The thinking framework is portable; the platform integration is replaceable.

2. **Composable, not monolithic.** Pick the voices you need. Don't invoke the whole team when one person will do. Unix philosophy applied to thinking partners.

3. **Feedback loops, not faith.** The Session Value retro makes taste legible. You don't have to believe the system works — you measure it.

4. **The human decides.** The voices advise. The council recommends. You own the decision. Always.

5. **Specify what, not how.** The archetypes describe *what kind of thinking* each voice contributes, not *how* to generate it. Better models produce better results from the same archetype files.

See [PHILOSOPHY.md](PHILOSOPHY.md) for the full intellectual lineage.

## Credits

Built by Bryan Kral as part of the [PAI (Personal AI Infrastructure)](https://github.com/OdinKral) project.

Intellectual influences: Martha Wells, Dennis E. Taylor, Andy Weir, Pete Adeney, Jocko Willink, Daniel Kahneman, Nassim Taleb, Donella Meadows, Rich Sutton (Bitter Lesson), Guy Freeman (Bitter Lesson's Missing Half), the Unix philosophy.

## License

MIT — use it, fork it, adapt the archetypes to your own thinking style.
