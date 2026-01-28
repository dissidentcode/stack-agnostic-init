# Project Initialization

You are initializing a new project. Conduct an interview to understand the project, then generate customized configuration files and Claude Code tooling.

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
13. **Deployment** - Where and how do you deploy?
    - Options: Vercel/Netlify, AWS, GCP, Docker/containers, Heroku, Self-hosted, Not decided yet, No deployment needed

### Phase 4: Claude Collaboration

Ask these questions together:

14. **Communication Style** - How should Claude communicate with you?
    - Options: Concise (brief responses), Detailed (thorough explanations), Ask first (confirm before acting)
15. **Code Preferences** - Any coding patterns or conventions you prefer? (free text)
16. **Things to Avoid** - Anything Claude should avoid? (dependencies, patterns, styles)

---

## Post-Interview Actions

After collecting all responses, perform these actions in order:

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

### Deployment

{Based on their deployment preferences, or omit if "No deployment needed"}

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

## Tooling

This project includes Claude Code tooling generated during initialization:

### Commands

Available via `/command-name`:

- `/plan` - Create implementation plans with research and documentation
- `/review` - Multi-agent code review (code, security, architecture)
- `/compound` - Document solved problems for future reference
- `/work` - Execute a plan systematically with incremental commits
{If testing != "none": - `/test` - Run tests with {test framework}}

### Agents

Located in `.claude/agents/`:

- `review/code-reviewer` - Code review tuned to {language}/{framework} conventions
- `review/security-reviewer` - Security review for {stack} vulnerabilities
- `review/architecture-reviewer` - Architectural analysis for {project type}
{If testing != "none": - `workflow/test-runner` - Runs tests using {test framework/commands}}

### Skills

Located in `.claude/skills/`:

- `compound-docs` - Document solved problems in `docs/solutions/`
- `project-setup` - Dev environment setup from scratch
{If testing != "none": - `testing` - Testing patterns and conventions for {stack}}

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
- `AGENTS.md` - Agent index and descriptions

### Available Commands

- `/plan` - Create implementation plans
- `/review` - Multi-agent code review
- `/compound` - Document solved problems
- `/work` - Execute plans systematically
{If testing != "none": - `/test` - Run project tests}

### Agents

This project includes specialized review agents in `.claude/agents/` that are invoked by the `/review` command for parallel code, security, and architecture review.

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

### 7. Generate Agents

Create `.claude/agents/` directory with subdirectories and markdown agent files. Each agent has YAML frontmatter and a system prompt **tailored to the specific project stack**.

#### A. `review/code-reviewer.md` (Always generated)

```markdown
---
name: code-reviewer
description: "Reviews code changes for quality, correctness, and adherence to project conventions.
<example>Review the changes in the current branch for code quality issues</example>
<example>Check this PR for bugs, readability problems, and convention violations</example>"
model: inherit
---

You are a code reviewer for a {language}/{framework} {project type} project called {project name}.

## Project Context

- **Language:** {language}
- **Framework:** {framework}
- **Package Manager:** {package manager}
- **Database:** {database}
- **Code Style:** {linting/formatting preferences}
- **Conventions:** {stated code preferences}

## Review Focus

{Stack-specific review criteria. Generate based on language/framework:}

{For TypeScript/JavaScript:}
- Type safety and proper TypeScript usage (if TS)
- Proper async/await patterns, no unhandled promises
- Correct use of {framework}-specific patterns (hooks, middleware, etc.)
- Import organization and module boundaries
- Error handling completeness

{For Python:}
- Type hints usage and correctness
- Proper exception handling with specific exception types
- Pythonic idioms (list comprehensions, context managers, etc.)
- Async patterns if using async framework
- Import organization (stdlib, third-party, local)

{For Rust:}
- Ownership and borrowing correctness
- Error handling with Result/Option (no unwrap in production code)
- Proper use of traits and generics
- Memory safety considerations
- Clippy lint compliance

{For Go:}
- Error handling (no ignored errors)
- Goroutine safety and proper channel usage
- Interface design and composition
- Proper use of context.Context
- Go idioms and conventions

{For Java:}
- Proper exception handling hierarchy
- Thread safety considerations
- Design pattern usage
- Null safety
- Resource management (try-with-resources)

## Review Output Format

For each issue found, report:

```
[severity: critical|warning|suggestion] file:line
Description of the issue

