---
slug: rfc-proposal-writer
name: rfc-proposal-writer
displayName: RFC / Proposal Writer
version: 1.0.0
summary: 从粗略想法生成RFC、ADR和技术提案
description: "Use when the user wants to write an RFC, create a design doc, draft a proposal, make an ADR, or document a technical decision. Triggers on 'write an RFC', 'create a design doc', 'draft a proposal', 'make an ADR', 'help me decide between', or when the user needs structured technical documentation."
license: MIT
---

# RFC / Proposal Writer

Generates structured RFCs, technical design documents, architecture decision records (ADRs), and project proposals from rough ideas or requirements.

## When to use

- Write an RFC for a new feature or system change
- Create an Architecture Decision Record (ADR)
- Draft a project proposal with success criteria
- Document a technical decision with tradeoff analysis

## When NOT to use

- Writing code or implementation
- Creating project management tickets or issues
- Generating meeting minutes or action items
- Writing legal contracts or compliance documents
- Creating marketing materials or sales pitches

## Workflow

1. Determine document type: RFC, ADR, or proposal.
2. Extract the core problem or decision from the input.
3. Generate the appropriate structure for that document type.
4. Fill in each section with concrete details.
5. Flag assumptions and open questions.
6. Output clean Markdown.

## Document types

### RFC Structure
1. **Summary**: One paragraph. What is this RFC about and what does it propose?
2. **Motivation**: Why does this need to exist? What problem does it solve?
3. **Detailed Design**: How does the proposed solution work? Include APIs, data flows.
4. **Tradeoffs**: What are the alternatives? Why was this approach chosen?
5. **Implementation Plan**: Phases, timeline, dependencies, rollback strategy.
6. **Security Considerations**: Security implications and mitigations.
7. **Open Questions**: What is still undecided?

### ADR Structure
1. **Title**: ADR-NNNN: [Decision Title]
2. **Status**: Proposed | Accepted | Deprecated | Superseded
3. **Context**: What is the issue that motivates this decision?
4. **Decision**: What is the change being proposed or decided?
5. **Consequences**: What becomes easier or harder? What tradeoffs are accepted?

### Proposal Structure
1. **Problem Statement**: One to two sentences. What needs to be solved?
2. **Proposed Solution**: What specifically are we building/changing?
3. **Success Criteria**: How do we know this worked? Measurable outcomes.
4. **Risks and Mitigations**: What could go wrong? How do we handle it?
5. **Timeline**: Key milestones and dependencies.

## Style rules

- Be specific. "Reduce latency by 40%" not "improve performance."
- Every claim needs a reason. If you cannot explain why, remove it.
- State tradeoffs explicitly. No approach is free.
- Include a flip condition: what change would make us pick a different approach.
- Use numbered sections for easy reference in review comments.
- Max 2000 words. If longer, split into supporting documents.

## Handling different inputs

- **Rough idea**: Expand into full structure, flag assumptions.
- **Comparison request**: Use ADR format with scoring matrix.
- **Meeting notes**: Extract decisions and format as ADR.
- **Thin source**: Generate template with `[TODO: ...]` placeholders and ask targeted questions.

## Error handling

- **Input too vague**: Ask one clarifying question about the core problem.
- **Ambiguous type** (could be RFC or proposal): Ask user which format they prefer.
- **Multiple decisions**: Ask user to pick one, or create separate documents.
- **Non-technical topic**: Adapt language, use proposal format instead of RFC.
- **Already has a document**: Offer to review and improve instead of rewriting.

## Examples

### Example 1: Caching RFC
Input: "We need a caching layer to reduce database load"
Output: Full RFC with summary, motivation, Redis-based design, tradeoffs vs Memcached, 3-phase rollout plan, security considerations.

### Example 2: Database ADR
Input: "Should we use PostgreSQL or MySQL for the new service?"
Output: ADR with context (current pain points), decision (PostgreSQL), scoring matrix, consequences (JSONB support, learning curve).

### Example 3: Feature proposal
Input: "Build an internal tool for automated deployments"
Output: Proposal with problem statement, CI/CD solution design, success criteria (deploy time, error rate), risks, 6-week timeline.

## Known limitations

- Does not generate diagrams or architecture visuals
- Cannot access external documentation or APIs during generation
- Tradeoff analysis is based on general knowledge, not project-specific data
- Does not track document versions or maintain revision history
- Not a substitute for team review and discussion

## Output format

Clean Markdown with proper heading hierarchy and section numbering.
