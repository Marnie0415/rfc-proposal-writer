---
slug: rfc-proposal-writer
name: rfc-proposal-writer
displayName: RFC / Proposal Writer
version: 1.2.0
summary: 从粗略想法生成RFC、ADR和技术提案
description: "Use when the user wants to write an RFC, ADR, or proposal. Triggers on 'write RFC', 'create ADR', 'draft proposal'."
license: MIT
---

# RFC / Proposal Writer

Generates structured RFCs, ADRs, and proposals from rough ideas.

## When to use

- Write RFC for new feature
- Create Architecture Decision Record
- Draft project proposal

## When NOT to use

- Writing code
- Project tickets
- Meeting minutes

## Workflow (follow these exact steps)

### Step 1: Understand the request

Read user's input or file:

```
read <file_path>
```

### Step 2: Determine document type

- **RFC**: Proposing features/system changes
- **ADR**: Documenting a specific decision
- **Proposal**: Project with success criteria

### Step 3: Gather code context (if needed)

Use `grep` to understand the codebase:

```
grep <pattern> <directory>
```

Use `glob` to find relevant files:

```
glob **/<pattern>*
```

### Step 4: Generate document

Follow the appropriate template (RFC/ADR/Proposal).

### Step 5: Save

```
write rfc-proposal.md <document_content>
```

Tell user: "Document saved to rfc-proposal.md"

## Error handling

- **Input too vague**: Ask one clarifying question
- **Ambiguous type**: Ask RFC or ADR
- **No code context**: Use generic templates, flag assumptions
