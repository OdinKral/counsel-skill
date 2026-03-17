---
name: Council
description: Cognitive Command Doctrine thinking partner system. USE WHEN council, war council, thinking partner, counsel, strategic decision, meta review, archetype, critic, coach, oracle, sage, strategist, engineer, values review, alignment check, telos check, operations review, process review, SOP check, pre-brief, situation report, flex team, bring in, think through with.
---

# Council — Cognitive Command Doctrine v2.0

Composable thinking partner system. 5 archetypes available as individual pipes, flexible teams, or preset formations. Three-phase session cycle: Brief → Session → Retro.

See the main repository README for full documentation. This file is the Claude Code
skill integration — it maps natural language triggers to workflow files.

## Integration Notes

To use this as a Claude Code skill:

1. Place this file at `~/.claude/skills/Council/SKILL.md`
2. Place workflow files at `~/.claude/skills/Council/Workflows/`
3. Place archetype files where your system can read them (e.g., `~/knowledge/archetypes/`)
4. Update archetype paths in workflow files to match your directory structure

## Trigger Mapping

| User Says | Mode | Workflow |
|-----------|------|----------|
| "oracle: [topic]" | Pipe | Load single archetype |
| "critic: [topic]" | Pipe | Load single archetype |
| "bring in the oracle and engineer" | Flex Team | `Workflows/FlexTeam.md` |
| "council: [topic]" | Council | `Workflows/CouncilSession.md` |
| "war council: [topic]" | War Council | `Workflows/WarCouncil.md` |
| "pre-brief: [topic]" | Pre-Brief | `Workflows/PreBrief.md` |
| "meta review" | Meta Review | `Workflows/MetaReview.md` |
| "values review" | Values | `Workflows/ValuesAlignmentReview.md` |
| "operations review" | Ops | `Workflows/OperationsReview.md` |

## Session Value Retro

All session-producing modes include a retro block. This is the system's learning mechanism.
See the main README and PHILOSOPHY.md for the reasoning behind this design.
