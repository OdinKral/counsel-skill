# The Philosophy Behind Council

## Why This Exists

Most AI chat interactions are one-dimensional: you ask, the AI answers, you evaluate. But real thinking — the kind that changes decisions — usually involves multiple perspectives in tension. A good team meeting isn't good because everyone agrees. It's good because the engineer sees what the strategist missed, and the critic catches what the optimist glossed over.

Council recreates that dynamic with AI. Not by making the AI smarter, but by giving it **distinct lenses** to think through.

## The Two-Layer Architecture

Every archetype has two layers:

**Protocol** — the structural role. What kind of thinking does this voice contribute? The Critic detects bias. The Oracle models futures. The Engineer decomposes problems. These are functions, not personalities.

**Persona** — the character voice. Murderbot's dry exasperation. Mark Watney's wry pragmatism. The Bobs' nerdy enthusiasm for exploring possibility space. These make each voice distinct, memorable, and — crucially — hard to accidentally blend together.

The protocol is *what* the voice does. The persona is *how* it sounds. They're deliberately separate because:

- You might want the Critic's function with a different voice
- The persona prevents the AI from producing five versions of the same generic analysis
- Character grounding produces more distinct, committed responses than abstract role descriptions

## Intellectual Roots

### The Bitter Lesson (Rich Sutton, 2019)

Sutton showed that general computational methods consistently outperform hand-crafted domain knowledge as compute scales. This shapes Council's design:

- Archetype files describe **what** each voice contributes, not **how** to generate it
- Workflows specify **outcomes**, not **procedures**
- As models improve, the same archetype files produce better results — no rewiring needed
- The system is designed to get *looser* over time, not tighter

### The Missing Half (Guy Freeman, 2026)

Freeman argued that Sutton's Bitter Lesson addresses capability but not purpose. You can scale compute infinitely, but you still need a **utility function** — a way to decide whether the next unit of computation is worth its cost.

This directly inspired the **Session Value Retro**:

```
- Action taken: [yes/no]
- Insight I wouldn't have reached alone: [yes/no]
- Right team for this question: [yes/no]
```

Three questions. Binary answers. This is the utility function for the thinking partner system. It doesn't optimize anything mathematically — it makes *taste* legible over time. After enough sessions, you can see: "Full councils on implementation questions produce no action. Pipe to the Engineer instead."

The question *"Is this next session worth having?"* is itself a decision-theoretic problem. The retro generates the data to answer it.

### The Unix Philosophy

> "Write programs that do one thing and do it well. Write programs to work together."
> — Doug McIlroy

Council treats archetypes like Unix tools:

- **Each archetype does one thing.** The Critic detects weakness. The Oracle models futures. They don't overlap.
- **They compose.** Pipe a topic to the Oracle alone, or assemble Oracle + Engineer for a focused working session, or run the full council.
- **The integration is thin.** The archetypes are markdown files. The platform (Claude Code, ChatGPT, Ollama) is just the pipe. Swap the platform, keep the archetypes.

This was directly inspired by the [Unix Manifesto for the Age of AI](https://linuxtoaster.com/manifesto.html), which argues that as AI removes friction from creation, **taste — the sustained refusal of unnecessary complexity** — becomes the only safeguard against entropy.

### Cybernetic Feedback Loops

> "No agency without feedback. No visibility, no trust."

The three-phase cycle (Brief → Session → Retro) is a cybernetic control loop:

1. **Observe** the terrain (Pre-Brief)
2. **Act** with the right team (Session)
3. **Measure** the result (Retro)
4. **Adjust** future team selection based on evidence (Meta Review)

Without the retro, you're running meetings with no way to know if they're productive. The system must observe its own effectiveness — otherwise it drifts toward theater.

### Composability Over Configuration

The old design had rigid meeting formats: Council (4 voices), War Council (5-6 voices), or nothing. The new design treats it like assembling a project team:

- "I need to think through this with the Engineer and Oracle" → Flex Team
- "Quick question for the Critic" → Pipe
- "This is big and uncertain, let's get everyone" → Full Council

This mirrors how real teams work. You don't pull 6 people into a room to answer a question that one person could handle. And you don't try to solve a multi-dimensional problem alone when three perspectives would help.

## The Role of Character Voice

Why Murderbot? Why Mark Watney? Why not just "Critical Thinking Agent" and "Problem Decomposition Agent"?

Three reasons:

1. **Distinctness.** When the AI generates responses from abstract role descriptions, the voices tend to blur. "The critical thinker identified risks while the strategic thinker proposed a plan" — that's one voice wearing two hats. Murderbot and Jocko Willink don't sound alike. They can't accidentally merge.

2. **Commitment.** A well-drawn character commits to their perspective. Murderbot doesn't soften criticism to be polite. Mr. Money Mustache doesn't hedge when simplification is the answer. The character voice creates a kind of constructive stubbornness that produces better analysis.

3. **Memorability.** When you're reviewing session notes a week later, "The Oracle found an unexpected branch" is more retrievable than "The probabilistic analysis yielded an alternative scenario." Characters create cognitive hooks.

The characters are chosen to match their archetype's function:

| Archetype | Character | Why This Match |
|-----------|-----------|---------------|
| Critic | Murderbot | Reluctant competence. Sees everything, would rather not intervene, but cares enough to when it matters. |
| Coach | Mr. Money Mustache | Radical simplification. Strips complexity to find the one lever. Tough love with humor. |
| Oracle | The Bobs (Bobiverse) | Self-replicating exploration. Each scenario is a "copy" sent to investigate a timeline. Nerdy, warm, rigorous. |
| Engineer | Mark Watney | Survival through decomposition. "What kills me next? What do I have? What's the fix?" |
| Strategist | Jocko Willink | Ownership, terrain, decisive action. "Good." Every setback is a direction. |
| Sage | *Unassigned* | Still finding the right voice for meta-cognitive regulation. Candidates: Stephen Jay Gould, others. |

## Adaptation

This system is designed to be forked. The archetypes reflect one person's thinking style and intellectual influences. Yours will be different.

**What to keep:**
- The Protocol/Persona separation
- The composable invocation model (pipe, flex team, council)
- The Session Value retro (the learning mechanism)
- The three-phase cycle

**What to change:**
- The character voices — pick characters that resonate with you
- The number and type of archetypes — maybe you need a "Devil's Advocate" or a "Historian"
- The workflows — adapt to your platform and preferences
- The team selection heuristics — these should emerge from your own retro data

**What not to add:**
- Complexity. If you find yourself adding archetypes "just in case," you're drifting. Start with 2-3. Add one only when you notice a gap in multiple sessions.
- Rigid procedures. The workflows are guides, not scripts. Better models will need less scaffolding, not more.

## The Meta-Insight

The most interesting thing about this system is that it applies its own principles to itself:

- The **Bitter Lesson** says: specify outcomes, not procedures. So the archetypes describe *what* each voice contributes, not *how* to generate it.
- The **Unix Philosophy** says: composable tools beat monolithic platforms. So the archetypes are individual files that compose flexibly, not a single prompt.
- **Freeman's Missing Half** says: you need a utility function. So the Session Value retro makes the system's own effectiveness measurable.
- The **Unix Manifesto** says: taste is sustained refusal. So the system explicitly asks "who's NOT needed?" in every Pre-Brief, and the Sage's job is to identify what to remove.

The system teaches you to think about thinking. And then it measures whether the thinking was worth doing.

---

*"The best meeting is the one you didn't need to have. The second best is the one with exactly the right people in the room."*
