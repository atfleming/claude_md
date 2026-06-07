# CLAUDE.md — 14-rule template

These rules apply to every task in this project unless explicitly overridden. Bias: caution over speed on non-trivial work. Use judgment on trivial tasks.

## Rules

**Rule 1 — Think Before Coding**
State assumptions explicitly. If uncertain, ask rather than guess. Present multiple interpretations when ambiguity exists. Push back when a simpler approach exists. Stop when confused. Name what's unclear.

**Rule 2 — Simplicity First**
Minimum code that solves the problem. Nothing speculative. No features beyond what was asked. No abstractions for single-use code. Test: would a senior engineer say this is overcomplicated? If yes, simplify.

**Rule 3 — Surgical Changes**
Touch only what you must. Clean up only your own mess. Don't "improve" adjacent code, comments, or formatting. Don't refactor what isn't broken. Match existing style.

**Rule 4 — Goal-Driven Execution**
Define success criteria. Loop until verified. Don't follow steps. Define success and iterate. Strong success criteria let you loop independently.

**Rule 5 — Use the model only for judgment calls**
Use me for: classification, drafting, summarization, extraction. Do NOT use me for: routing, retries, deterministic transforms. If code can answer, code answers.

**Rule 6 — Token budgets are not advisory**
Per-task: 4,000 tokens. Per-session: 30,000 tokens. If approaching budget, summarize and start fresh. Surface the breach. Do not silently overrun.

**Rule 7 — Surface conflicts, don't average them**
If two patterns contradict, pick one (more recent / more tested). Explain why. Flag the other for cleanup. Don't blend conflicting patterns.

**Rule 8 — Read before you write**
Before adding code, read exports, immediate callers, shared utilities. "Looks orthogonal" is dangerous. If unsure why code is structured a way, ask.

**Rule 9 — Tests verify intent, not just behavior**
Tests must encode WHY behavior matters, not just WHAT it does. A test that can't fail when business logic changes is wrong.

**Rule 10 — Checkpoint after every significant step**
Summarize what was done, what's verified, what's left. Don't continue from a state you can't describe back. If you lose track, stop and restate.

**Rule 11 — Match the codebase's conventions, even if you disagree**
Conformance > taste inside the codebase. If you genuinely think a convention is harmful, surface it. Don't fork silently.

**Rule 12 — Fail loud**
"Completed" is wrong if anything was skipped silently. "Tests pass" is wrong if any were skipped. Default to surfacing uncertainty, not hiding it.

**Rule 13 — No co-author tags**
Never append 'co-authored by' statements of any kind, to any commit.

**Rule 14 — Approval before committing**
Always ask for approval before committing.

**Rule 15 - Never use em-dashes.**
Never use em-dashes in copy. 

## Design guidance

Design and frontend styling rules live in `.claude/rules/` (`design-principles.md` and `web-design-hacks.md`). They load automatically when working on frontend files (CSS, SCSS, HTML, JSX/TSX, Vue, Svelte, Astro, MDX) — no import needed. See `.claude/rules/README.md` for scope and contents.

## Netlify Deployments

Always create `netlify.toml` at the repo root before the first deploy. Minimum config for a Vite/React static site:

```toml
[build]
  command = "npm run build"
  publish = "dist"
```

For any SPA with client-side routing, add a `_redirects` file to `public/`:

```
/*    /index.html   200
```

Confirm the build command and publish directory match `package.json` and the framework's output folder before pushing — a blank white page on Netlify almost always means it served the raw source `index.html` without building.

## Images

Never wire a raw photo (PNG/JPG from a phone or camera) directly into a component. Always convert first.

Use `sharp` (install as a devDependency) to convert and resize in one pass:

```bash
npm install --save-dev sharp
node -e "
const sharp = require('sharp');
sharp('public/images/input.PNG')
  .resize({ width: 1200, withoutEnlargement: true })
  .webp({ quality: 82 })
  .toFile('public/images/output.webp');
"
```

Target widths: hero/portrait images ~900px, full-width landscape images ~1400px, logos/icons ~500px. Adjust if the design uses a narrower max-width.

- Add `loading="lazy"` to any `<img>` that is below the fold.
- Always set `width` and `height` attributes on every `<img>` to prevent layout shift.
- Commit the WebP files alongside the originals, so the originals are available if dimensions or quality need to be re-exported later.
