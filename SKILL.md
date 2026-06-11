---
name: design-libera
version: "1.1.1"
description: "Visual and aesthetic design direction for web and UI. LIBERA Studio synthesis of impeccable design laws + high-end-visual-design pattern catalog. Self-contained for first-pass direction; optional deep-dive references if skill-web-design repository is available. Covers brand and product registers, OKLCH color strategy, typography, motion choreography, layout, and AI slop prevention at two levels. Modes: Build (default), Audit, Redesign, Study."
---

# Design Libera — Visual Design Direction

Aesthetic design intelligence for web and UI. Covers visual direction, color strategy, typography, motion, and layout for both brand and product surfaces.

Use alongside `/ui-ux-libera` for technical UX (accessibility, touch targets, performance, launch completeness). **When the two conflict, `/ui-ux-libera` wins** — see Conflict Resolution below.

---

## Mode Selection

Identify your mode before proceeding. Default is **Build**.

| Mode | Trigger phrases | What it does |
| ---- | --------------- | ------------ |
| **Build** | (default) | Creates new UI with selected register, theme, and macrostructure. Runs all gate checks. |
| **Audit** | "audit questo design", "valuta questo UI", "audita este diseño", "cosa non va", "score questo" | Scores existing code or screenshot against design patterns. No edits made. |
| **Redesign** | "ridisegna", "rediseña", "rediseña", "cambia stile", "stessa struttura diverso look", "preserva il contenuto" | Preserves copy and information architecture. Rebuilds visual fingerprint from scratch. |
| **Study** | "analizza questo sito", "analiza este sitio", "estrai il DNA", "voglio replicare questo stile", "cosa usa questo design" | Extracts design DNA from a URL or screenshot. Produces a portable design brief. |

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
- **Staggered card offsets** — `md:mt-N` on alternating grid cards to simulate a cascade or bento offset. Default refuse; the grid collapses to a single column on mobile and the offsets become misaligned rows with no visual logic. Use the Z-Axis Cascade archetype if vertical offset is structurally required.
- **CSS-class gradient text** — custom utility classes or keyframe animations applying `background-clip: text` with a gradient background. Same rule as inline gradient text. Default refuse.

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

Each archetype includes default scene, color strategy, font direction, and when to refuse it.

1. **Ethereal Glass** (SaaS / AI / Tech)
   OLED black (`oklch(8% 0.01 260)`), radial mesh gradients with subtle glowing orbs, `backdrop-blur-2xl`, `border border-white/10` hairlines, wide geometric Grotesk. Glass is valid here because depth and translucency are structural — not decorative. Requirements: blur only on fixed/sticky elements; contrast remains AA; no-blur fallback for `@supports not (backdrop-filter: blur())` and reduced-motion environments.
   *Refuse when:* the brief isn't AI/tech/cloud-native — this is the most overused SaaS aesthetic by 2026.

2. **Editorial Luxury** (Lifestyle / Real Estate / Agency)
   Warm creams (`oklch(97% 0.008 80)`), muted sage, or deep espresso tones. Variable Serif for massive headings. CSS noise overlay (`opacity-[0.03]`) for physical paper feel.
   *Refuse when:* the brand is digital-first with no physical analog.

3. **Soft Structuralism** (Consumer / Health / Portfolio)
   Silver-grey or white backgrounds. Massive bold Grotesk. Floating components with highly diffused ambient shadows.
   *Refuse when:* the brand needs strong color identity or dark mode.

4. **Terminal Noir** (Dev tools / CLI / Security / Infrastructure)
   Near-black canvas (`oklch(10% 0.008 200)`), monospace primary font, phosphor green / amber / cyan accent at max 10%, dense information layout, no decorative elements. The aesthetic is the tool — it should feel like something that works, not something that looks good.
   *Refuse when:* the audience is non-technical or the brief explicitly asks for approachability.

5. **Warm Craft** (Food / Artisan / Indie / Sustainable / Local)
   Earthy ochres, terracotta, forest green. Irregular grid, slight imperfection tolerated. Handwritten or humanist serif. Grain texture overlay. The page feels made by a person, not assembled by a system.
   *Refuse when:* the brand needs to signal scale, precision, or enterprise credibility.

6. **Clinical Precision** (Health / Medical / SaaS data / Research / Pharma)
   Pure white or near-white background, extreme whitespace, geometric sans at regular weight, one blue or teal accent at max 8%, precise 8pt grid, no decorative elements. Every element earns its place by conveying information.
   *Refuse when:* the brief calls for warmth, personality, or emotional engagement.

