---
name: design-libera
description: "Visual and aesthetic design direction for web and UI. LIBERA Studio synthesis of impeccable design laws + high-end-visual-design pattern catalog. Self-contained for first-pass direction; optional deep-dive references if skill-web-design repository is available. Covers brand and product registers, OKLCH color strategy, typography, motion choreography, layout, hybrid surfaces, and AI slop prevention at two levels. Use alongside /ui-ux-libera for technical UX standards."
---

# Design Libera — Visual Design Direction
*LIBERA Studio synthesis — maggio 2026*

Aesthetic design intelligence for web and UI. Covers visual direction, color strategy, typography, motion, and layout for both brand and product surfaces.

Use alongside `/ui-ux-libera` for technical UX (accessibility, touch targets, performance, launch completeness). **When the two conflict, `/ui-ux-libera` wins** — see Conflict Resolution below.

---

## Step 0 — Choose Your Register

Identify before doing anything else. Everything downstream depends on this.

**Brand** — design IS the product: landing pages, marketing surfaces, campaign pages, portfolios, about pages. Goal: communicate, impress, convert. The visitor's impression is the deliverable.

**Product** — design SERVES the product: app UIs, dashboards, settings, authenticated surfaces, tools. Goal: earn familiarity, disappear into the task.

**If unclear:** use the dominant verb of the surface. A landing page sells → brand. A dashboard works → product.

**If asking is not appropriate**, classify by dominant user intent:
- sell, persuade, announce, recruit, impress → Brand
- create, manage, monitor, edit, configure, analyze → Product
- both present → apply Hybrid Surfaces below; do not force one register on the whole page.

---

## Conflict Resolution with /ui-ux-libera

When this skill conflicts with `/ui-ux-libera`, resolve in this order:

1. **Accessibility** — always wins. Contrast, reduced motion, focus visibility, target sizes.
2. **Task completion** — user must be able to complete the action without friction.
3. **Performance and responsiveness** — no motion or layout that degrades interaction on mobile or slow networks.
4. **Existing product design systems** — respect what's already built.
5. **Design Libera direction** — applies only after all the above are satisfied.

Examples where `/ui-ux-libera` wins: `py-24` section padding reduced on mobile for density; ambitious Brand motion blocked by `prefers-reduced-motion`; Drenched color blocked by contrast requirements; Button-in-Button modified for accessible target size and focus ring.

---

## Hybrid Surfaces

Do not force a single register on a page that has mixed jobs.

Assign register by zone:

| Zone type | Register |
|-----------|----------|
| Hero, story, proof, pricing, about, campaign | Brand |
| Editor, dashboard, form, settings, table, workflow, authenticated tool | Product |
| Shared chrome (nav, footer) | Product behavior; may receive Brand styling if it does not harm task clarity |

Brand may frame Product (wrapper, hero, onboarding), but Product interaction patterns must remain familiar and predictable. Never apply Brand expression to repetitive task surfaces.

---

## Shared Design Laws

Apply to every design, both registers.

### Color

Use OKLCH. Reduce chroma as lightness approaches 0 or 100 — high chroma at extremes looks garish.

Never use `#000` or `#fff`. Tint every neutral toward the brand hue (chroma 0.005–0.01 is enough to feel natural; not enough to read as "tinted").

**Pick a color strategy before picking colors:**

| Strategy | Surface coverage | Default for |
|----------|------------------|-------------|
| **Restrained** | Tinted neutrals + one accent ≤10% | Product UI, minimal brand |
| **Committed** | One saturated color 30–60% | Brand identity-driven pages |
| **Full palette** | 3–4 named roles, each used deliberately | Brand campaigns, data viz |
| **Drenched** | The surface IS the color | Brand heroes, campaign pages |

The "one accent ≤10%" rule is Restrained only. Committed / Full palette / Drenched exceed it on purpose. Don't collapse every design to Restrained by reflex.

### Theme

Dark vs. light is never a default. Before choosing, write one sentence of physical scene: who uses this, where, under what ambient light, in what mood. The sentence must force the answer — if it doesn't, add detail until it does.

"Dashboard for SaaS" does not force an answer. "SRE checking incident severity on a 27-inch monitor at 2am in a dim room" does.

### Typography

