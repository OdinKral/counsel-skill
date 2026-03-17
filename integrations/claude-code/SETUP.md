# Council on Claude Code

Full integration as a Claude Code skill with auto-save, memory, and natural language triggering.

## Installation

1. Copy the `SKILL.md` file to your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/Council/Workflows
cp SKILL.md ~/.claude/skills/Council/
cp Workflows/*.md ~/.claude/skills/Council/Workflows/
```

2. Copy archetype files to your knowledge base (adjust path to your preference):

```bash
mkdir -p ~/knowledge/archetypes
cp archetypes/*.md ~/knowledge/archetypes/
```

3. Update the archetype paths in the workflow files to match your directory structure. Search for `/path/to/archetypes/` and replace with your actual path.

## Configuration

### Workflow Path References

Each workflow file references archetype paths. Update these to match your setup:

```markdown
# In each workflow file, update paths like:
/path/to/archetypes/Critic.md
/path/to/archetypes/Coach.md
# etc.
```

### Auto-Save (Optional)

The workflows save session outputs to a configurable directory. Set your preferred save location in each workflow's "Auto-Save" section:

```markdown
# Default save locations:
Sessions: ~/knowledge/sessions/
War Council: ~/knowledge/war-council/
Meta Reviews: ~/knowledge/meta-reviews/
```

### MemoryVault (Optional)

If you have a vector memory system, the workflows include optional MemoryVault integration for semantic search across past sessions. Remove or replace these sections if you use a different memory system.

## Usage

Claude Code's skill system triggers Council automatically from natural language:

```
"oracle: what if we delay?"           → Pipe mode
"bring in the critic and engineer"    → Flex Team
"council: should we refactor?"        → Full Council
"war council: should we pivot?"       → War Council
"pre-brief: MyProject"                → Situational scan + team recommendation
"meta review"                         → Sage pattern analysis
```

## Features Unique to Claude Code

- **Auto-save**: Sessions automatically saved as markdown files
- **Natural language triggering**: No commands needed — just talk naturally
- **Pre-Brief scanning**: Oracle can scan git history, test status, and recent sessions
- **MemoryVault integration**: Semantic search across past council outputs
- **Session Value retro**: Embedded in every session output for longitudinal tracking

## Adapting the SKILL.md

The included `SKILL.md` is the full specification used in the original PAI system. You'll want to:

1. Update file paths to match your directory structure
2. Remove MemoryVault references if you don't use one
3. Adjust the description field trigger words to match your vocabulary
4. Review the workflow files and simplify any sections that don't apply to your setup
