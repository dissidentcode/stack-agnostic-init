# Project Template

A Claude Code project template with interactive initialization.

## Getting Started

1. **Clone this repository**
   ```bash
   git clone <template-url> my-project-name
   cd my-project-name
   ```

2. **Remove the template's git history** (optional, for fresh start)
   ```bash
   rm -rf .git
   git init
   ```

3. **Open with Claude Code**
   ```bash
   claude
   ```

4. **Run the initialization command**
   ```
   /init
   ```

## What Happens During Initialization

Claude will conduct a brief interview about your project:

- **Project Identity** - Name, description, target users
- **Technical Stack** - Language, framework, database, services
- **Development Workflow** - Branching, testing, linting preferences
- **Collaboration Style** - How you want Claude to work with you

Based on your answers, Claude generates:

- Customized `CLAUDE.md` with project-specific guidance
- Updated `README.md` with setup instructions
- Stack-specific `.gitignore` patterns
- Directory structure matching your project type
- Minimal starter code scaffolding

## Template Contents

```
project-template/
├── .claude/
│   ├── settings.json
│   └── commands/
│       └── init.md          # The initialization command
├── docs/
│   ├── plans/               # Implementation plans
│   ├── solutions/           # Documented solutions
│   └── workflows/           # Reference workflows
├── CLAUDE.md                # Project context for Claude
├── AGENTS.md                # Agent working guidelines
└── README.md                # This file
```

## After Initialization

The `/init` command archives itself to `docs/archive/` after completing setup. Your project is then ready for development with Claude Code.
