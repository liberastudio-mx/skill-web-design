# skill-web-design

> A Claude Code skill for creating polished web and UI designs that refuse to look AI-generated.

**Maintained by [LIBERA Studio](https://github.com/liberastudio-mx/) · License: Apache 2.0**

---

## What this is

`skill-web-design` is a Claude Code skill for visual design direction on web and UI projects.

It covers brand and product registers, OKLCH color strategy, typography, motion choreography, layout archetypes, and a two-level AI slop prevention system. The skill provides design principles, reference material, and practical guidance that produces structurally distinct sites rather than template variations.

This repository was built by analyzing existing Claude Code design skills, extracting useful design knowledge, and synthesizing it into a focused, self-contained skill for LIBERA Studio workflows.

The reference documents in `reference/` are substantially derived from the `impeccable` project, licensed under Apache 2.0. See [NOTICE.md](NOTICE.md) for full attribution.

---

See [CHANGELOG.md](CHANGELOG.md) for version history. Current version: **1.1.1**.

## What's new in v1.1.0

- **Four operating modes** — Build (default), Audit, Redesign, Study. Each has its own protocol and output format.
- **Study mode** — analyze any admired design and extract a portable Design DNA brief (scene, register, vibe archetype, color strategy, typography, motion, elements to replicate).
- **Audit mode** — score existing code or screenshots against design patterns without making edits. Structured output with PASS/WARN/FAIL per category.
- **10 Vibe Archetypes** (expanded from 3) — Ethereal Glass, Editorial Luxury, Soft Structuralism, Terminal Noir, Warm Craft, Clinical Precision, Vivid Commerce, Motion Studio, Analog Revival, Civic Structure. Each includes default scene, color strategy, font direction, and when to refuse it.
- **Gate IDs** — pre-output checklist items now have IDs (`[G-01]`–`[G-13]`, `[B-01]`–`[B-09]`, `[P-01]`–`[P-06]`, `[H-01]`–`[H-03]`). Cite failures by ID in reviews.
- **Macrostructure documentation** — Execution Protocol now includes a step to add a comment to the root component documenting Register, Vibe Archetype, Layout Archetype, and Color Strategy chosen.

---

## Repository structure

```text
skill-web-design/
├── reference/          ← Design knowledge documents
├── SKILL.md            ← Claude Code skill instructions
├── README.md           ← Repository documentation
├── LICENSE             ← Apache 2.0 license
├── NOTICE.md           ← Third-party attribution
└── CONTRIBUTING.md     ← Contribution guidelines
```

---

## Operating modes

| Mode | Trigger | What it does |
| ---- | ------- | ------------ |
| **Build** | (default) | Creates new UI with selected register, theme, and macrostructure |
| **Audit** | "audit questo design", "score questo" | Scores existing code against design patterns. No edits. |
| **Redesign** | "ridisegna", "cambia stile" | Preserves copy and IA, rebuilds visual fingerprint |
| **Study** | "analizza questo sito", "estrai il DNA" | Extracts Design DNA from a URL or screenshot |

---

## What it is for

Use this skill when you want Claude Code to make strong visual design decisions, not just follow instructions.

It is especially useful for:

- Creating brand landing pages and marketing surfaces that don't look AI-generated
- Turning a basic layout into a polished, intentional interface
- Auditing existing UI code for design pattern violations
- Extracting the design DNA from an admired site to replicate its approach
- Improving typography, spacing, hierarchy, and visual rhythm
- Creating stronger color systems using OKLCH strategy
- Adding motion, interaction details, and UI polish
- Reducing generic AI-generated visual patterns with a two-level slop test

This skill is meant to work after the structure and UX planning stage. For website structure, content hierarchy, and UX flow, use [`skill-ui-ux-Libera`](https://github.com/liberastudio-mx/skill-ui-ux-Libera).

---

## Reference documents

The `reference/` folder contains design knowledge documents covering key UI and web design domains.

| File | Domain | Key content |
|------|--------|-------------|
| `brand.md` | Brand design | Font selection, aesthetic direction, brand/product fit |
| `product.md` | Product UI | Familiarity, density, system conventions, app usability |
| `color-and-contrast.md` | Color | OKLCH, tinted neutrals, palettes, dark mode, WCAG |
| `typography.md` | Typography | Type scales, fluid type, OpenType, variable fonts |
| `motion-design.md` | Motion | Timing, easing, choreography, perceived performance |
| `spatial-design.md` | Spacing | 4pt systems, hierarchy, layout balance |
| `layout.md` | Layout | Grid, flexbox, rhythm, card layout patterns |
| `responsive-design.md` | Responsive design | Mobile-first design, safe areas, adaptive images |
| `interaction-design.md` | Interaction | States, focus rings, modals, popovers |
| `cognitive-load.md` | UX psychology | Working memory, complexity, attention management |
| `ux-writing.md` | UX writing | Buttons, errors, empty states, microcopy |
| `bolder.md` | Design direction | Making safe designs more expressive |
| `quieter.md` | Design direction | Reducing visual noise |
| `distill.md` | Design direction | Simplifying without losing meaning |
| `overdrive.md` | Design direction | Pushing design intensity |
| `delight.md` | UX delight | Micro-interactions, personality, celebration |
| `animate.md` | Animation | UI animation direction and choreography |
| `colorize.md` | Color | Adding strategic color |
| `typeset.md` | Typography | Typography improvement checklist |
| `heuristics-scoring.md` | UX audit | Heuristic evaluation framework |
| `critique.md` | Design review | Design critique methodology |
| `polish.md` | Quality | Final visual polish checklist |
| `onboard.md` | UX patterns | First-run flows and activation |
| `adapt.md` | Responsive | Device and screen adaptation |
| `clarify.md` | UX writing | Copy clarity improvements |
| `harden.md` | Production | Errors, i18n, edge cases |
| `audit.md` | Quality | Accessibility, performance, responsive checks |
| `optimize.md` | Performance | UI performance diagnosis and fixes |
| `personas.md` | Research | Persona frameworks for design context |

---

## Install

Copy the skill file into your Claude Code commands directory:

```bash
# macOS / Linux
cp SKILL.md ~/.claude/commands/design-libera.md
```

```powershell
# Windows
Copy-Item SKILL.md "$env:USERPROFILE\.claude\commands\design-libera.md"
```

Invoke with `/design-libera` in any Claude Code session. For the optional reference deep-dives, clone this repository to a stable location (LIBERA convention: `D:\dev\skill-web-design` on Windows, `~/dev/skill-web-design` on macOS/Linux).

---

## How to use

Use this repository as a Claude Code skill or as a design reference library.

**Build mode (default):**
```text
Use /design-libera to design this landing page.
```

**Audit mode:**
```text
/design-libera — audit this component for design pattern violations
```

**Study mode:**
```text
/design-libera — analizza questo sito e dimmi cosa usare per replicarlo: https://example.com
```

**Redesign mode:**
```text
/design-libera — ridisegna questa pagina mantenendo il contenuto attuale
```

**Reference deep-dives:**
```text
Read reference/color-and-contrast.md and improve the current color palette.
```

```text
Use reference/motion-design.md to add subtle, high-quality interaction motion.
```

---

## What this is not

This repository is not:

- A complete design system generator
- A UI component library
- A frontend framework
- A CLI tool
- A replacement for UX strategy or information architecture
- A collection of the original source skills used during research

For structure, UX flow, and website planning, see [`skill-ui-ux-Libera`](https://github.com/liberastudio-mx/skill-ui-ux-Libera).

---

## Related repositories

| Repository | What it contains |
|------------|-----------------|
| [`skill-ui-ux-Libera`](https://github.com/liberastudio-mx/skill-ui-ux-Libera) | Claude Code skill for website structure, UX flow, content hierarchy, and UI planning |

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License and attribution

This repository is licensed under **Apache 2.0**. See [LICENSE](LICENSE).

Some reference material is derived from the `impeccable` project, licensed under Apache 2.0. See [NOTICE.md](NOTICE.md) for full third-party attribution.
