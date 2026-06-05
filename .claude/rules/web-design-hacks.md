---
paths:
  - "**/*.{css,scss,html,jsx,tsx,vue,svelte,astro,mdx}"
---

# Web design hacks

## Layout
- Use a 12-column grid; keep most sections to 1–3 columns.
- Lean on proven patterns (image left / text right, and reversed) — tweak slightly so they don't feel generic.
- Use more whitespace than feels comfortable; let sections breathe.
- Vary section backgrounds and layouts to keep users scrolling.
- Build hierarchy in 3 tiers: primary (instantly scannable), secondary (supports, doesn't compete), tertiary (fine detail, low-key).

## Typography
- Choose fonts on purpose: display for attention; legible faces for anything over ~7–10 words.
- Pair fonts by laying them side by side; if they clash, keep looking.
- Scale type with the golden ratio (×1.618) as a starting point — but if it looks good, it's good.

## Color
- Use color theory (analogous, complementary, triadic) for harmonious palettes; keep the count low.
- Apply 60-30-10: 60% dominant (often black/white), 30% brand, 10% accent.
- Reserve one consistent accent color for CTAs only, so users learn it means "act."
- Keep image colors in the ballpark of the palette.

## Images
- Choose photos where people look toward key content — eyes lead the viewer.
- Good stock = good lighting + natural expression (e.g. Pexels).
- Crop to the subject using rule of thirds before placement.
- (Conversion, sizing, lazy-loading, and dimensions are covered in the Images section of the root CLAUDE.md.)

## UX
- Design for the user first — not the portfolio, not the trend.
- People skim — make every section clear at a glance.
- Only ~20% get past the top fold: make the hero crystal clear and motivating.
- Proofread layouts by scrolling bottom-to-top for fresh eyes.
- Test on real devices, not just emulators/DevTools.
- Make button text specific and action-oriented ("See pricing," "Download the guide" — not "Let's do this").
- Budget competing priorities (brand, SEO, performance, accessibility, conversion) per section — they can't all win at once.

## Technical, SEO & accessibility
- Minimize third-party plugins; each adds code that slows the site.
- Use Chrome DevTools for CSS and Lighthouse to find what's slowing a page.
- Use semantic HTML: one H1 per page (page summary), H2s for sections, p / ul / li, plus nav and footer. Google reads structure first.
- Set 301 redirects on any URL change; fix broken links fast.
- Write descriptive alt text on every image (natural keywords, no stuffing) — for SEO and accessibility.
- Ensure strong color contrast, full keyboard navigation, and never rely on color alone — pair it with icons, labels, or patterns.
