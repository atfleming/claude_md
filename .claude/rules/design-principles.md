---
paths:
  - "**/*.{css,scss,html,jsx,tsx,vue,svelte,astro,mdx}"
---

# Design principles

Every choice must serve the brand and the goal of the piece — never use a trend for its own sake. Before adding anything, ask: *does this serve the client/site, or does it just look cool?* If it doesn't fit the big picture, it makes the design worse, not better.

## Core principles
- Serve the goal first — not the trend, not the portfolio.
- Less is usually more: fewer colors, fewer fonts, more whitespace.
- Any trend or effect is seasoning — a little goes a long way.
- Tie every element back to the overall brand and message.

## Layout & grids
- Build on a grid (12-column for web). Rarely use more than 1–3 columns per section.
- Use the grid to set hierarchy: span important elements across more columns so they dominate.
- Break the grid deliberately on 1–2 elements for contrast and impact — keep everything else aligned.
- Use the grid to plan whitespace; split columns/rows finer for precise micro-spacing.
- Keep line lengths comfortable — never too long or too short.
- Pick the grid type by job: baseline (align all type to multiples of the base leading), column (multi-content), modular (cards/products — enlarge a module to flag priority items), asymmetric (hero takes more space; overlap + diagonals add depth), rule-of-thirds (place key elements on the lines), compound (column + modular). Use the golden ratio (~1.618) as a starting point, then adjust by eye.

## Typography
- Work in three levels: (1) a single font, (2) a superfamily (one family with matching sans/serif/mono), (3) combos from different foundries that mesh. Levels 1–2 are safe; level 3 adds the most character.
- Anchor on the headline, not the body — it sets the page's personality and must match the brand. Choose every other font to support that anchor.
- Supporting fonts should feel from the same world but carry enough contrast to stay interesting. Avoid near-identical pairings (e.g. Georgia + Times) — they read as accidental.
- Use Fonts In Use to find proven pairings for an anchor font.
- Signal reading order with opacity, not just size: keep primary text near 100%, drop secondary to ~60–70%.

## Movement & flow (guide the eye)
- **Direction:** use cues — arrows, a subject's gaze, a visual path — to point toward the next element.
- **Hierarchy:** size and contrast form an invisible arrow; the biggest/boldest reads first. Prefer this over literal arrows.
- **Multiple paths:** add a main route plus small side-loops of detail to hold attention — keep secondary flows weaker than the main one.
- **Implied motion:** suggest movement with repetition, progressive scaling, blur, or directional patterns.
- **Disruption:** drop one jarring/rotated element across the path to force re-engagement at a key point — intentional, never random.
- **Temporal flow:** control rhythm — punch, slow, pause, release. Fast pacing for skimmable content, slow for dense content.

## The LIFT system
- **Leverage point:** choose the single most important element and make it dominate with scale, contrast, position, and isolation. Push everything else back to support it. (A layout can have more than one.)
- **Internal rhythm:** choreograph the eye with consistent spacing and predictable alignment. Group related elements. Predictable spacing builds trust; one deliberate disruption re-engages.
- **Friction & flow:** strategic friction (tight spacing, a jarring object) grabs attention — but isolate it in a friction zone and keep reading zones smooth. Good friction grabs the eye; bad friction loses the message. Ask of every element: clarity or noise?
- **Transferability:** the design must survive every format. Test at thumbnail size, on light and dark backgrounds, and across mobile/print/motion. Hierarchy and identity must hold.

## Make it memorable
- Give each page a "star of the show" — one element (a font, image, gradient, or object) that makes people feel something and holds attention long enough to act.
- Treat the star as a seed: pick it because it connects to the site's story, never just because it looks cool, then grow the rest of the design around it.
- Use visual rhyming: repeat details — shapes, colors, gradients, textures, often pulled from the star — across the site so everything feels from one universe.
- Add depth to make the site feel tangible: subtle textures (noise), 3D, or glass. Keep it settled — it should be noticed, never compete with the star.
- Before settling, try a radically different version — new layout, light mode, a different star — instead of only polishing the first idea. The best version is rarely the first.

## 2026 trends (use only where they fit the brand)
- **Barely-there UI:** hyper-minimal AI-startup look — thin sans-serifs, stripped layouts, dialed-back palette, heavy whitespace, one font family, data/graphs featured.
- **Restrained maximalism:** oversized headers plus one bold pop of color, in service of the brand — not chaos.
- **Human touch (anti-AI):** add 1–2 imperfect, handmade marks — hand-drawn arrows, messy underlines, unpolished/phone photos, paper or ink textures, slight asymmetry. Human, not messy.
- **Grade-school color:** grounded, Crayola-adjacent primaries with nuanced hues and shades. Orange (sometimes red-tinged) is the color of the moment.
- **Spaceship manual:** blueprint lines, tiny technical labels, monospaced type, lo-fi diagrams. Best for technical/SaaS. A little goes a long way.
- **Accessible 3D / WebGL:** Spline, Unicorn Studio, Rive for interactive 3D — use to tell the story, never to distract.
- **Internet nostalgia:** tasteful early-2000s touches — subtle custom cursors, blocky UI, ASCII/text images, retro tooltips. Start with one.
- **Interaction sound:** tiny click/hover micro-sounds for feedback. Keep it subtle and opt-in — never a forced soundtrack.
- **Tech-bro gradient:** soft purple/blue/teal with a faint glow (the SaaS/AI default). Use it, but vary the colors or shapes to stand out — and only if it fits.
