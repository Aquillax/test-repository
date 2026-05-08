# CLAUDE.md

This file documents the repository structure, conventions, and workflows for AI assistants working in this codebase.

## Repository Overview

**Name:** test-repository  
**GitHub:** aquillax/test-repository  
**Description:** test-project  
**Status:** Early-stage / minimal repository with no source code yet.

The repository currently contains only a `README.md`. This CLAUDE.md serves as the foundation for conventions to follow as the project grows.

## Repository Structure

```
test-repository/
└── README.md       # Project title and description
```

## Git Conventions

### Branches

- Default branch: `main`
- AI-generated feature branches follow the pattern: `claude/<description>-<short-id>`  
  Example: `claude/add-claude-documentation-eAZQk`
- Always develop on the designated feature branch; never push directly to `main` without explicit permission.

### Commits

- Use clear, descriptive commit messages in the imperative mood.  
  Good: `Add user authentication module`  
  Avoid: `added stuff`, `wip`, `fix`
- Keep commits focused — one logical change per commit.

### Push Workflow

```bash
git push -u origin <branch-name>
```

Retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s) on network failures.

## Development Workflow

1. Check out or create the designated feature branch before making any changes.
2. Make focused, incremental commits as work progresses.
3. Push to the remote branch when the task is complete.
4. Do **not** open a pull request unless explicitly requested by the user.

## AI Assistant Guidelines

- **Read before writing:** Always read a file before editing it.
- **Minimal changes:** Make only the changes required by the task. Do not refactor, add features, or clean up code beyond the scope of the request.
- **No speculative comments:** Do not add comments explaining what code does; only comment on non-obvious *why* decisions.
- **No unsolicited files:** Do not create README files, docs, or other artifacts unless explicitly asked.
- **Confirm before destructive actions:** Force-push, `reset --hard`, branch deletion, and similar irreversible operations require explicit user confirmation.
- **Security:** Do not introduce command injection, XSS, SQL injection, or other OWASP Top 10 vulnerabilities. Fix any insecure code immediately upon discovery.

## Adding to This File

As the project grows, update this file with:
- Build and test commands (e.g., `npm test`, `make build`)
- Environment setup instructions
- Code style and linting configuration
- Architecture decisions and key conventions
