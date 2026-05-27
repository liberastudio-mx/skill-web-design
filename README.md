# skill-web-design

> A curated web and UI design knowledge base for Claude Code — built by analyzing and synthesizing content from the best available design skills.

**Maintained by [LIBERA Studio](https://github.com/sayitlouderdev) · License: Apache 2.0**

---

## What this is

This repository is a design knowledge base for AI-assisted frontend development. It contains design principles, reference documents, and skill baselines that inform the `design-libera` Claude Code skill.

It was **not built from scratch**. It was built by:

1. **Analyzing** multiple existing Claude Code design skills (`impeccable`, `high-end-visual-design`, `frontend-design`, `minimalist-ui`, `design-taste-frontend`)
2. **Extracting** the reference documents from `impeccable` — the most architecturally sophisticated skill available, containing design laws, register-specific rules, and reference guides covering motion, color, typography, layout, interaction, and more
3. **Preserving** the original SKILL.md files from each tool as comparative baselines in `skills/`
4. **Synthesizing** these into `design-libera` — a self-contained skill without external dependencies

The reference documents in `reference/` are substantially the work of the `impeccable` project (Apache 2.0). See [NOTICE.md](NOTICE.md) for full attribution.

---

## Repository structure

```
skill-web-design/
├── reference/          ← Design knowledge docs (source: impeccable, Apache 2.0)
├── LICENSE             ← Apache 2.0
├── NOTICE.md           ← Third-party attribution
└── CONTRIBUTING.md     ← How to contribute
```

### reference/ — 29 design knowledge documents

Design reference documents from the `impeccable` skill. Each file covers a specific design domain and works standalone — no scripts, no external dependencies.

| File | Domain | Key content |
|------|--------|-------------|
| `brand.md` | Brand design | Font selection procedure, reflex-reject font list, aesthetic lane test, brand permissions vs. product permissions |
| `product.md` | Product/app UI | Earned familiarity principle, system fonts, density, standard affordances as features |
| `color-and-contrast.md` | Color | OKLCH color space, tinted neutrals, palette structure, dark mode theory, WCAG |
| `typography.md` | Typography | Modular scale, fluid type with `clamp()`, OpenType features, variable fonts, web font loading |
| `motion-design.md` | Animation | 100/300/500 duration rule, cubic-bezier curves, stagger patterns, perceived performance |
| `spatial-design.md` | Layout & spacing | 4pt base system, squint test, visual hierarchy through multiple dimensions |
| `layout.md` | Layout | Spacing systems, Grid vs Flexbox, card grid anti-patterns, visual rhythm |
| `responsive-design.md` | Responsive | Mobile-first, pointer/hover media queries, safe areas, `srcset`, art direction |
| `interaction-design.md` | Interaction | 8 interactive states, focus rings, modals, popover API, CSS anchor positioning |
| `cognitive-load.md` | UX psychology | 3 types of cognitive load, working memory rule (≤4 items), 8 common violations |
| `ux-writing.md` | Copy | Button label patterns, error message formula, empty states, translation expansion |
| `bolder.md` | Design direction | How to amplify safe/bland designs — anti-AI-slop guidance, contrast not chaos |
| `quieter.md` | Design direction | How to tone down overstimulating designs |
| `distill.md` | Design direction | Strip to essence, remove complexity without losing meaning |
| `overdrive.md` | Design direction | Push past conventional limits |
| `delight.md` | UX delight | Micro-interactions, copy personality, easter eggs, celebration patterns |
| `animate.md` | Animation | Animation direction and choreography for UI |
| `colorize.md` | Color | Adding strategic color to monochromatic UIs |
| `typeset.md` | Typography | Typography improvement checklist |
| `heuristics-scoring.md` | UX audit | Heuristic evaluation scoring framework |
| `critique.md` | Design review | Design critique methodology |
| `polish.md` | Quality | Final quality pass checklist before shipping |
| `onboard.md` | UX patterns | First-run flows, empty states, activation |
| `adapt.md` | Responsive | Device and screen size adaptation |
| `clarify.md` | Copy | UX copy clarity improvements |
| `harden.md` | Production | Production readiness: errors, i18n, edge cases |
| `audit.md` | Quality | Technical quality checks (a11y, performance, responsive) |
| `optimize.md` | Performance | UI performance diagnosis and fixes |
| `personas.md` | Research | User persona frameworks for design context |

### skills/ — original design skill baselines

The original SKILL.md files from each source tool, preserved as-is for reference and comparison.

| File | Source | Focus |
|------|--------|-------|
| `impeccable-core.md` | [impeccable](https://github.com/impeccable-dev/impeccable) | Design laws, color strategy axis (Restrained→Drenched), AI slop test (2 levels), brand/product register routing |
| `high-end-visual-design.md` | high-end-visual-design skill | Variance Engine (3 archetypes), Double-Bezel nested architecture, premium motion choreography |
| `frontend-design.md` | [Claude Plugins Official](https://github.com/anthropics/claude-code-plugins) | Anti-slop creative direction, bold aesthetic choices |
| `minimalist-ui.md` | minimalist-ui skill | Editorial minimalism, precise color values, monochrome strategy |
| `design-taste-frontend.md` | design-taste-frontend skill | DESIGN_VARIANCE / MOTION_INTENSITY / VISUAL_DENSITY dial system |

---

## How to use

### As a Claude Code knowledge base

Reference these files in Claude Code sessions when working on design:

```
Read reference/brand.md and apply the font selection procedure to this project.
```

```
Read reference/color-and-contrast.md. The current palette feels lifeless — what should change?
```

### With design-libera (coming soon)

The `design-libera` Claude Code skill uses this repository as its knowledge base. Once available, install it in `~/.claude/commands/design-libera.md`.

### Standalone reading

Each document in `reference/` is designed to be read and applied directly. No tools, scripts, or frameworks required.

---

## What this is NOT

- Not a complete replacement for any of the source tools
- Not a tutorial or course
- Not a design system generator
- Not a tool with a CLI or scripts (see [skill-ui-ux-Libera](https://github.com/sayitlouderdev/skill-ui-ux-Libera) for the searchable CSV-based design system)

---

## Related repositories

| Repository | What it contains |
|------------|-----------------|
| [skill-ui-ux-Libera](https://github.com/sayitlouderdev/skill-ui-ux-Libera) | UI/UX skill with 30 CSV databases (161 color palettes, 57 font pairings, 50+ styles), Python search engine |

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License and attribution

This repository is licensed under **Apache 2.0**. See [LICENSE](LICENSE).

The content in `reference/` is substantially derived from the `impeccable` project (Apache 2.0). The files in `skills/` are the original works of their respective authors. See [NOTICE.md](NOTICE.md) for full third-party attribution.
