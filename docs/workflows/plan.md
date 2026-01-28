# Planning Workflow

How to create implementation plans for non-trivial features.

## When to Plan

- New features with multiple components
- Refactoring that touches multiple files
- Uncertain technical approaches
- Tasks estimated to take more than a few changes

## Planning Process

### 1. Understand the Goal

- What problem are we solving?
- What does success look like?
- Are there constraints or requirements?

### 2. Explore the Codebase

- Find related existing code
- Understand current patterns
- Identify what needs to change

### 3. Design the Approach

- Break down into discrete steps
- Identify risks or unknowns
- Consider alternatives

### 4. Document the Plan

Create a plan file in `docs/plans/` with:

```markdown
# Feature Name

## Goal
What we're trying to achieve

## Approach
How we'll implement it

## Steps
1. First change
2. Second change
3. ...

## Open Questions
- Any uncertainties to resolve
```

### 5. Get Feedback

Review the plan before implementing. Adjust based on feedback.

## Tips

- Keep plans focused on the what and why, not implementation details
- It's okay to update plans as you learn more during implementation
- Archive completed plans to `docs/archive/` for future reference
