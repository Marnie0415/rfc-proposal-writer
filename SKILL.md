---
slug: rfc-proposal-writer
name: rfc-proposal-writer
displayName: RFC / Proposal Writer
version: 1.1.0
summary: 从粗略想法生成RFC、ADR和技术提案
description: "Use when the user wants to write an RFC, ADR, or proposal. Triggers on 'write RFC', 'create ADR', 'draft proposal'."
license: MIT
---

# RFC / Proposal Writer

Generates structured RFCs, ADRs, and project proposals from rough ideas.

## When to use

- Write an RFC for a new feature
- Create an Architecture Decision Record
- Draft a project proposal

## When NOT to use

- Writing code
- Creating project tickets
- Meeting minutes

## Workflow

### Step 1: Understand the request

Use `read` tool if the user provides a file:

```
read <file_path>
```

Or work with the problem description they paste.

### Step 2: Determine document type

- **RFC**: Proposing new features or system changes
- **ADR**: Documenting a specific technical decision
- **Proposal**: Project proposal with success criteria

### Step 3: If code context is needed

Use `grep` to understand the codebase:

```
grep <pattern> <directory>
```

Use `glob` to find relevant files:

```
glob **/<relevant_pattern>*
```

This helps fill in real project context instead of generic templates.

### Step 4: Generate the document

Follow the appropriate template:

**RFC structure:**
```markdown
## Summary
One paragraph.

## Motivation
Why this needs to exist.

## Detailed Design
How it works (APIs, data flows, components).

## Tradeoffs
Alternatives considered and why this was chosen.

## Implementation Plan
Phases, timeline, dependencies.

## Security Considerations
Risks and mitigations.

## Open Questions
What's still undecided.
```

**ADR structure:**
```markdown
## Title: ADR-NNNN: [Decision]
## Status: Proposed | Accepted
## Context: What's the problem
## Decision: What we're doing
## Consequences: What becomes easier/harder
```

### Step 5: Save the document

```bash
write rfc-proposal.md <document_content>
```

## Error handling

- **Input too vague**: Ask one clarifying question about the core problem
- **Ambiguous type**: Ask RFC or ADR
- **Multiple decisions**: Ask user to pick one, or create separate docs
- **No code context**: Use generic templates, flag assumptions with `[ASSUMPTION: ...]`

## Known limitations

- Cannot access external documentation or APIs
- Tradeoff analysis is general knowledge, not project-specific
- Does not track document versions or revisions
- Not a substitute for team review and discussion
