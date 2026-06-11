---
description: Rules for authoring, modifying, and reviewing GitHub Actions workflows.
paths:
  - ".github/workflows/**/*.yml"
  - ".github/workflows/**/*.yaml"
  - ".github/actions/**/*"
---
# GitHub Actions Workflow Rules

When creating or modifying GitHub Actions, you MUST adhere to the following standards:

## Naming and Triggers
- Use `kebab-case` for workflow filenames (e.g., `build-and-deploy.yml`).
- Include descriptive `name:` fields for both the workflow and individual jobs.
- Explicitly define triggers. Always include `workflow_dispatch` for manual debugging alongside automated triggers like `push` or `pull_request`.

## Security & Secrets
- NEVER hardcode credentials, tokens, or API keys in plain text. Always inject them via `${{ secrets.SECRET_NAME }}`.
- Apply the principle of least privilege. Explicitly set `permissions:` at the workflow or job level (e.g., `contents: read`).
- When using third-party actions, pin to specific commit SHAs rather than mutable tags for security-critical environments.

## Performance & Caching
- Implement caching for language dependencies (e.g., `actions/setup-node` with `cache: 'npm'` or native `actions/cache`) to minimize workflow execution time.
- Use matrix strategies (`strategy.matrix`) when running tests across multiple language versions or operating systems.
- Fail fast: Order jobs so that fast checks (linting, formatting) run before time-intensive jobs (E2E tests, builds).

## Syntax & Linting
- Use valid, standard YAML format. Indent with 2 spaces.
- Group logical sequential steps using `needs:` to define dependency graphs between jobs.
- Keep inline shell scripts short. For complex scripts, execute a dedicated script file from the repository (e.g., `run: ./scripts/build.sh`).
