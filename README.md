# skill-web-design

> A Claude Code skill for creating polished web and UI designs from structured website plans.

**Maintained by [LIBERA Studio](https://github.com/liberastudio-mx/) · License: Apache 2.0**

---

## What this is

`skill-web-design` is a Claude Code skill focused on web and UI design.

It helps Claude Code improve the visual layer of a website after the structure, content hierarchy, and UX flow have already been defined. The skill provides design principles, reference material, and practical guidance for layout, typography, color, spacing, motion, interaction, responsiveness, accessibility, and final UI polish.

This repository was built by analyzing existing Claude Code design skills, extracting useful design knowledge, and synthesizing it into a focused, self-contained skill for LIBERA Studio workflows.

The reference documents in `reference/` are substantially derived from the `impeccable` project, licensed under Apache 2.0. See [NOTICE.md](NOTICE.md) for full attribution.

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

## What it is for

Use this skill when you already have a website structure or page layout and want Claude Code to improve the visual design.

It is especially useful for:

- Turning a basic layout into a polished interface
- Improving typography, spacing, hierarchy, and visual rhythm
- Creating stronger color systems and better contrast
- Making interfaces feel more intentional and less generic
- Adding motion, interaction details, and UI polish
- Reviewing a design before shipping
- Reducing generic AI-generated visual patterns

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

## How to use

Use this repository as a Claude Code skill or as a design reference library.

Example prompts:

```text
Use the skill-web-design skill to improve the visual design of this landing page.
```

```text
Read reference/color-and-contrast.md and improve the current color palette.
```

```text
Review this UI using reference/polish.md and suggest final design improvements.
```

```text
Use reference/typography.md to improve the type scale and text hierarchy.
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