- Cap body line length at 65–75ch
- Hierarchy through scale + weight contrast — minimum 1.25 ratio between steps
- Flat scales (1.1× apart) read as uncommitted

### Layout

- Vary spacing for rhythm. Same padding everywhere is monotony.
- Cards are the lazy answer. Use them only when they're the best affordance for the content.
- Nested cards are wrong when they create redundant grouping or card-inside-card clutter. Double-Bezel (see Pattern Catalog) is allowed when the outer layer acts as a material frame, not a second content container.
- Don't wrap everything in a container. Most things don't need one.

### Motion

- Don't animate CSS layout properties (`width`, `height`, `top`, `left`, margins)
- Ease out with exponential curves. No bounce, no elastic.
  - `cubic-bezier(0.25, 1, 0.5, 1)` — quart out, smooth and refined
  - `cubic-bezier(0.16, 1, 0.3, 1)` — expo out, snappy and confident
- Exit animations at ~70% of enter duration
- All motion must respect `prefers-reduced-motion`. In reduced-motion mode, preserve state clarity with opacity, instant state changes, or shorter transitions — never remove state feedback entirely.

### Default-Refuse Patterns

Match-and-refuse by default. Allow only if you can state: (1) why this pattern is structurally needed, (2) why a simpler alternative is worse, (3) how it avoids the cliché form.

- **Side-stripe borders** — `border-left` or `border-right` >1px as a colored accent on cards, alerts, or list items. Default refuse; exceptions: changelog entries, code diff markers, severity alerts with documented rationale.
- **Gradient text** — `background-clip: text` + gradient background. Default refuse; exceptions: deliberate campaign typography with a clear brand reason.
- **Glassmorphism as default** — blur and glass cards used decoratively. Default refuse; see Ethereal Glass archetype for when glass is structurally justified.
- **Hero-metric template** — big number, small label, supporting stats, gradient accent. SaaS cliché; default refuse.
- **Identical card grids** — same-sized cards with icon + heading + text, repeated endlessly. Default refuse; exceptions: pricing comparison, directory listings, marketplace items with documented rationale.
- **Modal as first thought** — exhaust inline / progressive / slide-over alternatives first. Modals for high-stakes confirmation, quick-create, command palette, or media preview only.

### Copy

- Every word earns its place. No restated headings, no intros that repeat the title.
- Avoid em dashes as a default AI-copy rhythm. Use commas, colons, semicolons, or periods. Use em dashes only if the brand voice explicitly requires them.

---

## AI Slop Test

Run at two levels before finalizing any design. Both must pass.

**First-order** — if someone could guess the theme + palette from the category alone ("observability → dark blue", "healthcare → white + teal", "fintech → navy + gold", "crypto → neon on black"), it's the first training-data reflex. Rework the scene sentence and color strategy until the answer isn't obvious from the domain.

**Second-order** — if someone could guess the aesthetic family from category + anti-references ("AI tool that's not SaaS-cream → editorial-typographic", "fintech not navy → terminal-dark mode"), it's the trap one tier deeper. The first reflex was avoided; the second wasn't. Rework until both levels are non-obvious.

If someone can look at the result and say "AI made that" without hesitation, it has failed.

---

## Brand Register

### Font selection procedure

Every project. Never skip.

1. Write three concrete brand-voice words. Not "modern" or "elegant" — physical-object words: "warm and mechanical and opinionated", "calm and clinical and careful"
2. List the three fonts you'd reach for by reflex. If any appear on the reflex-reject list, they are blocked as first-choice defaults — discard them.
3. Browse a real catalog (Google Fonts, Pangram Pangram, Future Fonts, ABC Dinamo, Klim, Velvetyne) with the three words. Find the font for the brand as a *physical object*: a museum caption, a 1970s terminal manual, a fabric label, a concert poster, a receipt from a mid-century diner. Reject the first option that "looks designy."
4. Cross-check: "elegant" is not necessarily serif. "Technical" is not necessarily sans. "Warm" is not Fraunces. If the final pick aligns with your original reflex, start over.

### Reflex-reject font list

Training-data defaults that create monoculture — blocked as first-choice defaults, not universally banned. Use one only if required by an existing brand system, or if used in a way that demonstrably avoids the common template fingerprint.

