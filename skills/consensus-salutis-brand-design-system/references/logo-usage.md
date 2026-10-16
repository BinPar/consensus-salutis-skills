# Logo Usage

> Sources: `public/logos/binpar-brand/*.svg`, `public/favicon.svg`,
> `public/favicon.ico`, `src/app/layout.tsx` (icons), and production usage in
> `site-header.tsx`, `contrast-footer.tsx` + `footer-design.css`,
> `home-cover.tsx` + `home-cover.css`, `brand-isotype-reveal.tsx`,
> `clinical-chat-mock.tsx`, `clinical-process-visuals.tsx` (`Mark`),
> `contact-assistant/contact-assistant.css`, `contacto/_components/office-map.*`,
> `platform-preview/*` (website HEAD `70613ae`).

The product is **BinPar** (formerly Consensus Salutis; renamed in website
`05d5437`, 2026-10-06). The old C+S square mark, the "CONSENSUS SALUTIS"
wordmark and its brand-manual philosophy are retired. There is no BinPar brand
manual in any repo yet: everything below is read from the artwork and the code.
Don't write a "philosophy" or construction story for the new mark until a
BinPar brand source provides one.

## The mark (isotipo)

- One solid **rounded, pointy-top hexagon**: vertices at top and bottom, flat
  vertical sides, corner radius ≈11 units. No container, no tile, no square.
- Pierced by **two identical hook-shaped negative channels**, 180°
  point-symmetric about the center (≈60.9, 65.9): two interlocking halves.
  Each channel band is ≈14.6 units wide (≈11% of the mark height); the solid
  rim left around them is ≈9.6 units.
- One path, three contours: outer hexagon (`M119.3,45.22…`), upper-left
  channel (`M32.72,42.72…`), lower-right channel (`M89.04,89.08…`). The
  channels wind opposite to the hexagon, so the default nonzero fill rule cuts
  them out. viewBox `0 0 121.76 131.79` → ratio **0.924:1, portrait**, not
  square.
- The code invariant: "Canonical BinPar silhouette; animation reveals it
  without changing its shape." (`brand-isotype-reveal.tsx:1`). The exported
  `binparIsotypeOutline` string is byte-identical to the `d` of
  `binpar-isotipo-*.svg`; animated and inline marks reuse it, never a redraw
  (see `motion-system.md` → Brand mark motion).

## The lockup (logo)

- Mark + wordmark **"BinPar"**: mixed case (capital B and P), one tone, set to
  the right of the mark and optically centered on it. Outlined geometric bold
  sans (square tittle on the `i`, double-storey `a`; face unverified) — it is
  paths, not a font: never retype it in Sora or Plus Jakarta Sans.
- viewBox `0 0 430.04 131.79` → ratio **3.263:1**. Wordmark cap height ≈47% of
  the mark height; mark → "B" gap 45.37 units (≈0.34× the mark height). The
  old 7.03:1 lockup is gone: at equal height the new one is ≈54% narrower.

| Height | Lockup width | Isotipo width |
|--------|--------------|---------------|
| 16px | 52.2px | 14.8px |
| 24px | 78.3px | 22.2px |
| 32px | 104.4px | 29.6px |
| 48px | 156.6px | 44.3px |
| 64px | 208.8px | 59.1px |

## Asset inventory (`assets/logos/`)

Byte copies of the website's `public/logos/binpar-brand/` (Illustrator
exports, viewBox only, no width/height attributes).

| File | Fills | viewBox | Use on |
|------|-------|---------|--------|
| `binpar-logo-light.svg` | mark `#006f7b`, wordmark `#002366` | 430.04×131.79 | Light backgrounds |
| `binpar-logo-dark.svg` | mark `#00bebc`, wordmark `#fff` | 430.04×131.79 | Dark backgrounds + always-dark bands |
| `binpar-isotipo-light.svg` | `#006f7b` | 121.76×131.79 | Light bg, small/square slots |
| `binpar-isotipo-dark.svg` | `#00bebc` | 121.76×131.79 | Dark bg, small/square slots |

**File colors ≠ UI tokens.** The SVG fills drift 1–2 units from the tokens
(`#006f7b` vs `#006d79`, `#00bebc` vs `#00BCBB`, `#002366` vs `#002262` /
heading `#05215e`). This drift lives ONLY inside the files: never "fix" the
SVGs and never adopt the drift as UI colors. Inline or animated marks use
`currentColor` driven by the tokens (`text-primary-light
dark:text-primary-dark`), never a hard-coded hex. (The website's cover
animation hard-codes `#006f7b` / `#00bcbb`; the product and new work follow
the token rule.)

## Theme-paired rendering (canonical pattern)

Always render BOTH files and let the `dark` class on `<html>` switch them
(`site-header.tsx:33-48`):