7. **Vivid Commerce** (E-commerce / Retail / Consumer brand / FMCG)
   High-contrast, product-forward. Strong hero with product photography. Bold color block headers. Price and CTA always visible. Conversion architecture over aesthetic expression. Color Committed or Drenched strategy.
   *Refuse when:* the brand is premium/luxury — switch to Editorial Luxury instead.

8. **Motion Studio** (Creative agency / Portfolio / Film / Music / Event)
   Dark canvas, oversized display type, scroll-driven animation is structural (not decorative), cinematic section transitions. The motion IS the product — it demonstrates the studio's craft. Frame every section as a scene.
   *Refuse when:* the client needs to communicate information quickly or the audience is impatient.

9. **Analog Revival** (Music / Print / Publishing / Zine / Indie label)
   Grain, muted desaturated palette, editorial grid from print tradition (columns, rules, folios). Mixes grotesque and slab. Physical media references: LP sleeve, magazine spread, concert poster, receipt. Intentional rawness.
   *Refuse when:* the brand is digital-native with no physical heritage or the audience skews corporate.

10. **Civic Structure** (NGO / Government / Education / Documentation / Open source)
    High accessibility, predictable hierarchy, generous whitespace, system sans, conservative color (one civic blue or green), no decorative motion. Clarity over expression — the content is the point.
    *Refuse when:* the brief requires personality or differentiation over trustworthiness.

---

### B. Layout Archetypes (pick 1)

1. **Asymmetrical Bento** — masonry CSS Grid of varying card sizes (`col-span-8 row-span-2` next to stacked `col-span-4`). Mobile: single column, all `col-span` reset to 1, generous `gap-6`.
2. **Z-Axis Cascade** — elements stacked like physical cards, slightly overlapping with `−2deg` or `3deg` rotation. Mobile: remove all rotations and negative-margin overlaps below 768px — they cause touch-target conflicts.
3. **Editorial Split** — massive typography on left (`w-1/2`), interactive content on right. Mobile: full-width vertical stack (`w-full`), typography block on top.

**Universal mobile override:** Any asymmetric layout above `md:` MUST collapse to `w-full`, `px-4`, `py-8` below 768px. Never `h-screen` — always `min-h-[100dvh]` (iOS Safari viewport jump fix).

---

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

- Section padding varies — minimum `py-20`, range `py-20` to `py-40`. Use at least 3 different values across a landing page. Same `py-N` on every section is monotony, not rhythm.
- Eyebrow tags before major H1/H2: `rounded-full px-3 py-1 text-[10px] uppercase tracking-[0.2em] font-medium`. **Maximum 3 per page.** Reserve for hero, primary feature section, and social proof. An eyebrow above every heading destroys the emphasis of each one.
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

## Study Mode

**Trigger:** "analizza questo sito", "analiza este sitio", "estrai il DNA di design", "voglio replicare questo stile", "cosa usa questo design", "study this"

Analyze an admired design (URL or screenshot) and extract a portable design brief. Output is a structured summary ready to pass to the next Build session as a reference.

### Study Protocol

1. **Observe the physical scene** — who uses this, where, when, in what mood. Write one sentence.
2. **Identify the register** — Brand / Product / Hybrid? Which zones?
3. **Name the vibe archetype** — which of the A archetypes does this most closely match, or is it a hybrid/unnamed direction?
4. **Identify the color strategy** — Restrained / Committed / Full palette / Drenched? Dominant hue in OKLCH terms if determinable.
5. **Identify the layout archetype** — Asymmetrical Bento / Z-Axis Cascade / Editorial Split / other (describe)?
6. **Extract typography** — heading font, body font, scale impression (tight/loose/dramatic), weight contrast used.
7. **Read the motion register** — fast/slow, which easing family, scroll-driven or triggered, micro-interactions present?
8. **Spot default-refuse patterns** — list any from the refuse list that appear. Note whether they're used structurally or decoratively.
9. **Run slop tests** — is this first-order predictable? Second-order? What makes it escape prediction?
10. **List 3 elements to replicate** — specific and implementable: a spacing decision, a color relationship, a motion choice.
11. **List 2 elements to avoid** — things specific to this brand/budget/context that shouldn't be copied verbatim.

