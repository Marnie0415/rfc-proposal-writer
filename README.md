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

## Prerequisites

- Claude Code, Codex, or any LLM agent that supports SKILL.md
- Git (to clone the repository)
- No Python, Node.js, or other runtime required

## Installation

### Step 1: Clone the repository

```bash
git clone https://github.com/Marnie0415/rfc-proposal-writer.git
```

### Step 2: Copy to your skills directory

**macOS / Linux:**

```bash
# For Claude Code
cp -r rfc-proposal-writer ~/.claude/skills/

# For Codex
cp -r rfc-proposal-writer ~/.codex/skills/
```

**Windows (PowerShell):**

```powershell
# For Claude Code
Copy-Item -Path "rfc-proposal-writer" -Destination "$env:USERPROFILE\.claude\skills\rfc-proposal-writer" -Recurse

# For Codex
Copy-Item -Path "rfc-proposal-writer" -Destination "$env:USERPROFILE\.codex\skills\rfc-proposal-writer" -Recurse
```

### Step 3: Restart your agent

Restart Claude Code or Codex to pick up the new skill.

## Usage

In Claude Code or Codex, simply ask:

```text
Write an RFC for my caching proposal
```

The agent will automatically detect and use this skill.

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
