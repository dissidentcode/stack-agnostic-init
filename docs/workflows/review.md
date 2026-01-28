# Review Workflow

How to review code changes effectively.

## Self-Review Checklist

Before requesting review, check:

- [ ] Code does what it's supposed to do
- [ ] Tests pass
- [ ] No obvious bugs or edge cases missed
- [ ] Code is readable and well-organized
- [ ] No debug code or temporary hacks left in
- [ ] Documentation updated if needed

## Reviewing Others' Code

### What to Look For

**Correctness**
- Does it solve the stated problem?
- Are edge cases handled?
- Could it break existing functionality?

**Clarity**
- Is the code easy to understand?
- Are variable/function names descriptive?
- Is the logic straightforward?

**Maintainability**
- Is it easy to modify in the future?
- Does it follow project conventions?
- Is there appropriate test coverage?

### Giving Feedback

- Be specific about what needs to change
- Explain why, not just what
- Distinguish between required changes and suggestions
- Acknowledge what's done well

### Feedback Format

```
[Required/Suggestion] <description>

<explanation of why>
```

## Responding to Feedback

- Assume good intent
- Ask for clarification if needed
- Address all comments before re-requesting review
- Thank reviewers for their time

## Tips

- Review in small chunks - large PRs are hard to review well
- Take breaks if reviewing a lot of code
- Focus on important issues, not style nitpicks
