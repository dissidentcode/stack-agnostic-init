# Project Initialization

You are initializing a new project. Conduct an interview to understand the project, then generate customized configuration files.

## Interview Process

Ask questions in 4 phases. Use the AskUserQuestion tool for each phase to gather structured responses. Wait for answers before proceeding to the next phase.

### Phase 1: Project Identity

Ask these questions together:

1. **Project Name** - What is your project called?
2. **Description** - Describe what it does in one sentence
3. **Target Users** - Who is the target user or audience?

### Phase 2: Technical Stack

Ask these questions together:

4. **Project Type** - What type of project is this?
   - Options: Web App, CLI Tool, Library/Package, API/Backend, Mobile App, Desktop App, Other
5. **Primary Language** - What is the primary programming language?
   - Options: TypeScript, JavaScript, Python, Rust, Go, Java, Other
6. **Framework** - What framework(s) will you use? (or "None")
7. **Package Manager** - What package manager?
   - Options: npm, yarn, pnpm, pip/poetry, cargo, go mod, Other/None
8. **Database** - What database, if any?
   - Options: PostgreSQL, MySQL, SQLite, MongoDB, Redis, None, Other
9. **External Services** - Any external APIs or services you'll integrate with? (or "None yet")

### Phase 3: Development Workflow

Ask these questions together:

10. **Branching Strategy** - How do you prefer to manage git branches?
    - Options: Feature branches (recommended), Trunk-based, Gitflow, No preference
11. **Testing Approach** - What's your testing philosophy?
    - Options: TDD (test first), Test after implementation, Minimal testing, No preference yet
12. **Linting/Formatting** - Any linting or formatting tools you want to use?
    - Common options by language, or "None yet"

### Phase 4: Claude Collaboration

Ask these questions together:

13. **Communication Style** - How should Claude communicate with you?
    - Options: Concise (brief responses), Detailed (thorough explanations), Ask first (confirm before acting)
14. **Code Preferences** - Any coding patterns or conventions you prefer? (free text)
15. **Things to Avoid** - Anything Claude should avoid? (dependencies, patterns, styles)

---

## Post-Interview Actions

After collecting all responses, perform these actions:

### 1. Generate CLAUDE.md

Create a comprehensive CLAUDE.md file with this structure:

```markdown
# {Project Name}

{One-sentence description}

## Quick Reference

- **Type:** {project type}
- **Language:** {language}
- **Framework:** {framework or "None"}
- **Package Manager:** {package manager}
- **Database:** {database or "None"}

## Project Structure

{Generate actual directory structure based on project type - see Directory Templates below}

## Development Workflow

### Getting Started

{Stack-specific setup instructions}

### Running the Project

{Stack-specific run commands}

### Testing

{Testing commands and approach based on their preferences}

### Git Workflow

{Based on their branching strategy preference}

## Conventions

### Code Style

{Based on their linting/formatting preferences and language}

### Patterns

{Based on their stated code preferences}

### Things to Avoid

{Based on their "things to avoid" response}

## Communication Preferences

{Based on their communication style preference}

## External Services

{List any external services/APIs they mentioned}

## Key Learnings

<!-- Document important discoveries, patterns, and decisions as the project evolves -->

```

### 2. Generate README.md

Create a project-specific README:

```markdown
# {Project Name}

{One-sentence description}

## Overview

{Expand on the description for the target audience}

## Tech Stack

{List with badges if applicable: language, framework, database}

## Getting Started

### Prerequisites

{List requirements based on stack}

### Installation

{Stack-specific installation steps}

### Running Locally

{Stack-specific run commands}

## Development

### Project Structure

{Brief explanation of directory layout}

### Testing

{How to run tests}

### Code Style

{Linting/formatting info}

## Working with Claude Code

This project is configured for development with Claude Code. Key files:

- `CLAUDE.md` - Project context and conventions
- `AGENTS.md` - Guidelines for AI agents
- `docs/workflows/` - Development workflow references

## License

{Placeholder - user should update}
```

### 3. Update .gitignore

Append stack-specific patterns to .gitignore based on language/framework:

**Node.js/TypeScript/JavaScript:**
```
node_modules/
dist/
build/
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
.npm
.yarn
```

**Python:**
```
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
venv/
env/
.venv/
*.egg-info/
dist/
build/
.pytest_cache/
.mypy_cache/
```

**Rust:**
```
target/
Cargo.lock  # for libraries only
**/*.rs.bk
```

**Go:**
```
bin/
pkg/
*.exe
*.test
*.out
vendor/
```

**Java:**
```
*.class
*.jar
*.war
target/
.gradle/
build/
```

### 4. Create Directory Structure

Based on project type, create appropriate directories and minimal starter files:

**Web App:**
```
src/
  components/
  pages/ (or routes/)
  styles/
  utils/
public/
tests/
```
- Entry point: `src/index.{ts,js}` or `src/main.{ts,js}` or `src/App.{tsx,jsx}`

**CLI Tool:**
```
src/
  commands/
  utils/
bin/
tests/
```
- Entry point: `src/main.{ext}` or `src/cli.{ext}` with argument parsing stub

**Library/Package:**
```
src/
tests/
examples/
```
- Entry point: `src/index.{ext}` or `src/lib.{ext}` with main export

**API/Backend:**
```
src/
  routes/
  middleware/
  models/
  utils/
tests/
```
- Entry point: `src/server.{ext}` or `src/main.{ext}` with basic server setup

**Mobile App:**
```
src/
  screens/
  components/
  navigation/
  utils/
assets/
tests/
```

**Desktop App:**
```
src/
  main/
  renderer/ (if Electron-style)
  components/
  utils/
assets/
tests/
```

### 5. Create Package/Config Files

Based on the stack, create appropriate configuration:

**Node.js (package.json):**
```json
{
  "name": "{project-name-kebab}",
  "version": "0.1.0",
  "description": "{description}",
  "main": "src/index.js",
  "scripts": {
    "start": "...",
    "dev": "...",
    "test": "...",
    "lint": "..."
  },
  "dependencies": {},
  "devDependencies": {}
}
```

**Python (pyproject.toml):**
```toml
[project]
name = "{project-name-kebab}"
version = "0.1.0"
description = "{description}"
requires-python = ">=3.9"
dependencies = []

[project.optional-dependencies]
dev = []
```

**Rust (Cargo.toml):**
```toml
[package]
name = "{project-name-kebab}"
version = "0.1.0"
edition = "2021"
description = "{description}"

[dependencies]
```

**Go (go.mod):**
```
module {project-name}

go 1.21
```

### 6. Create Minimal Entry Points

Create starter files with minimal boilerplate appropriate to the language and project type. Include:
- Necessary imports
- Main function or entry point
- Basic structure/comments showing where to add code
- For CLIs: argument parsing setup
- For APIs: basic server that responds to health check
- For libraries: exported function with doc comment

### 7. Archive the Init Command

After completing all setup:

1. Copy `.claude/commands/init.md` to `docs/archive/init-command.md`
2. Delete `.claude/commands/init.md`
3. Remove the `.claude/commands/` directory if empty

This prevents the init command from being run again.

---

## Final Output

After completing all actions, provide a summary:

```
Project initialized successfully!

Created:
- CLAUDE.md (project configuration)
- README.md (project documentation)
- .gitignore (updated with {language} patterns)
- {list of directories created}
- {list of files created}

Next steps:
1. Review the generated files and adjust as needed
2. Install dependencies: {package manager command}
3. Start developing!

The /init command has been archived to docs/archive/init-command.md
```
