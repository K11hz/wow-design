---
name: design-wow
description: Art director for high-impact web design on Next.js, React, Tailwind CSS, and Motion. Covers visual direction, typography, OKLCH palettes, micro-interactions, anti-slop rules, and screenshot-based visual QA. Use for landing pages, hero sections, redesigns, "make it look premium", "boring UI", "linear style", "apple style".
---

# Design WOW

Goal: The visitor opens the site and says "wow". Average, generic results count as failure.

## Step 0. Brief (Never Skip)

If `DESIGN.md` does not exist in the project root, ask the user at most 3 questions:
1. What is the product/site, who is the audience, and what emotion should it evoke (luxurious, bold, calm, tech-forward, playful)?
2. 1–3 reference websites that match the desired quality.
3. Light mode, dark mode, or both?

Pick ONE direction from `references/directions.md`, document it briefly (palette, font pairings, signature feature, motion feel) in `DESIGN.md`, and adhere to `DESIGN.md` consistently.

## Step 1. One Core Visual Feature

Every page must have one strong, memorable visual hook. Examples: massive editorial hero typography, interactive 3D/WebGL canvas, bento grid with live interactive previews, horizontal narrative scroll, cursor spotlight, or an animated gradient mesh.
One signature feature executed flawlessly beats five mediocre elements.

## Step 2. Typography — 50% of the Impact

- Max 2 font families via `next/font`: one expressive display font for headings + one neutral workhorse for body text. Examples: `Instrument Serif + Inter`, `Space Grotesk + Inter`, `Fraunces + Geist`, `Clash Display + Satoshi`, `Unbounded + Manrope`. Verify Cyrillic/glyph support if non-Latin scripts are needed.
- Hero heading: bold and deliberate. Use `clamp(3rem, 8vw, 8rem)`, `leading-[0.9]`, `tracking-tight`. Accent a single key word with serif italics or subtle gradient text.
- Modular type scale (1.25–1.333). Body text: `max-w-[65ch]`, `leading-relaxed`.
- Numbers in stats, tables, and metrics: always use `tabular-nums`. Use correct typographical quotes and em/en dashes.

## Step 3. Color & Palette

- Define OKLCH tokens in `@theme`: background, surface, text, muted text, border, and ONE accent color (+ hover state). Follow the 60/30/10 ratio.
- Avoid pure `#000` and `#fff` — use off-black (`oklch(0.14 0.01 260)`) and off-white.
- Reserve the accent color strictly for focus points: primary CTA, key value metric, active state.
- For dark mode: elevate surfaces by increasing lightness, not by stacking black shadows.

## Step 4. Composition & Craftsmanship ("Premium" Details)

- Generous whitespace: sections `py-24 md:py-32`, max container `max-w-7xl`. Break the grid intentionally: asymmetry, elements bleeding past container edges, layered overlays.
- 1px translucent borders (`border-white/10`), multi-layered soft shadows, subtle inner bevel highlights (`shadow-[inset_0_1px_0_rgb(255_255_255/0.08)]`).
- Depth: subtle grain texture (SVG noise at 3–6% opacity), diffuse colored glows behind key content, `backdrop-blur` for floating navigation bars.
- Real content and visuals: authentic product captures, custom diagrams, or curated photography. Never use placeholder "Lorem ipsum" or generic icons in colored circles.
- Micro-polish: custom text selection styling (`selection:`), styled scrollbars, favicon, OG metadata, and polished 404 pages.

## Step 5. Motion (React Motion / CSS)

- Animation library: `motion` (formerly framer-motion) or native CSS. Use View Transitions for route changes.
- Scroll reveal: `opacity 0→1` + `y 24→0`, stagger 60–80ms, easing `[0.22, 1, 0.36, 1]`, duration 500–700ms. Trigger once, never loop on scroll.
- Micro-interactions: buttons slightly elevate and illuminate on hover, press down on active (`scale-[0.98]`); cards feature spotlight/tilt following cursor; magnetic feel on primary CTA.
- Hero: word/character stagger entrance, subtle layer parallax, scroll-driven transforms (`useScroll` + `useTransform`).
- Animate only GPU-accelerated properties: `transform`, `opacity`, `filter`. Always support `prefers-reduced-motion`. Target a solid 60fps on mid-tier hardware.

## Step 6. Visual Self-Verification (Mandatory)

Inspect the page visually through screenshots:
1. Start the dev server. Capture screenshots at 375px, 768px, and 1440px across light and dark themes (via Playwright MCP or script).
2. Rate the result on a 10-point scale: hierarchy, typography, color harmony, whitespace, signature hook, and overall "wow factor".
3. If any metric scores below 8/10: identify the 3 weakest elements, refine them, and re-capture screenshots (up to 3 iterations).
4. Run the final check against `references/anti-slop.md`.

## Implementation Sequence

1. Brief → write `DESIGN.md`
2. Tokens (colors, fonts, radii) in `@theme`
3. Layout structure and mobile-first responsiveness
4. Hero section with signature visual hook
5. Secondary sections and interactive components
6. Motion, transitions, and micro-interactions
7. Screenshot-based visual verification
8. Performance optimization and accessibility checks
