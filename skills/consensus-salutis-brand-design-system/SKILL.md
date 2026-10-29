---
name: consensus-salutis-brand-design-system
description: >
  Brand design system for BinPar, the institutional medical AI platform (formerly Consensus
  Salutis): color tokens, typography, the hexagonal BinPar logo and favicon, light/dark theming,
  UI component specs, motion (signal field, brand-mark reveal and loader, section index) and
  landing/blog page patterns. Use when creating, reviewing, or modifying any visual design, UI,
  marketing material, presentation, email, social media asset, or web/app interface for the
  BinPar clinical AI product (website, clinical chat, back office), or when generating CSS,
  design tokens, or component configurations for it. Not for unrelated BinPar company work
  outside this product.
---

> **Deprecated:** superseded by `binpar-brand-design-system` in BinPar/skills (identity manual v1.0). Prefer it; this copy is no longer maintained.

# BinPar Brand Design System

## Brand Identity Overview

**BinPar — institutional medical AI** (formerly Consensus Salutis). A platform
that turns clinical guidelines, protocols and medical corpus into traceable,
auditable answers for healthcare professionals, built on three pillars:
BinPar (product and engineering), Editorial Médica Panamericana (clinical
knowledge) and AWS (resilient infrastructure). The brand voice is serious,
institutional and evidence-driven; the visual language is **calm ice-blue
light mode / deep-navy dark mode**, with a teal→turquoise accent, geometric
type, glass cards, slow organic "signal" motion, a brand mark that traces
itself in, and rare navy contrast bands.

The mark is a single rounded, pointy-top hexagon pierced by two identical
hook-shaped channels, 180° point-symmetric — two interlocking halves. The
lockup sets the wordmark "BinPar" (mixed case, one tone) to its right. No
container. There is no BinPar brand manual yet: don't invent a philosophy
for the mark (see `references/logo-usage.md`).

> Sources of truth: the production implementation in
> **consensus-salutis-website** (HEAD `70613ae`: `src/styles/globals.css`,
> `src/app/layout.tsx`, `src/app/_components/`, `public/logos/binpar-brand/`)
> and, for the base palette and Plus Jakarta Sans only, the Consensus
> Salutis-era brand manual PDF. Code wins; logo rules come from the
> `binpar-brand` SVGs and their usage in code. **The definitive home layout is
> the VERTICAL one** (`VerticalHome`, opened by `HomeCover`) — the horizontal
> rail is legacy.

### Naming

- The brand string is exactly **"BinPar"** (capital B and P, one word). Never
  "Binpar", "BINPAR" in source text, "Bin Par", "binPar", or the legacy
  "Consensus Salutis" / "Consensus" / "CS" in user-visible copy (sole
  exception: one "BinPar (antes Consensus Salutis)" note at first mention,
  where readers know the old name). Eyebrows may render it uppercase via CSS
  only. Legal entity: BinPar Team S.L. Wording and copy rules:
  `consensus-salutis-brand-voice` (sister skill).