### Study Output Format

```markdown
## Design DNA — [site name or URL]

**Scene:** [one sentence]
**Register:** [Brand / Product / Hybrid]
**Vibe Archetype:** [name or closest match]
**Layout Archetype:** [name or closest match]
**Color Strategy:** [Restrained / Committed / Full palette / Drenched]
**Dominant palette:** [approximate OKLCH description]
**Heading font:** [name + weight + style]
**Body font:** [name + size / line-height impression]
**Motion register:** [duration family, easing impression, key animations]

**Refuse patterns present:** [list or "none"]
**Slop test:** [first-order escape / second-order escape / fails at level N]

**Replicate:**
1. [specific element]
2. [specific element]
3. [specific element]

**Avoid:**
1. [specific element]
2. [specific element]
```

---

## Audit Mode

**Trigger:** "audit questo design", "valuta questo UI", "audita este diseño", "cosa non va", "score questo", "review this code design-wise"

Score existing code or a screenshot against design patterns. **No edits made in Audit mode** — output is analysis only. For UX/accessibility audit use `/ui-ux-libera` instead; this mode covers visual design only.

### Audit Protocol

1. **Identify register** — Brand / Product / Hybrid? Does the implementation match the content's actual register?
2. **Color audit** — strategy used (stated or implied)? OKLCH or raw hex? Pure black/white present? Neutral tinting?
3. **Typography audit** — reflex-reject fonts present? Scale ratio? Line length controlled? Heading/body contrast adequate?
4. **Layout audit** — archetype identifiable? Cards overused? Spacing monotonous (same `py-N` everywhere)? Container overuse?
5. **Motion audit** — CSS layout properties animated? Custom cubic-bezier or default `ease/linear`? `prefers-reduced-motion` handled?
6. **Default-refuse check** — which patterns from the refuse list are present? Structural justification documented?
7. **Slop test** — first-order predictable? Second-order? What level fails?
8. **LIBERA Fingerprint Test** — count stacked defaults.
9. **Overall verdict** — one sentence.

### Audit Output Format

```markdown
## Design Audit — [component / page name]

**Register identified:** [Brand / Product / Hybrid] — [correct match or mismatch]

**Color** [PASS / WARN / FAIL]
[finding]

**Typography** [PASS / WARN / FAIL]
[finding]

**Layout** [PASS / WARN / FAIL]
[finding]

**Motion** [PASS / WARN / FAIL]
[finding]

**Default-refuse violations:** [list or "none"]

**Slop test:**
- First-order: [PASS / FAIL — reason]
- Second-order: [PASS / FAIL — reason]

**LIBERA Fingerprint:** [N/7 defaults stacked — list them]

**Verdict:** [one sentence]

**Top 3 fixes (priority order):**
1. [fix]
2. [fix]
3. [fix]
```

---

## Execution Protocol

1. **[MODE]** Build / Audit / Redesign / Study? If Audit → jump to Audit Mode. If Study → jump to Study Mode. If Redesign → note existing copy/IA before step 2, then proceed.
2. **[REGISTER]** Brand or product? Use the dominant verb. If unclear, use the fallback classification. If hybrid, split by zone.
3. **[CONFLICT CHECK]** If used alongside `/ui-ux-libera`, confirm no conflicts on accessibility, performance, or responsiveness before proceeding.
4. **[SCENE]** Write the physical scene sentence. It must force the dark/light answer.
5. **[STRATEGY]** Choose color strategy explicitly: Restrained / Committed / Full palette / Drenched. Brand rarely defaults to Restrained.
6. **[VARIANCE]** Brand only: pick one Vibe Archetype + one Layout Archetype from the Pattern Catalog.
7. **[FINGERPRINT — pre-build]** Count how many LIBERA defaults the planned design will use. If 3+ are stacked in the plan, redesign the approach before writing any code — return to step 6.
8. **[SLOP TEST]** Run both levels. If predictable at either level, return to step 5.
9. **[COMPOSE]** Brand landing pages only: map every section before writing code. For each section list: name | layout type (card grid / split / bento / list / image+text / full-bleed) | eyebrow? (yes/no). Verify: (a) no two adjacent sections use identical layout; (b) eyebrow count ≤ 3 total; (c) section padding uses at least 3 different `py-N` values across the page. Advance to BUILD only when this map passes.
10. **[BUILD]** Implement. Brand: Double-Bezel, Spatial Rhythm, Motion Choreography. Product: system fonts, predictable grids, Restrained color, familiar patterns, density mode.
11. **[DOCUMENT]** Add a macrostructure comment at the top of the root component documenting the design decisions made.

    ```tsx
    {/* Design: [Register] | Vibe: [Archetype] | Layout: [Archetype] | Color: [Strategy] */}
    ```

    CSS-only projects: `/* Design: [Register] | Vibe: [Archetype] | Layout: [Archetype] | Color: [Strategy] */`
