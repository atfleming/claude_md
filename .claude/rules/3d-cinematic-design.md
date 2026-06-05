---
paths:
  - "**/*.{css,scss,html,jsx,tsx,vue,svelte,astro,mdx}"
---

# 3D & cinematic design

Use this when a site calls for a 3D centerpiece, an animated background, or a "next-level" cinematic feel. Two rules come first: the design has to look good *naked* — establish a solid foundation (layout, type, hierarchy) before any 3D or animation, and never lean on effects to rescue weak design. And treat 3D/motion as the last 10% that takes a good page from 90 to 100, not the thing the page is built on.

## Production pipeline
1. **Direction — stylescape, not wireframe.** Explore typography, color, layout, and imagery together on one canvas (Figma). Duplicate and iterate rather than delete; keep every variation. Lock a direction before building: a centerpiece concept, 1–2 fonts, and a restrained palette (commonly dark + a single metallic/accent color).
2. **Centerpiece — AI image generation.** Generate the hero subject with a tool like Magnific. Expect to iterate — no one nails it in one prompt; refine and keep going. For a 3D centerpiece, generate several angle variations of the same subject so it can be turned into a 3D model.
3. **Build — design-first.** If your builder is design-first (e.g., Showit), go straight from stylescape to page and make layout calls in context; skip throwaway wireframes/mockups. In a framework repo, block out the real components instead of static mockups.
4. **3D object — Spline.** Import the model, set materials (a touch of gloss reads premium), and add one interaction — e.g., a look-at event so the object tracks the cursor. Export and embed (see Integration).
5. **Background life — animated texture.** Add subtle motion and grit with a tool like Unicorn Studio: start from an image, layer effects (noise/FBM, film grain), drop in a brand-colored shape, keep movement slow. Export and embed.

## Composition (what makes these work)
- One star per view: the 3D centerpiece is the leverage point — everything else supports it.
- Layer for depth: place headline text partly in front of and behind the object, not floating flat above it.
- Old-meets-new: pair a classical/organic 3D subject with a clean sans for headlines and one script/serif accent for a luxury note.
- Restrained palette: a dark base plus a single accent (gold/metallic) keeps a busy hero from getting noisy.
- Texture bridges real and digital: light grain or film noise over flat color makes the screen feel tangible.
- Keep motion slow and settled so it never competes with the message or the CTA.

## Integration (framework repo)
- Embed Spline via the official runtime (`@splinetool/react-spline`) for React, or paste the Spline viewer embed into a dedicated component/iframe. Unicorn Studio ships an embed script + element — isolate it in its own component.
- Keep each effect in its own component so it's easy to lazy-load and to remove.
- Treat embeds like heavy images: never wire them into the critical render path.

## Performance & accessibility (non-negotiable)
- 3D/WebGL and animated backgrounds are expensive. Lazy-load or defer them; mount below the fold or after first interaction so they don't block LCP.
- Always ship a static fallback (poster image or plain background) for first paint, slow connections, and load failures.
- Respect `prefers-reduced-motion`: disable cursor-follow, autoplay, and background motion when it's set.
- Watch mobile: test GPU load and battery on a real device; consider serving a static image instead of the live scene on small screens.
- Keep text contrast strong over busy/animated backgrounds; never rely on the effect to carry legibility.
- No forced audio — if a scene has sound, it's opt-in.
- Just because you *can* add an effect doesn't mean you should — it must serve the page's goal (see `design-principles.md`).