Fraunces · Newsreader · Lora · Crimson · Crimson Pro · Crimson Text · Playfair Display · Cormorant · Cormorant Garamond · Syne · IBM Plex Mono · IBM Plex Sans · IBM Plex Serif · Space Mono · Space Grotesk · Inter · DM Sans · DM Serif Display · DM Serif Text · Outfit · Plus Jakarta Sans · Instrument Sans · Instrument Serif

### Reflex-reject aesthetic lanes

Currently saturated aesthetic families. Default refuse unless the brief structurally requires it:

- **Editorial-typographic** — display serif (often italic) + small mono labels + ruled separators + monochromatic restraint. By 2026, every Stripe-adjacent and Notion-adjacent brand has landed here. Fingerprint: three rule-separated columns, italic Newsreader/Fraunces headline, lowercase tracked metadata, no imagery.

### Brand permissions

Brand can afford things product cannot:
- Ambitious first-load motion and scroll-triggered transitions
- Single-purpose viewports — one dominant idea per fold, long scroll, deliberate pacing
- Typographic risk: enormous display type, unexpected italic cuts, mixed cases, a single oversize word as hero
- Drenched or committed color strategies — palette IS voice
- Art direction per section — different visual worlds per section if the narrative demands it

### Brand bans

- Monospace as lazy shorthand for "technical" when the brand isn't technical
- Large rounded-corner icons above every heading — screams template
- All-caps body copy — reserve for short labels and headings
- Timid palettes and average layouts — safe = invisible
- Defaulting to editorial-magazine aesthetics (display serif + italic + broadsheet grid) on briefs that aren't magazine-shaped

---

## Product Register

### Typography

- System fonts are legitimate: `-apple-system, BlinkMacSystemFont, "Segoe UI", system-ui, sans-serif` — native feel on every platform, loads instantly
- One family is often right — product UIs don't need a display/body pairing
- Fixed rem scale, not fluid — `clamp()` headings in product UI degrade spatial predictability
- Tighter scale ratio: 1.125–1.2 between steps

### Color

Product defaults to **Restrained**. Accent color for: primary actions, current selection, state indicators. Not decoration.

### Density

Choose one before designing:

| Mode | Use when | Controls |
|------|----------|----------|
| **Compact** | Admin panels, data tables, power users, desktop-first tools | Tight spacing, smaller type, high information density |
| **Comfortable** | SaaS dashboards, CRM, collaboration tools | Standard 4/8pt rhythm, readable data |
| **Spacious** | Onboarding, mobile apps, consumer productivity | Generous padding, breathing room, lower cognitive load |

Density governs spacing scale, type scale, table row height, card usage, and navigation weight. Do not mix modes within a surface unless zones have clearly different jobs.

### Layout

- Predictable grids. Consistency IS an affordance — users navigate faster when structure is expected.
- Familiar patterns are features: top bar, side nav, breadcrumbs, tabs, form layouts have earned trust. Don't reinvent for flavor.
- Responsive behavior is structural (collapse sidebar, responsive table), not fluid typography.

### Brand Moments in Product

Product may use Brand-level expression only in isolated surfaces:
- Onboarding and first-run welcome screens
- Empty states (first use)
- Upgrade / paywall surfaces
- Success milestones and celebration moments
- Report covers and public share pages

Never apply Brand expression to repetitive task surfaces: data tables, settings, forms, nav, dashboards in daily use.

### Product bans

- Decorative motion that doesn't convey state
- Inconsistent component vocabulary across screens — if "save" looks different in two places, one is wrong
- Display fonts in UI labels, buttons, or data
- Reinventing standard affordances for flavor: custom scrollbars, non-standard modals, weird form controls

---

## Pattern Catalog — Brand Register

Before writing code, silently pick one archetype from each group. The combination determines the visual world.

### A. Vibe Archetypes (pick 1)

1. **Ethereal Glass** (SaaS / AI / Tech) — OLED black (`oklch(8% 0.01 260)`), radial mesh gradients with subtle glowing orbs, `backdrop-blur-2xl`, `border border-white/10` hairlines, wide geometric Grotesk. Glass is valid here because depth and translucency are structural to the aesthetic — not decorative. Requirements: blur only on fixed/sticky elements; contrast remains AA; a no-blur fallback exists for `@supports not (backdrop-filter: blur())` and reduced-motion environments.
2. **Editorial Luxury** (Lifestyle / Real Estate / Agency) — warm creams (`oklch(97% 0.008 80)`), muted sage, or deep espresso tones. Variable Serif for massive headings. CSS noise overlay (`opacity-[0.03]`) for physical paper feel.
3. **Soft Structuralism** (Consumer / Health / Portfolio) — silver-grey or white backgrounds. Massive bold Grotesk. Floating components with highly diffused ambient shadows.

