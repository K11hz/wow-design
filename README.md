# WOW Design

Art director skill for Claude Code and AI coding agents. Helps build custom web interfaces in Next.js, React, Tailwind CSS, and Motion instead of default AI layouts.

## Contents

- `SKILL.md`: core instructions for project briefing, signature features, typography hierarchy, OKLCH palettes, motion, and screenshot verification loops.
- `references/directions.md`: visual directions covering font pairings, color ratios, layouts, and signature mechanics.
- `references/anti-slop.md`: checklist of common AI design mistakes to avoid.

## Installation

### Global skill (Claude Code)

Clone into your global Claude skills directory:

```bash
git clone https://github.com/K11hz/wow-design.git ~/.claude/skills/design-wow
```

### Project-specific skill

Clone into your repository's local skills directory:

```bash
git clone https://github.com/K11hz/wow-design.git .claude/skills/design-wow
```

## Usage

The skill triggers on prompts involving frontend design and visual polish, such as:
- *"Make this landing page look premium"*
- *"Redesign the hero section"*
- *"This UI looks boring and generic"*
- *"Design a landing page like Linear or Apple"*
- *"Fix our typography and color palette"*

### Workflow

1. Briefing: establish the design foundation and record it in `DESIGN.md`.
2. Tokens: set up OKLCH color variables and typography pairings in Tailwind `@theme`.
3. Structure: build section rhythm and mobile-first responsive layout.
4. Hero and signature element: implement one focal interactive or visual feature.
5. Motion: add micro-interactions and smooth scroll reveals with Motion.
6. Self-verification: capture responsive screenshots (375px, 768px, 1440px) via Playwright and iterate against the 10-point craft scale.

## License

MIT