```tsx
<Image src="/logos/binpar-brand/binpar-logo-light.svg" alt="" width={430.04}
  height={131.79} priority className="h-6 w-auto sm:h-8 dark:hidden" />
<Image src="/logos/binpar-brand/binpar-logo-dark.svg" alt="" width={430.04}
  height={131.79} priority className="hidden h-6 w-auto sm:h-8 dark:block" />
```

- Size by **height** + `w-auto`; pass the real viewBox as `width`/`height`
  (`430.04×131.79`, `121.76×131.79`) so the intrinsic ratio is right.
- Portrait isotipo in a square slot (`size-6`, `24×24`, `64×64`): add
  **`object-contain`** (website `05d5437` added it everywhere). SVG `meet`
  never distorts, but the mark renders ≈7.6% narrower than the box and
  centered — expected.
- `alt`: decorative copies get `alt=""` inside a labeled link
  (`aria-label="Inicio"` header, `aria-label="BinPar · Inicio"` footer);
  standalone logos get `alt="BinPar"`.
- **Always-dark band exception**: on the navy contrast band (`#081827`,
  identical in both themes) render ONLY `binpar-logo-dark.svg`, unpaired
  (`ContrastFooter` → `Brand white`, `contrast-footer.tsx:12-33`).
- **Self-themed replica exception**: a component with its own theme state
  (the `/plataforma` product replica, `data-theme`) picks one file from that
  state (`preview-ui.tsx` `PreviewLogo`) instead of the `dark:` pair.

## Sizes in production

| Placement | Variant | Size | Source |
|-----------|---------|------|--------|
| Site header | logo pair | `h-6 sm:h-8` (24/32px → ≈78/104px wide) | `site-header.tsx:33-48` |
| Contrast footer | `binpar-logo-dark` only | `.ft-brand img { height: 26px }`; 24px ≤767px | `footer-design.css:31-34,289-291` |
| Home cover | isotipo in app-icon tile | tile 96×96, radius 28px; mark 56px wide (76×76, r23, 44px ≤767px) | `home-cover.css:70-120` |
| Contact assistant | animated isotipo | 56px tall in a 56×56 box | `contact-assistant.css` `.ca-brand` |
| Chat mock empty state | isotipo | `size-10` above eyebrow "BinPar" + "Comité clínico" | `clinical-chat-mock.tsx` |
| Chat mock processing line | isotipo | `size-4` | `clinical-chat-mock.tsx` |
| Process scenes | isotipo (`Mark`) | welcome `size-12`; app-header lockup `size-6` + "BinPar" in Sora `text-sm font-semibold`; status `size-5` | `clinical-process-showcase.tsx`, `clinical-process-visuals.tsx` |
| Architecture pillar | logo pair | `h-7` (large `h-10`) | `product-strata/product-strata-scene.tsx` |
| Evaluador interview | logo pair; avatars isotipo | `h-5`; `size-6 object-contain` | `interview/interview-screen.tsx` |
| Office map marker | isotipo | 24×26 inside a 46px circle badge + label "BinPar" | `contacto/_components/office-map.css` |

**Product chat mirror** (`/plataforma` replica of `apps/chat`,
`platform-preview.css`) — the reference for the product apps:

| Slot | Variant | Size |
|------|---------|------|
| Sidebar header | lockup | **24px** high (`.pp-logo`), inside the "BinPar · Nuevo chat" button; header 48px tall |
| Collapsed rail | isotipo | 24×24 `object-fit: contain` |
| Mobile header | isotipo | 24px + page title |
| Empty-chat welcome | isotipo | **64×64**, then org eyebrow (Sora 10px 700 `0.22em` uppercase accent) and h2 24px 800 |

**Minimum sizes** (derived from production, no source defines them): lockup
24px tall by default, 20px only in dense chrome (interview `h-5`); isotipo
16px (`size-4`); below that use the favicon. **Clearspace**: no source defines
one — don't invent a rule.

## App-icon tile

The only "container" the mark gets, on intro/cover moments. Box: 96×96,
`border-radius: 28px`; ≤767px 76×76, 23px (`home-cover.css:70-75,111-116`).

**Production: animated tile.** Every call site at HEAD (`HomeCover` and the
lab) passes `animateEntrance`, so the cover carries `data-entry-study="true"`.
That mode strips the element's background, border color and shadow and paints
the surface on `::before`, so it can fade on its own (`home-cover.css:128-155`).
Port this version:

```css
/* element */
position: relative; isolation: isolate;
background: none; border-color: transparent; box-shadow: none;
/* ::before, light */
content: ""; position: absolute; inset: -1px; z-index: -1;
border-radius: inherit;
border: 1px solid rgba(5, 33, 94, 0.08);
background: #fff;
box-shadow: 0 2px 3px rgba(5, 33, 94, 0.08), 0 12px 28px rgba(5, 33, 94, 0.07);
/* ::before, dark */
background: #102535;
border-color: rgba(125, 211, 252, 0.16);
box-shadow: 0 2px 3px rgba(0, 0, 0, 0.2), 0 12px 28px rgba(0, 0, 0, 0.15);
```

