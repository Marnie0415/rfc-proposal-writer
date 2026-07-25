# RFC / Proposal Writer

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.txt)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-D97757)](SKILL.md)
[![Codex](https://img.shields.io/badge/Codex-Skill-000000)](SKILL.md)
[![Version](https://img.shields.io/badge/Version-1.0.0-blue)]()

> Generate RFCs, ADRs, and technical proposals from rough ideas.

## What it does

Takes a rough idea or problem description and produces a structured RFC, Architecture Decision Record (ADR), or project proposal. Includes tradeoff analysis, implementation plan, security considerations, and open questions.

## Why this exists

Writing good RFCs and proposals takes practice. Most engineers struggle with structure, tradeoff analysis, and what to include. This skill provides the exact framework used by top tech companies — every document follows the standard format with all required sections.

## Quick start

```text
# In Claude Code or Codex
Use the rfc-proposal-writer skill
```

```bash
cp -r rfc-proposal-writer ~/.claude/skills/
```

## Three document types

### RFC (Request for Comments)
For proposing new features or system changes.

```
Summary → Motivation → Detailed Design → Tradeoffs
  → Implementation Plan → Security → Open Questions
```

### ADR (Architecture Decision Record)
For documenting technical decisions.

```
Title (ADR-NNNN) → Status → Context → Decision → Consequences
```

### Proposal
For project proposals with success criteria.

```
Problem Statement → Solution → Success Criteria
  → Risks & Mitigations → Timeline
```

## What you get

| Input | Output |
|-------|--------|
| "We need caching" | Full RFC with Redis design, tradeoffs, 3-phase plan |
| "PostgreSQL vs MySQL" | ADR with scoring matrix, decision, consequences |
| "Build deployment tool" | Proposal with criteria, risks, 6-week timeline |

## Acknowledgments

README structure inspired by [sovereign-skills](https://github.com/AlexZio00/sovereign-skills), [claude-code-skills](https://github.com/levnikolaevich/claude-code-skills), and [html-to-editable-pptx](https://github.com/Hasasasa/html-to-editable-pptx). All referenced projects are MIT licensed.

## License

MIT
