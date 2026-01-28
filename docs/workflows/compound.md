# Compound Documentation Workflow

How to document solved problems for future reference.

## What is Compound Documentation?

When you solve a non-trivial problem, document the solution so it can be reused. This creates a knowledge base that compounds over time.

## When to Document

- Solved a tricky bug
- Found a non-obvious approach
- Integrated a new service or library
- Established a pattern others should follow

## Solution Document Format

Create a file in `docs/solutions/` named descriptively:

```markdown
# Problem Title

## Context
What situation led to this problem?

## Problem
What was the specific issue?

## Solution
How did we solve it?

## Code Example
```<language>
// Relevant code snippet
```

## Key Learnings
- What did we learn?
- What would we do differently?

## References
- Links to relevant docs, issues, or discussions
```

## Naming Convention

Use descriptive kebab-case names:
- `handling-auth-token-refresh.md`
- `postgres-connection-pooling.md`
- `react-form-validation-pattern.md`

## Keeping Solutions Updated

- Review when related code changes
- Archive outdated solutions
- Link to solutions from code comments when helpful

## Tips

- Write solutions while the context is fresh
- Include enough detail that someone unfamiliar could understand
- Keep examples minimal but complete
- Update CLAUDE.md if the solution represents a project pattern