Suggested fix:
{code snippet}
```

Group findings by severity. Start with a brief summary of the overall change quality.
```

#### B. `review/security-reviewer.md` (Always generated)

```markdown
---
name: security-reviewer
description: "Reviews code for security vulnerabilities and best practices.
<example>Check these changes for security vulnerabilities</example>
<example>Audit the authentication flow for security issues</example>"
model: inherit
---

You are a security reviewer for a {language}/{framework} {project type} project.

## Security Focus Areas

{Generate based on stack. Include ALL that apply:}

### General (Always)
- No hardcoded secrets, API keys, or credentials
- No sensitive data in logs or error messages
- Proper input validation at system boundaries
- Secure defaults in configuration

{For Web Apps / API/Backend:}
### Web Security
- XSS prevention (output encoding, CSP headers)
- CSRF protection
- SQL injection prevention (parameterized queries)
- Authentication and authorization checks
- Secure session management
- CORS configuration
- Rate limiting considerations
- Secure HTTP headers

{For projects with Database:}
### Database Security
- Parameterized queries (no string concatenation for SQL)
- Principle of least privilege for DB connections
- Sensitive data encryption at rest
- Migration safety (no data loss)

{For TypeScript/JavaScript:}
### Node.js / Browser Security
- No eval() or Function() with user input
- Dependency vulnerability awareness
- Prototype pollution prevention
- Safe regex patterns (no ReDoS)
- Proper CORS and CSP configuration

{For Python:}
### Python Security
- No pickle with untrusted data
- No eval/exec with user input
- Safe YAML loading (yaml.safe_load)
- Proper password hashing (bcrypt/argon2)
- SQL injection via ORMs (raw queries)

{For Rust:}
### Rust Security
- Unsafe block justification and review
- No panics in library code
- Proper cryptographic library usage
- Input validation before unsafe operations

{For Go:}
### Go Security
- No unsanitized user input in templates
- Proper TLS configuration
- Context timeout enforcement
- Safe concurrent access patterns

## Output Format

For each finding:

```
[severity: critical|high|medium|low] file:line
VULNERABILITY: {type}
Description: {what's wrong}
Impact: {what could happen}
Fix: {how to fix it}
```

List critical and high severity issues first. End with a summary assessment.
```

#### C. `review/architecture-reviewer.md` (Always generated)

```markdown
---
name: architecture-reviewer
description: "Reviews changes for architectural consistency and design quality.
<example>Evaluate these changes for architectural impact</example>
<example>Check if this new module follows the project's architectural patterns</example>"
model: inherit
---

You are an architecture reviewer for a {language}/{framework} {project type} project.

## Project Architecture

- **Type:** {project type}
- **Language:** {language}
- **Framework:** {framework}
- **Database:** {database}

## Architecture Principles

{Generate based on project type and framework:}

{For Web Apps:}
- Component hierarchy and data flow direction
- State management boundaries
- Client/server separation
- Routing organization

{For API/Backend:}
- Layer separation (routes → controllers → services → repositories)
- Dependency injection patterns
- API versioning strategy
- Error handling consistency across endpoints

{For CLI Tools:}
- Command structure and subcommand organization
- Input/output separation
- Configuration management
- Composability of operations

{For Libraries:}
- Public API surface minimization
- Breaking change awareness
- Dependency management
- Documentation of public interfaces

{For all project types:}
- Single responsibility for modules/files
- Dependency direction (no circular dependencies)
- Appropriate abstraction levels
- Consistency with existing patterns in the codebase

## Review Output Format

For each concern:

```
[impact: high|medium|low] {area}
Observation: {what you noticed}
Concern: {why it matters}
Recommendation: {what to do instead}
```

Start with an architectural summary of the changes, then list specific concerns.
```

#### D. `workflow/test-runner.md` (Only when testing != "none")

```markdown
---
name: test-runner
description: "Runs tests and reports results with analysis.
<example>Run the test suite and report results</example>
<example>Run tests related to the authentication module</example>"
model: inherit
---

You are a test runner for a {language}/{framework} project.

## Test Configuration

- **Test Framework:** {infer from stack: pytest for Python, jest/vitest for TS/JS, cargo test for Rust, go test for Go, JUnit for Java}
- **Test Command:** {infer: `pytest`, `npm test`, `cargo test`, `go test ./...`, `mvn test`}
- **Test Directory:** {infer: `tests/`, `__tests__/`, `src/**/*.test.*`}

## Process

1. Run the test command using Bash
2. Parse the output for pass/fail status
3. If tests fail:
   - Identify which tests failed
   - Read the failing test files
   - Read the source files being tested
   - Provide analysis of why each test fails
   - Suggest fixes
4. If all tests pass:
   - Report summary (total, passed, duration)
   - Note any warnings or skipped tests

## Output Format

```
Test Results: {PASS|FAIL}
Total: {n} | Passed: {n} | Failed: {n} | Skipped: {n}
Duration: {time}

{If failures:}
## Failures

### {test name}
File: {test file path}
Error: {error message}
Analysis: {why it's failing}
Suggested fix: {what to change}
```
```

### 8. Generate Skills

Create `.claude/skills/` directory with skill subdirectories, each containing a `SKILL.md` file.

#### A. `compound-docs/SKILL.md` (Always generated)

```markdown
---
name: compound-docs
description: "Document a solved problem for future reference. Creates structured solution docs in docs/solutions/ that compound project knowledge over time."
allowed-tools: ["Read", "Write", "Glob", "Grep", "Bash"]
---

# Compound Documentation

Create a solution document for a problem that was just solved.

## Process

1. **Understand the context** - Review recent changes, commits, or conversation to identify what was solved
2. **Gather details** - Read relevant source files to understand the solution
3. **Create the document** - Write to `docs/solutions/` using the format below
4. **Update CLAUDE.md** - If the solution represents a recurring pattern, add it to the "Key Learnings" section

## Solution Document Format

Create `docs/solutions/{descriptive-kebab-case-name}.md`:

```markdown
# {Problem Title}

## Context
What situation led to this problem?

## Problem
What was the specific issue?

## Solution
How did we solve it? Include the reasoning behind the approach.

## Code Example
```{language}
// Key code that illustrates the solution
```

## Key Learnings
- What did we learn?
- What patterns does this establish?
- What should we watch out for in the future?

## References
- Links to relevant docs, files, or discussions
```

## Naming Convention

Use descriptive kebab-case names that make solutions findable:
- `handling-auth-token-refresh.md`
- `postgres-connection-pooling.md`
- `{framework}-form-validation-pattern.md`
```

#### B. `project-setup/SKILL.md` (Always generated)

```markdown
---
name: project-setup
description: "Guide for setting up the development environment from scratch. Covers prerequisites, installation, and first run."
allowed-tools: ["Read", "Bash", "Glob"]
---

# Project Setup Guide

Walk a developer through setting up this project from a fresh clone.

## Steps

{Generate based on stack:}

{For Node.js/TypeScript/JavaScript:}
1. Verify Node.js is installed: `node --version` (requires {version})
2. Install dependencies: `{npm install|yarn|pnpm install}`
3. Copy environment file: `cp .env.example .env` (if applicable)
4. Set up database (if applicable): {database-specific setup}
5. Run the project: `{npm run dev|yarn dev|pnpm dev}`
6. Run tests: `{npm test|yarn test|pnpm test}`

{For Python:}
1. Verify Python is installed: `python --version` (requires >=3.9)
2. Create virtual environment: `python -m venv .venv`
3. Activate: `source .venv/bin/activate` (or `.venv\Scripts\activate` on Windows)
4. Install dependencies: `pip install -e ".[dev]"` or `poetry install`
5. Copy environment file: `cp .env.example .env` (if applicable)
6. Set up database (if applicable): {database-specific setup}
7. Run the project: `python -m {module}` or `{framework} run`
8. Run tests: `pytest`

{For Rust:}
1. Verify Rust is installed: `rustc --version`
2. Build the project: `cargo build`
3. Run the project: `cargo run`
4. Run tests: `cargo test`

{For Go:}
1. Verify Go is installed: `go version` (requires >=1.21)
2. Download dependencies: `go mod download`
3. Run the project: `go run .`
4. Run tests: `go test ./...`

{For Java:}
1. Verify Java is installed: `java --version` (requires {version})
2. Build: `mvn install` or `gradle build`
3. Run: `mvn exec:java` or `gradle run`
4. Test: `mvn test` or `gradle test`

## Verification

After setup, verify everything works by running the test suite and confirming the application starts without errors.
```

#### C. `testing/SKILL.md` (Only when testing != "none")

```markdown
---
name: testing
description: "Testing conventions and patterns for this project. Covers how to write, organize, and run tests."
allowed-tools: ["Read", "Write", "Bash", "Glob", "Grep"]
---

# Testing Guide

How to write and organize tests for this project.

## Test Framework

{Based on stack:}
{TypeScript/JavaScript: jest, vitest, or mocha}
{Python: pytest}
{Rust: built-in cargo test + optional proptest}
{Go: built-in testing package}
{Java: JUnit 5}

## Running Tests

{Stack-specific commands:}
- All tests: `{test command}`
- Single file: `{test command for single file}`
- Watch mode: `{watch command if available}`
- With coverage: `{coverage command}`

## Test Organization

{Based on language and project type:}

{For TypeScript/JavaScript:}
- Co-locate test files next to source: `src/module.ts` → `src/module.test.ts`
- Or use `tests/` directory mirroring `src/` structure
- Use `describe`/`it` blocks with descriptive names
- Group by feature, not by type

{For Python:}
- Tests in `tests/` directory mirroring `src/` structure
- Test files named `test_{module}.py`
- Test functions named `test_{behavior}`
- Use fixtures for shared setup
- Use parametrize for data-driven tests

{For Rust:}
- Unit tests in `#[cfg(test)]` modules within source files
- Integration tests in `tests/` directory
- Use `#[test]` attribute
- Test module mirrors source module structure

{For Go:}
- Test files named `{file}_test.go` alongside source
- Test functions named `Test{FunctionName}`
- Use table-driven tests for multiple cases
- Use `testify` for assertions if preferred

{For Java:}
- Tests in `src/test/java/` mirroring main source structure
- Test classes named `{Class}Test`
- Use `@Test`, `@BeforeEach`, `@AfterEach` annotations
- Use descriptive method names: `shouldDoXWhenY`

## Writing a New Test

1. Create the test file in the appropriate location
2. Import the module/function being tested
3. Write test cases covering:
   - Happy path (expected behavior)
   - Edge cases (empty input, boundaries)
   - Error cases (invalid input, failures)
4. Run the test to verify it passes (or fails first for TDD)

## Test Patterns

{Based on project type:}

{For API/Backend:}
- Use request/response testing for endpoints
- Mock external services
- Test middleware separately
- Use test database or in-memory DB

{For Web Apps:}
- Component rendering tests
- User interaction tests
- Integration tests for key flows
- Mock API calls

{For Libraries:}
- Public API contract tests
- Edge case coverage
- Performance benchmarks for critical paths

{For CLI Tools:}
- Command output testing
- Argument parsing tests
- Error message verification
- Exit code testing
```

### 9. Generate Commands

Create `.claude/commands/` directory with markdown command files. Each command has YAML frontmatter and orchestration instructions.

#### A. `plan.md` (Always generated)

```markdown
---
name: plan
description: "Create an implementation plan for a feature or task"
argument-hint: "feature or task to plan"
---

# Create Implementation Plan

Create a thorough implementation plan for: $ARGUMENTS

## Process

1. **Research** - Use the Explore agent to understand the relevant parts of the codebase:
   - Find existing code related to this feature/task
   - Understand current patterns and architecture
   - Identify what files will need to change

2. **Design** - Based on research, design the approach:
   - Break the work into discrete, ordered steps
   - Identify risks or unknowns
   - Consider alternative approaches and justify the chosen one
   - Estimate which files will be created/modified

3. **Document** - Write the plan to `docs/plans/{descriptive-name}.md`:

```markdown
# {Feature/Task Name}

## Goal
What we're trying to achieve and why

## Research Findings
What we learned about the current codebase

## Approach
How we'll implement it, and why this approach

## Steps
1. {First change - specific files and what changes}
2. {Second change}
3. ...

## Testing Strategy
How we'll verify the implementation works

## Open Questions
- Any uncertainties to resolve before starting
```

4. **Present** - Summarize the plan and ask for feedback before implementation begins
```

#### B. `review.md` (Always generated)

```markdown
---
name: review
description: "Run multi-agent code review on current changes"
argument-hint: "branch or files to review (default: current changes)"
---

# Multi-Agent Code Review

Run a comprehensive review of the current changes using specialized review agents.

## Process

1. **Identify changes** - Determine what to review:
   - If $ARGUMENTS specifies a branch: `git diff main...$ARGUMENTS`
   - If $ARGUMENTS specifies files: review those files
   - Otherwise: `git diff` for unstaged + `git diff --cached` for staged changes
   - If no changes found, check `git log main..HEAD` for committed changes on the current branch

2. **Run reviews in parallel** - Launch all three review agents simultaneously using the Task tool:

   - **Task agent code-reviewer**: "Review the following changes for code quality, correctness, and convention adherence: {changes summary}"
   - **Task agent security-reviewer**: "Review the following changes for security vulnerabilities: {changes summary}"
   - **Task agent architecture-reviewer**: "Review the following changes for architectural consistency: {changes summary}"

3. **Synthesize results** - After all agents complete, combine their findings:

```markdown
# Code Review Summary

## Overview
{Brief description of what was reviewed}

## Code Quality
{Findings from code-reviewer}

## Security
{Findings from security-reviewer}

## Architecture
{Findings from architecture-reviewer}

## Action Items
{Consolidated list of required changes, ordered by severity}

## Suggestions
{Non-blocking improvements to consider}
```

4. **Present** - Show the synthesized review to the user
```

#### C. `compound.md` (Always generated)

```markdown
---
name: compound
description: "Document a solved problem for compound knowledge"
argument-hint: "problem that was solved (or leave blank to auto-detect)"
---

# Compound Documentation

Document a solved problem so the knowledge compounds over time.

## Process

1. **Identify the problem** - If $ARGUMENTS is provided, use it. Otherwise:
   - Review recent git commits: `git log --oneline -10`
   - Review recent conversation context
   - Ask the user what was solved if unclear

2. **Invoke the compound-docs skill** to create the documentation:
   - Gather context from the relevant source files
   - Create the solution document in `docs/solutions/`
   - Follow the format defined in the skill

3. **Update CLAUDE.md** - If this solution establishes a pattern or key learning:
   - Add a bullet point to the "Key Learnings" section
   - Reference the solution doc path

4. **Confirm** - Show the user what was documented and where
```

#### D. `work.md` (Always generated)

```markdown
---
name: work
description: "Execute an implementation plan systematically"
argument-hint: "plan to execute (path or description)"
---

# Execute Implementation Plan

Systematically implement a plan with incremental commits.

## Process

1. **Load the plan** - If $ARGUMENTS is a file path, read it. Otherwise:
   - Search `docs/plans/` for a matching plan
   - If no plan found, ask the user which plan to execute
   - If no plans exist, suggest running `/plan` first

2. **Create a feature branch** (if not already on one):
   - Branch name: `feat/{descriptive-name}` based on the plan
   - `git checkout -b feat/{name}`

3. **Execute each step** from the plan:
   - For each step:
     a. Announce what you're about to do
     b. Implement the change
     c. Verify the change works (run relevant tests if they exist)
     d. Commit with a descriptive message: `{type}: {what this step accomplishes}`
     e. Move to the next step
   - If a step is unclear, ask for clarification before proceeding
   - If a step fails, stop and report the issue

4. **Final verification**:
   - Run the full test suite (if tests exist)
   - Review all changes: `git log --oneline main..HEAD`
   - Summarize what was implemented

5. **Report completion**:

```
## Implementation Complete

Branch: {branch name}
Commits: {number of commits}

### Changes Made
{List of what was done per step}

### Test Results
{Test output summary}

### Next Steps
- Review with `/review`
- Document learnings with `/compound` if applicable
- Merge when ready
```
```

#### E. `test.md` (Only when testing != "none")

```markdown
---
name: test
description: "Run tests and analyze results"
argument-hint: "specific test file, pattern, or 'all' (default: all)"
---

# Run Tests

Run the project test suite and analyze results.

## Process

1. **Determine scope**:
   - If $ARGUMENTS specifies a file or pattern: run that subset
   - If $ARGUMENTS is empty or "all": run the full suite

2. **Run tests** using the test-runner agent:
   - Task agent test-runner: "Run {scope} tests and report results"

3. **If tests fail**:
   - Show the failure summary
   - For each failure, provide analysis and suggested fixes
   - Ask if the user wants to fix the issues

4. **If tests pass**:
   - Show the summary (total, passed, skipped, duration)
   - Note any warnings or areas with low coverage if coverage data is available
```

### 10. Update AGENTS.md

Replace the contents of AGENTS.md with an agent index:

```markdown
# Agents

Specialized agents for this project. These are invoked by commands and can also be called directly via `Task agent {name}`.

## Review Agents

### code-reviewer
Reviews code for quality, correctness, and adherence to {language}/{framework} conventions. Checks for proper patterns, error handling, and code organization.

**Location:** `.claude/agents/review/code-reviewer.md`

### security-reviewer
Reviews code for security vulnerabilities specific to {language}/{framework} and {project type} applications. Covers OWASP top 10, {stack-specific vulnerabilities}.

**Location:** `.claude/agents/review/security-reviewer.md`

### architecture-reviewer
Reviews changes for architectural consistency, proper separation of concerns, and adherence to {project type} patterns.

**Location:** `.claude/agents/review/architecture-reviewer.md`

{If testing != "none":}
## Workflow Agents

### test-runner
Runs the test suite using {test framework}, parses results, and provides analysis of any failures with suggested fixes.

**Location:** `.claude/agents/workflow/test-runner.md`

## Working Agreement

- **Branching:** Create feature branches for non-trivial changes
- **Safety:** Never delete or overwrite files without confirmation
- **Testing:** Run tests after changes to core functionality
- **Documentation:** Update CLAUDE.md when new patterns emerge
- **Quality:** Prefer simple solutions over clever ones
- **Communication:** Be concise, show relevant code when discussing changes
```

### 11. Archive the Init Command

After completing all setup:

1. Copy `.claude/commands/init.md` to `docs/archive/init-command.md`
2. Delete `.claude/commands/init.md`

This prevents the init command from being run again. Do NOT delete the `.claude/commands/` directory since it now contains generated commands.

---

## Final Output

After completing all actions, provide a summary:

```
Project initialized successfully!

Created:
- CLAUDE.md (project configuration with tooling reference)
- README.md (project documentation)
- AGENTS.md (agent index)
- .gitignore (updated with {language} patterns)
- {list of directories created}
- {list of entry point files created}

Tooling generated:
- Agents: {list agents created, e.g. "code-reviewer, security-reviewer, architecture-reviewer, test-runner"}
- Skills: {list skills created, e.g. "compound-docs, project-setup, testing"}
- Commands: {list commands created, e.g. "/plan, /review, /compound, /work, /test"}

Next steps:
1. Review the generated files and adjust as needed
2. Install dependencies: {package manager command}
3. Try `/plan` to create your first implementation plan
4. Start developing!

The /init command has been archived to docs/archive/init-command.md
```
