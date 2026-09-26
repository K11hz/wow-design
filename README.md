# WOW Design

An art director skill for Claude Code and AI coding agents. Guides the creation of distinctive, high-craft web experiences using Next.js, React, Tailwind CSS, and Motion without generic AI design patterns.

## Contents

- `SKILL.md` — Core instructions: project briefing, single signature feature, typography hierarchy, OKLCH color palettes, motion choreography, and screenshot verification loops.
- `references/directions.md` — Curated visual directions (curated font pairings, color ratios, layout aesthetics, and signature mechanics).
- `references/anti-slop.md` — Checklist of common AI design pitfalls to avoid.

## Installation

### Global Skill (Claude Code)

Clone directly into your global Claude skills directory:

```bash
git clone https://github.com/K11hz/wow-design.git ~/.claude/skills/design-wow
```

### Project-Specific Skill

Clone into your repository's local skills directory:

```bash
git clone https://github.com/K11hz/wow-design.git .claude/skills/design-wow
```

## Usage

The skill triggers automatically on prompts involving frontend design and visual polish, such as:
- *"Make this landing page look premium"*
- *"Redesign the hero section"*
- *"This UI looks boring and generic"*
- *"Design a landing page like Linear or Apple"*
- *"Fix our typography and color palette"*

### Workflow Sequence

1. **Briefing** — Establish the design foundation and record it in `DESIGN.md`.
2. **Tokens** — Set up OKLCH color variables and typography pairings in Tailwind `@theme`.
3. **Structure** — Build section rhythm and mobile-first responsive layout.
4. **Hero & Signature Element** — Implement one memorable interactive or visual focal point.
5. **Motion** — Add subtle micro-interactions and smooth scroll reveals with Motion.
6. **Self-Verification** — Capture responsive screenshots (375px, 768px, 1440px) via Playwright and iterate against a 10-point craft scale.

## License

MIT
