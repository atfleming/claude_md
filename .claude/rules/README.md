# .claude/rules/

Path-scoped instruction files for Claude Code. Each file here is auto-discovered at session start, but its `paths:` frontmatter gates when it actually loads into context: a rule only applies when Claude reads a file matching one of its glob patterns. This keeps design guidance out of unrelated sessions (and out of the engineering rules in the root `claude.md`).

No `@import` is needed — do **not** reference these from `claude.md`, or they'll load every session and defeat the scoping.

## Files

| File | Scope (loads when Claude opens…) | Covers |
| --- | --- | --- |
| `design-principles.md` | `**/*.{css,scss,html,jsx,tsx,vue,svelte,astro,mdx}` | Core design philosophy, grids & layout, typography, eye movement & flow, the LIFT system, making a page memorable, and the 2026 trend list. |
| `web-design-hacks.md` | `**/*.{css,scss,html,jsx,tsx,vue,svelte,astro,mdx}` | Quick tactical tips: layout patterns, type, color (60-30-10), image selection, UX, and technical/SEO/accessibility. Image build mechanics (WebP/sizing) live in the root `claude.md` instead. |

## How it works

- Rules **with** a `paths:` block load only when Claude reads a matching file.
- Rules **without** a `paths:` block load every session, at the same priority as the root `claude.md`.
- Verify what's loaded: open a matching file in a Claude Code session and run `/memory` — each active rule file should be listed.

## Adding a rule

1. Create a new `.md` file in this directory (one topic per file; descriptive name).
2. Add a `paths:` frontmatter block to scope it, or omit it to load always:

   ```
   ---
   paths:
     - "**/*.{ts,tsx}"
   ---
   ```
3. Keep each file focused and under ~200 lines for best adherence.

See the Claude Code memory docs for full details: https://code.claude.com/docs/en/memory
