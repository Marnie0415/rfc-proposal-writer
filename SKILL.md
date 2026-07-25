---
slug: rfc-proposal-writer
name: rfc-proposal-writer
displayName: RFC / Proposal Writer
version: 1.3.0
summary: 从粗略想法生成RFC、ADR和技术提案
description: "Use when the user wants to write an RFC, ADR, or proposal. Triggers on 'write RFC', 'create ADR', 'draft proposal'."
license: MIT
---

# RFC / Proposal Writer

Generates structured technical documents with project context awareness.

## When to use

- Write RFC for new feature
- Create Architecture Decision Record
- Draft project proposal

## When NOT to use

- Writing code
- Project tickets
- Meeting minutes

## Workflow

### Step 1: Understand context deeply

Read the request AND the project:

```
read <file_path>
```

Gather project context:

```
read README.md
read package.json  # or requirements.txt, go.mod, etc.
glob **/*.md       # find existing docs
grep -r "TODO\|FIXME" --include="*.py" .  # find known issues
```

### Step 2: Determine document type and scope

- **RFC**: Large feature or system change → full structure
- **ADR**: Single decision → concise format
- **Proposal**: Project with timeline → success criteria focus

Ask the user:
- "What's the scope?" (single service / entire system)
- "Any existing docs I should reference?"
- "Who will review this?"

### Step 3: Generate with project context

Reference gathered context:
- Existing architecture decisions
- Current tech stack
- Known constraints
- Team conventions

### Step 4: Generate review checklist

After the document, add a review checklist:

```markdown
## Review Checklist

- [ ] Problem statement is clear
- [ ] Alternatives are documented
- [ ] Tradeoffs are explicit
- [ ] Implementation plan has milestones
- [ ] Security considerations addressed
- [ ] Rollback strategy defined
```

### Step 5: Multi-turn iteration

- User says "Add more detail to Tradeoffs" → expand section
- User says "The timeline is wrong" → adjust dates
- User says "Include cost analysis" → add cost section
- User says "Simplify" → reduce to essentials

### Step 6: Save

```
write rfc-proposal.md <document>
```

## Error handling

- **Input too vague**: Ask one clarifying question
- **No code context**: Use generic templates, flag assumptions
- **Multiple decisions**: Create separate documents
