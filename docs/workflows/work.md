# Work Workflow

How to execute implementation systematically.

## Before Starting

1. **Understand the task** - Read any related plan or issue
2. **Check the current state** - Run tests, check git status
3. **Create a branch** - For non-trivial changes

## During Implementation

### Work Incrementally

- Make small, focused changes
- Test frequently
- Commit at logical checkpoints

### Stay Focused

- Resist scope creep
- Note related improvements for later
- Ask if requirements are unclear

### Keep Things Working

- Run tests after significant changes
- Don't leave the codebase in a broken state
- If stuck, ask for help rather than guessing

## After Completing

1. **Verify it works** - Manual testing, run test suite
2. **Review your changes** - Look for mistakes, cleanup
3. **Update documentation** - If behavior changed
4. **Commit with clear message** - Describe what and why

## Commit Message Format

```
<type>: <short description>

<optional longer description>
```

Types: `feat`, `fix`, `refactor`, `docs`, `test`, `chore`

## Tips

- Small commits are easier to review and revert
- It's okay to commit work-in-progress to a feature branch
- When in doubt, ask before making significant changes