The fill is flat and has no inset highlight. Entrance timing is in
`motion-system.md` → Brand-intro choreography.

**Static variant (unused at HEAD).** The non-animated branch
(`home-cover.css:70-95`, the `<img>` isotipo on a gradient) is not rendered
by any page. It is listed for reference only; don't port it:

```css
/* light */
border: 1px solid rgba(5, 33, 94, 0.08);
background: linear-gradient(145deg, #fff, #f6fafc);
box-shadow: 0 2px 3px rgba(5, 33, 94, 0.08), 0 12px 28px rgba(5, 33, 94, 0.07),
  inset 0 1px 0 #fff;
/* dark */
border-color: rgba(125, 211, 252, 0.16);
background: linear-gradient(145deg, #172c3d, #0c1c2b);
box-shadow: 0 2px 3px rgba(0, 0, 0, 0.2), 0 12px 28px rgba(0, 0, 0, 0.15),
  inset 0 1px 0 rgba(255, 255, 255, 0.06);
```

The mark takes ≈58% of the tile width (56/96; mobile 44/76). The tile is white
or deep navy, never a teal fill.

## Favicon (`assets/favicon/`)

| File | Content |
|------|---------|
| `favicon.svg` | Bare isotipo `#00bebc` on transparent, **no tile** — byte-identical to `binpar-isotipo-dark.svg`, viewBox 121.76×131.79; `sizes="any"` |
| `favicon.ico` | Real multi-size ICO, 4 PNG frames 16/32/48/64px (4693 B) |

Browsers cache favicons aggressively: version every reference with
`?v=<first 12 hex of sha256(file)>` and change it whenever the file changes:

```bash
shasum -a 256 favicon.svg | cut -c1-12   # 3f2ea0207fce
shasum -a 256 favicon.ico | cut -c1-12   # 5c39334f2516
```

Website metadata (`layout.tsx`, SVG only; `/favicon.ico` is served from
`public/` by default):

```ts
icons: {
  icon: [{ url: "/favicon.svg?v=3f2ea0207fce", type: "image/svg+xml", sizes: "any" }],
  shortcut: [{ url: "/favicon.svg?v=3f2ea0207fce", type: "image/svg+xml" }],
},
```

Product apps also declare the ICO fallback:

```ts
icons: {
  icon: [
    { url: "/favicon.svg?v=3f2ea0207fce", type: "image/svg+xml", sizes: "any" },
    { url: "/favicon.ico?v=5c39334f2516", sizes: "16x16 32x32 48x48 64x64" },
  ],
  shortcut: "/favicon.ico?v=5c39334f2516",
},
```

The JSON-LD publisher logo is `absoluteUrl("/favicon.svg")`
(`blog/[slug]/page.tsx`). There is no apple-touch-icon and no manifest. Always
use these exact files for any BinPar web property; organization skins (e.g.
CatSalut) keep their own favicon.

## Rules

- Light bg → `binpar-logo-light` (navy wordmark + teal mark); dark bg →
  `binpar-logo-dark` (white + turquoise). Never mix: the navy wordmark
  disappears on dark. On the always-dark contrast band → `-dark` in BOTH
  themes.
- Keep native proportions (lockup 430.04:131.79 ≈ 3.26:1; isotipo
  121.76:131.79 ≈ 0.924:1). Never stretch, crop, recolor partially, add
  effects or outlines, rotate, or rebuild the wordmark in a font.
- The full lockup is the default representation; the isotipo alone is for
  small or square slots (favicons, avatars, rails, chat identity, map pins,
  loaders, intros).
- The mark is a solid accent silhouette on transparent: never place it on a
  teal/turquoise fill (it vanishes). Use the glass app-icon tile or the page
  surface.
- On photos or gradients, place the logo over an area quiet enough to read
  the wordmark, or use the isotipo.
- Animate the mark only with the canonical reveal/loader recipes; the
  silhouette never changes shape (`motion-system.md` → Brand mark motion).
- The name in copy is exactly "BinPar". Uppercase "BINPAR" only through CSS
  `uppercase` on eyebrows/micro-labels; lowercase `binpar` only in
  identifiers (file names, URLs, events).

## Partner / third-party logos

In dark mode, monochrome partner logos are inverted with utilities rather than
extra assets: `dark:brightness-0 dark:invert` (optionally `dark:opacity-80`).
Logos with a dedicated dark variant (Axia → `axia-white.svg`) switch files
with the same `dark:hidden` / `dark:block` pattern instead
(`success-cases/success-cases-data.ts` `darkLogo`). BinPar is no longer a
partner credit: there is no separate company credit in the footer, and the
old yellow company logo (`public/logos/BinparSquare.svg`) is unreferenced —
never use it for the product.