12. **[CHECKLIST]** Final pass before delivering. All applicable gates below must pass.

---

## Pre-Output Checklist

Gate IDs allow citing specific failures in reviews (e.g. "failed G-04 and B-02").

**Both registers**

- `[G-01]` Register identified and confirmed (brand / product / hybrid zones)
- `[G-02]` Physical scene sentence written — it forced the dark/light answer
- `[G-03]` Color strategy chosen explicitly — not defaulted
- `[G-04]` First-order slop check: palette not predictable from category alone
- `[G-05]` Second-order slop check: aesthetic lane not predictable from category + anti-references
- `[G-06]` No default-refuse patterns used without documented structural rationale
- `[G-07]` All transitions use custom cubic-bezier — no `linear` or default `ease`
- `[G-08]` `backdrop-blur` only on fixed/sticky elements
- `[G-09]` Full-height sections: `min-h-[100dvh]`, not `h-screen`
- `[G-10]` Scroll animations use IntersectionObserver, not scroll event listener
- `[G-11]` Motion respects `prefers-reduced-motion`
- `[G-12]` Copy: no em dashes unless brand voice requires them, no restated headings
- `[G-13]` Macrostructure comment added to root component

**Brand only**

- `[B-01]` Font procedure followed — no fonts from reflex-reject list as first choice
- `[B-02]` No aesthetic lanes from reflex-reject lanes
- `[B-03]` Double-Bezel used selectively: primary feature container or hero media only, never on every card (outer = frame, not second content container; see Fingerprint Test)
- `[B-04]` Section padding minimum `py-20` (per Spatial Rhythm), at least 3 different values across the page
- `[B-05]` Motion uses `cubic-bezier(0.32, 0.72, 0, 1)` — no `ease-in-out`
- `[B-06]` LIBERA Fingerprint Test passed — fewer than 3 defaults stacked
- `[B-07]` Overall impression reads as designed with intent, not assembled from templates
- `[B-08]` Eyebrow tags ≤ 3 total across the page
- `[B-09]` No two adjacent sections use identical layout type

**Product only**

- `[P-01]` Density mode chosen (Compact / Comfortable / Spacious) — consistent throughout
- `[P-02]` Component vocabulary consistent across all screens
- `[P-03]` No decorative motion — all motion conveys state
- `[P-04]` Standard navigation patterns used, not reinvented
- `[P-05]` Accent color only on primary actions, selection, state indicators
- `[P-06]` Brand Moments limited to appropriate surfaces (onboarding, empty state, success)

**Hybrid surfaces**

- `[H-01]` Zones explicitly identified (Brand zone / Product zone)
- `[H-02]` Product zones use familiar patterns regardless of Brand framing
- `[H-03]` No Brand expression on repetitive task surfaces

---

## External References

This skill is self-contained for first-pass visual direction. The `reference/` files in [skill-web-design](https://github.com/liberastudio-mx/skill-web-design) are optional deep-dives.

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
| Make a design bolder/louder | `overdrive.md` |
| Simplify without losing meaning | `distill.md` |
| Micro-interactions, delight | `delight.md` |
| Animation direction | `animate.md` |
| Adding strategic color | `colorize.md` |
| Typography improvement pass | `typeset.md` |
| Heuristic UX scoring | `heuristics-scoring.md` |
| Design critique methodology | `critique.md` |
| First-run flows, activation | `onboard.md` |
| Device/screen adaptation | `adapt.md` |
| Copy clarity | `clarify.md` |
| Errors, i18n, edge cases | `harden.md` |
| A11y/perf/responsive audit | `audit.md` |
| UI performance fixes | `optimize.md` |
| Persona frameworks | `personas.md` |

---

*LIBERA Studio synthesis — maggio 2026*
*Fonti: impeccable (Apache 2.0) + high-end-visual-design*
*Repository: https://github.com/liberastudio-mx/skill-web-design*