### B. Layout Archetypes (pick 1)

1. **Asymmetrical Bento** — masonry CSS Grid of varying card sizes (`col-span-8 row-span-2` next to stacked `col-span-4`). Mobile: single column, all `col-span` reset to 1, generous `gap-6`.
2. **Z-Axis Cascade** — elements stacked like physical cards, slightly overlapping with `−2deg` or `3deg` rotation. Mobile: remove all rotations and negative-margin overlaps below 768px — they cause touch-target conflicts.
3. **Editorial Split** — massive typography on left (`w-1/2`), interactive content on right. Mobile: full-width vertical stack (`w-full`), typography block on top.

**Universal mobile override:** Any asymmetric layout above `md:` MUST collapse to `w-full`, `px-4`, `py-8` below 768px. Never `h-screen` — always `min-h-[100dvh]` (iOS Safari viewport jump fix).

### C. Double-Bezel Architecture

Use for premium cards, images, and feature containers. The outer layer is a material frame, not a second content container — this is not a nested card.

- **Outer shell** — `bg-black/5 ring-1 ring-black/5 p-1.5 rounded-[2rem]`
- **Inner core** — distinct background, `shadow-[inset_0_1px_1px_rgba(255,255,255,0.15)]`, radius `rounded-[calc(2rem-0.375rem)]` for mathematically concentric curves

### D. Button-in-Button Pattern

Trailing icons (arrows `↗`) must nest inside their own circular wrapper flush with the button's right inner padding — never sitting naked next to the text.

```html
<button class="flex items-center gap-2 rounded-full px-6 py-3 bg-neutral-950 text-neutral-50">
  Get started
  <span class="w-8 h-8 rounded-full bg-neutral-50/10 flex items-center justify-center">↗</span>
</button>
```

### E. Spatial Rhythm

- Section padding minimum `py-24`, target `py-32` to `py-40` — let the design breathe heavily
- Eyebrow tags before major H1/H2: `rounded-full px-3 py-1 text-[10px] uppercase tracking-[0.2em] font-medium`
- Double standard padding everywhere — whitespace is a design material

### F. Motion Choreography

- All transitions: `cubic-bezier(0.32, 0.72, 0, 1)` — premium, confident
- Scroll entry: `translate-y-16 blur-md opacity-0` → `translate-y-0 blur-0 opacity-100` over 800ms+
- Hamburger → X morph: `rotate-45` and `-rotate-45` with absolute positioning, not disappear/reappear
- Staggered nav link reveal: `delay-100`, `delay-150`, `delay-200` per item
- Button hover: `active:scale-[0.98]`, inner icon `group-hover:translate-x-1 group-hover:-translate-y-[1px] scale-105`
- In reduced-motion mode: remove `blur` and translate transforms; keep opacity transitions ≤200ms.

### G. Performance Guardrails

- Animate only `transform` and `opacity` — never layout-triggering properties
- `backdrop-blur` only on fixed/sticky elements — never on scrolling containers (continuous GPU repaints on mobile)
- `will-change: transform` only on elements actively animating, never preemptively
- Scroll-triggered animations: `IntersectionObserver` only — never `window.addEventListener('scroll')`

---

## LIBERA Fingerprint Test

Before finalizing any Brand design, check whether it overuses this skill's own defaults:

- double-bezel on every card and container
- pill eyebrow tag above every heading
- button-in-button arrow on every CTA
- Asymmetrical Bento as the default layout without content reason
- OLED black + glass + radial glow for any tech brief
- `py-32`+ section padding without content that needs that space
- scroll blur reveal (`blur-md → blur-0`) on every section entry

**If 3 or more are present, remove or replace at least one.** Anti-slop includes avoiding this skill's own fingerprint when it becomes recognizable.

---

## Execution Protocol