- Brand + qualifier: `" · "` ("BinPar · Lecturas clínicas", "BinPar ·
  Inicio", "BinPar · Nuevo chat", "BinPar · Editor"). Website `<title>`
  template: `"%s | BinPar"`. Product tabs: "BinPar — Chat" (es, en),
  "BinPar — Xat" (ca), "BinPar — Editor".
- Internal identifiers keep the legacy prefix on purpose — never rename them
  for the brand: this skill's ID, `consensus-theme` / `consensus-chat-*`
  storage keys, the `consensus` chat-skin and font keys, `@consensus/*`
  packages, author id `equipo-consensus-salutis`, the `data-consensus-isotype`
  attribute, i18n key names (`consensusName`, `optConsensus`,
  `fontConsensus`), cookies, env var names, R2 hosts/buckets, Clerk metadata
  keys, the `consensussalutis.com` domain and mailboxes.

---

## Quick Reference: Design Tokens

### Colors (core)

```json
{
  "deep-navy":            "#002262",
  "heading-navy":         "#05215e",
  "primary-light":        "#006d79",
  "primary-dark":         "#00BCBB",
  "primary-dark-lighter": "#71fffe",
  "secondary-light":      "#ffd230",
  "secondary-dark":       "#f6ff53",
  "bg-light":             "#f4f9fc",
  "bg-light-home":        "#fbfdff",
  "band-light-deep":      "#deedf3",
  "band-light-panel":     "#e8f2f7",
  "bg-dark":              "#06111f",
  "bg-dark-deep":         "#030916",
  "band-dark-panel":      "#081827",
  "card-dark":            "#152230e6",
  "contrast-band":        "#081827",
  "text-muted-dark":      "#a9bacb"
}
```

`primary-light`/`secondary-light` = accent **when the light theme is active**
(teal `#006d79` / warm yellow `#ffd230`); `primary-dark`/`secondary-dark` = the
dark-theme counterparts (turquoise `#00BCBB` / lime `#f6ff53`). Text and borders
lean on Tailwind `slate` + translucent `cyan`. The rebrand did NOT change the
tokens; the logo files carry their own fills (`#006f7b`, `#00bebc`, `#002366`)
that never become UI colors.

### Typography Hierarchy

| Level | Font | Classes |
|-------|------|---------|
| Eyebrow | Sora | `font-display text-xs font-bold tracking-[0.22em] uppercase` in accent |
| Cover H1 | Sora | 54/48/36px extrabold, `line-height 1.12` + 40px accent line |
| H1 / display | Sora | `font-display text-4xl–6xl font-extrabold tracking-tight text-[#05215e] dark:text-slate-50`; two-line variant with accent 2nd line |
| H2 section | Sora | `font-display text-3xl–5xl font-extrabold tracking-tight` |
| Card title | Sora | `font-display text-base–lg font-semibold` |
| Lede | Plus Jakarta Sans | `font-body text-lg leading-8 text-slate-600 dark:text-slate-400` |
| Body / card | Plus Jakarta Sans | `font-body text-sm–base leading-6–7` |
| Micro-label | PJS / Sora | `text-[10px]–xs font-semibold tracking-[0.12–0.22em] uppercase` in accent |

Fonts load via `next/font/google` (`--font-sora`, `--font-plus-jakarta-sans`);
`font-sans` defaults to Plus Jakarta Sans. The BinPar wordmark is outlined
paths, not a font — never typeset it.

### Surfaces, Radius & Motion

- Cards: `rounded-2xl` glass (`bg-white/80 backdrop-blur-xs shadow-big-blocks` /
  dark `bg-[#152230e6]/90` + cyan glow); stage frames and deep panels
  `rounded-3xl`; pills/CTAs `rounded-full`; fields `rounded-lg`.
- Borders: translucent cyan (`border-cyan-800/10–25` light,
  `border-cyan-300/10–25` dark) — never opaque gray.
- Contrast band: `radial-gradient(ellipse at 90% 90%, rgb(0 109 121 / 22%),
  transparent 60%), #081827`, identical in both themes (volume band, footer).
- Motion: background blobs morph 10–32s linear; content fades 0.18–0.9s
  ease-out; brand-mark trace ~1.2s, loader 2s loop; looping scenes pause
  off-screen and in hidden tabs; hovers lift (`-translate-y-0.5/-2`, 150ms).
  Everything honors `prefers-reduced-motion`.

---

## Workflow: Applying the Brand

### By task type:

**Web UI / App Interface**
1. Set up theme tokens + `dark` class switching → `references/colors-and-tokens.md`, `references/light-dark-mode.md`
2. Configure Sora + Plus Jakarta Sans via next/font → `references/typography.md`
3. Add background layers (grid + SignalField) → `references/motion-system.md`
4. Build with the button/card/form recipes; long pages get the section index (`SectionNavigation`) → `references/ui-components.md`
5. Place theme-paired logos and the versioned favicon → `references/logo-usage.md`
6. Loading and intro states: brand-mark loader / reveal → `references/motion-system.md` (Brand mark motion)

**Landing / Marketing Page**
1. Follow the vertical home structure (cover → presentación + chat mock →
   casos (map) → proceso (player) → arquitectura (strata) → volumen (contrast
   band) → blog → contacto (assistant)) → `references/landing-patterns.md`
2. Wrap sections in `HomePaintPanel`, register them in the section index;
   masked-blend surfaces with one navy contrast band; reveal cadence
   0 / 0.1 / 0.2 / 0.3 → `references/motion-system.md`
3. CTAs: teal primary + ghost pair in-page; one exploratory CTA on the cover;
   yellow pill as the contrast CTA (header on the website — elsewhere, the
   one element that must pop)

**Blog / Content**
1. Content engine (MDX + Zod frontmatter), cards, index, tags, covers, OG
   image and feeds → `references/blog-patterns.md`
2. MDX body typography recipe → `references/typography.md`

**Marketing Asset (Social, Banner, Presentation)**
1. Pick a theme: ice-light (`#f4f9fc` bg, navy headings, teal accent) or
   deep-navy dark (`#06111f`, white headings, turquoise accent)
2. Logo variant must match the background; native 3.26:1 proportions →
   `references/logo-usage.md`
3. Headlines in Sora ExtraBold; one accent story: teal/turquoise, with yellow
   as the contrast highlight where emphasis is needed
4. Optional texture: the 44px grid + an organic blob shape at low alpha

**Design Token / CSS Generation**
1. Output the `@theme` block from `references/colors-and-tokens.md` verbatim
   (Tailwind v4 + `@custom-variant dark`)
2. Include `.font-body`/`.font-display` utilities and `--shadow-big-blocks`
3. Include the theme-boot script + `theme-changing` CSS from
   `references/light-dark-mode.md`

**Brand Compliance Review**
1. Run the checklist below
2. Cross-reference each area against its reference file

---

## Core Rules Summary

### Color
- One accent story: teal `#006d79` (light) / turquoise `#00BCBB` (dark) for
  links, eyebrows, numbers, fills, focus. Hover shifts: `cyan-800` / `#71fffe`.
- Yellow (`#ffd230` light / `#f6ff53` dark) is the **contrast color**: use it
  for the few elements that must stand out against the teal story (key CTAs,
  highlights, attention states, badges). On the website it appears in the
  header CTA and the evidence highlight wash, but it is not limited to that —
  just keep it scarce so it keeps reading as contrast; never body text,
  borders, or large fills.
- Text on turquoise/yellow fills is near-black navy (`#03111d`–`#06111f`);
  white text only on light-mode teal `#006d79`.
- Headings `#05215e` (web). Logo SVGs carry their own fills (`#002366`,
  `#006f7b`, `#00bebc`): never recolor them, never adopt them as UI colors.
- Borders are translucent cyan; surfaces are translucent white/navy glass.
- Only rose (errors) and teal (status) beyond the brand hues; never new colors.

### Typography
- Sora extrabold for headings/eyebrows/numbers; Plus Jakarta Sans for
  everything else. Never Sora for paragraphs.
- Eyebrows/micro-labels: UPPERCASE, wide tracking, accent color. Buttons:
  sentence case, `font-semibold text-sm`.
- Copy is Spanish, institutional and sober ("trazable", "evidencia", "fuentes
  verificables") — no hype. Wording rules: `consensus-salutis-brand-voice`.

### Logo
- `binpar-logo-light.svg` (navy `#002366` wordmark + teal `#006f7b` mark) on
  light; `binpar-logo-dark.svg` (white + `#00bebc`) on dark; isotipo alone for
  small/square slots (portrait 0.924:1 → `object-contain` in square boxes).
- Render both variants with `dark:hidden` / `hidden dark:block` — never a
  single fixed file in themed UI. Exception: the always-dark contrast band
  (footer, volume) shows only the `-dark` file in both themes.
- Never distort, partially recolor, restyle, or retype the wordmark.
  Animated/inline marks reuse the canonical outline with `currentColor`.
- Partner logos in dark mode: `dark:brightness-0 dark:invert` or a dedicated
  white variant.

### Theming
- Both themes always; light default; `dark` class on `<html>` +
  `consensus-theme` localStorage (legacy key kept on purpose; renaming it
  resets users' preference) + no-flash boot script + 180ms `theme-changing`
  transition.
- Every component ships paired `x dark:y` classes from day one. The only
  theme-fixed surfaces are the navy contrast bands.

### Surfaces & Motion
- Glass cards over a 44px grid background with SignalField blobs behind
  (`[clip-path:inset(0)]` + fixed layer trick); light sections blend through
  masks, not hard band edges.
- Contrast bands (`#081827` + teal radial) are intentionally theme-fixed. The
  volume band carries `data-section-navigation-surface="dark"`
  (`volume-section.tsx:84-86`); the footer does not. Mark any new contrast
  band the section index can overlap.
- Background morphs slow/linear; content reveals are opacity-only fades with
  0.1s stagger steps; hovers lift. The brand mark animates only via the
  canonical reveal (one-shot) or loader (looping) and never changes shape.
- Looping scenes run only when painted, in view and the tab is visible.
  `prefers-reduced-motion` renders final states — no exceptions.
- Decorative layers: `aria-hidden`, `pointer-events-none`, `z-0`; content `z-10`.

---

## Light/Dark Quick Reference

| Element | Light | Dark |
|---------|-------|------|
| Page bg | `#f4f9fc` / home `#fbfdff` | `#06111f` |
| Bands | `#deedf3` · `#e8f2f7` | `#030916` · `#081827` |
| Contrast band (volume, footer) | `#081827` + teal radial | same (theme-fixed) |
| Card | `bg-white/80` + `shadow-big-blocks` | `bg-[#152230e6]/90` + cyan glow |
| Heading | `#05215e` | `slate-50` / `#f8fafc` |
| Body | `slate-600/700` | `slate-400/300`; custom CSS `#a9bacb` |
| Border | `cyan-800/10–25` | `cyan-300/10–25` |
| Accent | `#006d79` | `#00BCBB` (hover `#71fffe`) |
| Primary btn text | white | `#03111d` |
| Yellow contrast accent | `#ffd230` + `#06111f` text | `#f6ff53` + `#06111f` text |
| Logo | `binpar-logo-light.svg` | `binpar-logo-dark.svg` |

→ Full details in `references/light-dark-mode.md`

---

## Asset Inventory

### Logos (4 files)
```
assets/logos/
  binpar-logo-light.svg      # lockup, light bg: mark #006f7b + wordmark #002366, 430.04×131.79 (3.263:1)
  binpar-logo-dark.svg       # lockup, dark bg: mark #00bebc + wordmark #fff, 430.04×131.79
  binpar-isotipo-light.svg   # mark alone, #006f7b, 121.76×131.79 (0.924:1, portrait)
  binpar-isotipo-dark.svg    # mark alone, #00bebc, 121.76×131.79
```
Byte copies of the website's `public/logos/binpar-brand/`. The retired
`consensus-*` files are gone; never use them.

### Favicon (2 files)
```
assets/favicon/favicon.svg   # bare #00bebc isotipo on transparent, no tile (= binpar-isotipo-dark.svg) — sizes="any"
assets/favicon/favicon.ico   # real ICO, PNG frames 16/32/48/64 px (4693 B)
```
These are the canonical favicon assets. **Always use these exact files** for
any BinPar web property, referenced with a cache-busting
`?v=<first 12 hex of sha256>`: `favicon.svg?v=3f2ea0207fce`,
`favicon.ico?v=5c39334f2516`. Recompute when a file changes
(`references/logo-usage.md`).

### Fonts
No binaries needed: **Sora** and **Plus Jakarta Sans** load via
`next/font/google` (both SIL OFL). See `references/typography.md`.

---

## Brand Compliance Checklist

When reviewing or producing any BinPar artifact, verify:

- [ ] **Name**: "BinPar" exactly in visible copy, alt and aria (never "Consensus Salutis", "Binpar", "BINPAR" in source, beyond one "antes Consensus Salutis" note)? Internal legacy identifiers left untouched?
- [ ] **Themes**: both light and dark styled? `dark:` pairs on every colored class?
- [ ] **Accent discipline**: teal/turquoise as the primary accent? Yellow used sparingly as contrast (high-emphasis elements only)?
- [ ] **Text on fills**: near-black navy on turquoise/yellow — never white in dark mode?
- [ ] **Headings**: Sora `font-extrabold tracking-tight` in `#05215e`/`slate-50`?
- [ ] **Eyebrow present** above every H1/H2 (except the cover and centered two-line accent display headings: `/plataforma` H1, strata H2), uppercase, `tracking-[0.22em]`, accent color?
- [ ] **Body**: Plus Jakarta Sans, `slate-600/700` (light) / `slate-300/400` (dark)?
- [ ] **Borders**: translucent cyan (not gray)? Radius scale (full/3xl/2xl/xl/lg/md)?
- [ ] **Cards**: glass fill + `backdrop-blur` + `shadow-big-blocks` (light) / cyan glow (dark)?
- [ ] **Logo**: `binpar-*` files only? Correct variant per theme, both rendered with `dark:hidden`/`dark:block` (or `-dark` alone on a contrast band)? Proportions intact (3.26:1 lockup, portrait isotipo with `object-contain`)?
- [ ] **Partner logos**: inverted or white-variant in dark mode?
- [ ] **Motion**: background linear+slow, foreground fade-only, staggered in reading order?
- [ ] **Brand mark motion**: only the canonical reveal/loader, `currentColor`, silhouette unchanged?
- [ ] **Reduced motion & gating**: final states rendered; loops and scenes paused off-screen and in hidden tabs?
- [ ] **Icons**: lucide, `strokeWidth 1.8` (documented exceptions only), `aria-hidden`?
- [ ] **Landing**: vertical home structure opened by the brand cover, sections registered in the section index? (NOT the horizontal rail)
- [ ] **Copy**: Spanish, institutional, evidence-led? CTAs sentence case? Wording checked against `consensus-salutis-brand-voice` (no trailing periods in headings, no *agente*/*orquestador*; *comité clínico* allowed)?
- [ ] **Favicon**: canonical `favicon.svg` (+ `.ico`) with `sizes="any"` and a `?v=` hash matching the file?

---

## Reference Files Index

| File | Topic | Read when... |
|------|-------|-------------|
| `references/colors-and-tokens.md` | Full palette, `@theme` block, semantic maps, contrast band, logo-file colors, shadows, radius | Setting up colors, generating tokens |
| `references/typography.md` | Sora/PJS setup, hierarchy (cover, two-line display, stage titles), rules, MDX article recipe | Configuring or reviewing text styling |
| `references/logo-usage.md` | BinPar mark and lockup geometry, files, theming, production sizes, app-icon tile, favicon + cache-bust, partner logos | Placing logos, choosing versions |
| `references/light-dark-mode.md` | Theme architecture, toggle, boot script, token mapping, theme-fixed contrast bands | Implementing theming |
| `references/ui-components.md` | Buttons (incl. cover CTA), cards, header, contrast footer, section index, contact assistant, forms, chat mock, process player | Building UI components |
| `references/motion-system.md` | Registers, grid + SignalField, **brand mark reveal + loader**, brand-intro choreography, typed reply, thinking indicator, beacon, scenes, paint panels, durations, gating; legacy counters | Adding motion, loaders, page shells |
| `references/landing-patterns.md` | Vertical home (cover → … → contact assistant), panels, masked surfaces, content blocks, subpages, deleted routes | Building landing/marketing pages |
| `references/blog-patterns.md` | MDX content engine, covers, OG image, cards, index, tags, feeds | Building blog/content surfaces |

---

## Examples

### Example 1: New section on the landing

**Request**: "Add a security section to the BinPar home"

**Expected behavior**: A `HomePaintPanel` section in the vertical flow,
wrapped as `section-navigation-region` with an `id` + `tabIndex={-1}` and
added to the `homeSections` index with a short noun label ("Seguridad").
Surface masked to blend with its neighbors (no hard band edge; at most the
existing navy contrast band nearby). `max-w-7xl` container, Eyebrow
("Seguridad") → Sora H2 `text-5xl font-extrabold text-[#05215e]
dark:text-slate-50` → lede → glass cards (`rounded-2xl border-cyan-800/15
bg-white/80 shadow-big-blocks` + dark glow). Reveals: 0/0.1/0.2/0.3
opacity cadence, reduced-motion safe.

### Example 2: CSS tokens

**Request**: "Generate the CSS variables for BinPar"

**Expected behavior**: Output the Tailwind v4 `@theme` block from
`references/colors-and-tokens.md` verbatim (`--color-primary-*`,
`--color-secondary-*`, fonts, `--shadow-big-blocks`, `--breakpoint-3xl`) plus
`@custom-variant dark`, the `.font-body`/`.font-display` utilities, and the
theme-boot script + `theme-changing` transition CSS. No logo-file hex.

### Example 3: Social media banner

**Request**: "Design a LinkedIn banner for BinPar"

**Expected behavior**: Deep navy `#06111f` (or ice `#f4f9fc`) background with
the subtle 44px grid and one low-alpha organic blob (turquoise→teal gradient).
`binpar-logo-dark.svg` (or `-light`) at native 3.26:1 proportions. Headline in
Sora ExtraBold, white (or `#05215e`), with one key phrase in the accent — or
in yellow if it needs maximum contrast. Institutional Spanish copy.

### Example 4: Dashboard in the platform

**Request**: "Create a metrics dashboard screen"

**Expected behavior**: Body `bg-[#f4f9fc] dark:bg-[#06111f]` + grid background.
Metric cards per `ui-components.md` (glass, `rounded-2xl`, `font-display`
values in `text-cyan-800 dark:text-primary-dark-lighter`; static values —
count-ups are legacy). Eyebrow + H2 header block. Pending data shows the
brand-mark loader at 20–24px in the accent. Fixed header with theme toggle and
yellow CTA. Forms/fields with the teal focus ring recipe.

### Example 5: Chat loading and empty state

**Request**: "Replace the old loader and intro animation in the chat"

**Expected behavior**: Port the canonical recipes from
`references/motion-system.md` → Brand mark motion: `BINPAR_ISOTYPE_OUTLINE` +
three contours, viewBox `0 0 121.76 131.79`. Empty state: the one-shot reveal
(1.2s trace, fill at 850ms), copy at ≈0.8s, composer at ≈1.3s. Pending
states: the looping loader (stroke 9, 2s, `currentColor`, no ids); keep the
product's existing `data-consensus-isotype` attribute on the loader root. Both
reduced-motion safe; organization skins keep their own assets.

---

## Source Traceability

Website paths at `consensus-salutis-website` HEAD `70613ae`.

| Skill section | Source |
|---------------|--------|
| Base palette, Plus Jakarta Sans | Brand manual PDF (Consensus Salutis era, "Aspectos técnicos") + `src/styles/globals.css` |
| Logo geometry, files, favicon | `public/logos/binpar-brand/`, `public/favicon.svg`, `public/favicon.ico`, `src/app/layout.tsx` (icons), `brand-isotype-reveal.tsx` |
| Theme tokens, fonts, shadows | `src/styles/globals.css`, `src/app/layout.tsx` |
| Theme switching | `layout.tsx` boot script, `theme-toggle.tsx`, `globals.css` |
| Contrast band, footer | `contrast-footer.tsx`, `footer-design.css`, `site-footer.tsx` (`VerticalFooter`), `volume-section.tsx` + `.css` |
| Buttons, cards, shells, header | `site.tsx`, `site-header.tsx`, `scroll-header-frame.tsx`, `mobile-navigation.tsx` |
| Cover, brand-mark motion | `home-cover.tsx` + `.css`, `brand-isotype-reveal.tsx`, `brand-isotype-particles.tsx` |
| Motion system | `motion-system.tsx` (incl. `HomeGrid`), `product-signal-left.tsx`, `home-paint-panel.tsx` |
| Section index | `section-navigation.tsx` + `.css`, `side-linkedin-link.tsx` |
| Landing patterns | `horizontal-home.tsx` (`VerticalHome` = canonical, `HeroPanel`, `MobileHome`), `page.tsx`, `src/env.js` |
| Casos, proceso, arquitectura | `success-cases/*`, `clinical-process-{showcase,player,visuals,typing,data}.ts(x)`, `clinical-{committee,evidence,followup}-scene.tsx`, `product-strata/*` |
| Chat mock | `clinical-chat-mock.tsx` |
| Contact | `contact-assistant/*`, `contacto/_components/*` (legacy form: `contact-form.tsx`) |
| Subpages | `platform-walkthrough.tsx`, `platform-preview/*`, `src/app/plataforma/page.tsx`, `src/app/contacto/page.tsx` |
| Blog | `src/lib/blog.ts`, `src/content/blog/`, `blog/page.tsx`, `blog/[slug]/page.tsx`, `blog/[slug]/opengraph-image.tsx`, `blog/tag/[tag]/page.tsx`, `blog/rss.xml/route.ts`, `blog-index.tsx`, `blog-article-card.tsx`, `blog-cover.tsx`, `home-blog.css` |
| Brand-mark loader | Derived (no website equivalent): reveal geometry + the product's 2s loader cadence |