1. **[REGISTER]** Brand or product? Use the dominant verb. If unclear, use the fallback classification. If hybrid, split by zone.
2. **[CONFLICT CHECK]** If used alongside `/ui-ux-libera`, confirm no conflicts on accessibility, performance, or responsiveness before proceeding.
3. **[SCENE]** Write the physical scene sentence. It must force the dark/light answer.
4. **[STRATEGY]** Choose color strategy explicitly: Restrained / Committed / Full palette / Drenched. Brand rarely defaults to Restrained.
5. **[VARIANCE]** Brand only: pick one Vibe Archetype + one Layout Archetype from the Pattern Catalog.
6. **[SLOP TEST]** Run both levels. If predictable at either level, return to step 4.
7. **[BUILD]** Implement. Brand: Double-Bezel, Spatial Rhythm, Motion Choreography. Product: system fonts, predictable grids, Restrained color, familiar patterns, density mode.
8. **[FINGERPRINT]** Run LIBERA Fingerprint Test. If 3+ defaults present, remove at least one.
9. **[CHECKLIST]** Final pass before delivering.

---

## Pre-Output Checklist

**Both registers**
- [ ] Register identified and confirmed (brand / product / hybrid zones)
- [ ] Physical scene sentence written — it forced the dark/light answer
- [ ] Color strategy chosen explicitly — not defaulted
- [ ] First-order slop check: palette not predictable from category alone
- [ ] Second-order slop check: aesthetic lane not predictable from category + anti-references
- [ ] No default-refuse patterns used without documented structural rationale
- [ ] All transitions use custom cubic-bezier — no `linear` or default `ease`
- [ ] `backdrop-blur` only on fixed/sticky elements
- [ ] Full-height sections: `min-h-[100dvh]`, not `h-screen`
- [ ] Scroll animations use IntersectionObserver, not scroll event listener
- [ ] Motion respects `prefers-reduced-motion`
- [ ] Copy: no em dashes unless brand voice requires them, no restated headings

**Brand only**
- [ ] Font procedure followed — no fonts from reflex-reject list as first choice
- [ ] No aesthetic lanes from reflex-reject lanes
- [ ] Double-Bezel on major cards/containers (outer = frame, not second content container)
- [ ] Section padding minimum `py-24`
- [ ] Motion uses `cubic-bezier(0.32, 0.72, 0, 1)` — no `ease-in-out`
- [ ] LIBERA Fingerprint Test passed — fewer than 3 defaults stacked
- [ ] Overall impression reads as designed with intent, not assembled from templates

**Product only**
- [ ] Density mode chosen (Compact / Comfortable / Spacious) — consistent throughout
- [ ] Component vocabulary consistent across all screens
- [ ] No decorative motion — all motion conveys state
- [ ] Standard navigation patterns used, not reinvented
- [ ] Accent color only on primary actions, selection, state indicators
- [ ] Brand Moments limited to appropriate surfaces (onboarding, empty state, success)

**Hybrid surfaces**
- [ ] Zones explicitly identified (Brand zone / Product zone)
- [ ] Product zones use familiar patterns regardless of Brand framing
- [ ] No Brand expression on repetitive task surfaces

---

## External References

This skill is self-contained for first-pass visual direction. The `reference/` files in [skill-web-design](https://github.com/sayitlouderdev/skill-web-design) are optional deep-dives.

**If the repository is not available:** do not claim to have read these files. Continue with this document only.

| Need | File |
|------|------|
| Brand design direction | `brand.md` |
| Product UI principles | `product.md` |
| OKLCH, palettes, dark mode theory | `color-and-contrast.md` |
| Font scale, fluid type, OpenType | `typography.md` |
| Duration rules, easing, stagger | `motion-design.md` |
| Spacing systems, squint test | `spatial-design.md` |
| Grid vs Flex, card grid anti-patterns | `layout.md` |
| Mobile-first, safe areas, srcset | `responsive-design.md` |
| 8 interactive states, focus rings | `interaction-design.md` |
| Working memory, cognitive load | `cognitive-load.md` |
| Button labels, error messages, i18n | `ux-writing.md` |
| Amplify a bland design | `bolder.md` |
| Tone down an aggressive design | `quieter.md` |
| Final quality pass | `polish.md` |

---

*LIBERA Studio synthesis — maggio 2026*
*Fonti: impeccable (Apache 2.0) + high-end-visual-design*
*Repository: https://github.com/sayitlouderdev/skill-web-design*
