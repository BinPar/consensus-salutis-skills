# BinPar Skills Repository (consensus-salutis-skills)

> [!WARNING]
> **Deprecated.** This repository is retired. The BinPar brand skills now live in
> [BinPar/skills](https://github.com/BinPar/skills) and follow the BinPar identity
> manual v1.0: `binpar-brand-design-system` (replaces `consensus-salutis-brand-design-system`),
> `binpar-brand-voice` (replaces `consensus-salutis-brand-voice`) and `binpar-documents`
> (branded PDFs). Migrate with:
>
> ```bash
> npx skills remove consensus-salutis-brand-design-system consensus-salutis-brand-voice
> npx skills add BinPar/skills --skill binpar-brand-design-system --skill binpar-brand-voice -a claude-code -y
> ```

## Naming

- The product was renamed **BinPar** (website `05d5437`, 2026-10-06; it was
  Consensus Salutis). All user-facing skill content says "BinPar".
- Skill IDs, directory names, the plugin/marketplace name
  (`consensus-salutis-skills`) and this repo name keep the legacy
  `consensus-salutis-` prefix on purpose: renaming breaks installed copies
  (`skills-lock.json`, `.claude/skills` symlinks, slash commands). The website
  does the same with `consensus-theme`, author id `equipo-consensus-salutis`
  and the `consensussalutis.com` domain.
- Last alignment with the website: HEAD `70613ae` (2026-10-16).

## Project structure

```
skills/          — Agent skills (each in its own subdirectory)
template/        — SKILL.md template for creating new skills
.claude-plugin/  — Marketplace configuration
```

## Creating a new skill

1. Copy `template/SKILL.md.template` into `skills/<skill-name>/SKILL.md`
2. The directory name MUST match the `name` field in frontmatter
3. Fill in all required frontmatter fields and replace placeholder content

## Naming conventions

- Skill names: lowercase letters, numbers, and hyphens only
- Max 64 characters
- Must not start or end with a hyphen
- No consecutive hyphens (`--`)
- No spaces, underscores, or uppercase letters
- Directory name must match the `name` frontmatter field exactly

## Frontmatter validation

Every SKILL.md must have at minimum:

- `name` — matches directory name, follows naming rules above
- `description` — non-empty, max 1024 chars, explains what the skill does AND when to use it

## When adding skills to marketplace

After creating a new skill, add its path to `.claude-plugin/marketplace.json` in the `skills` array:

```json
"skills": ["./skills/my-new-skill"]
```

## Source of truth

### `consensus-salutis-brand-design-system`

Extracted from two sources:

- The production website implementation in the `consensus-salutis-website` repo
  (`src/styles/globals.css`, `src/app/layout.tsx`, `src/app/_components/` incl.
  `home-cover.*`, `brand-isotype-*`, `section-navigation.*`,
  `contrast-footer.tsx` + `footer-design.css`, `volume-section.*`,
  `contact-assistant/*`; logos and favicon from `public/logos/binpar-brand/`
  and `public/favicon.*`)
- The Consensus Salutis-era brand identity manual PDF — now only for the base
  palette and Plus Jakarta Sans. Its logo and philosophy chapters describe the
  retired C+S mark; there is no BinPar brand manual in any repo yet.

When the website implementation changes (tokens, components, motion, logos),
update the skill references to match, and re-copy the assets byte-for-byte
(recompute the favicon `?v=` hashes). Code wins for logo usage and
implementation details; the palette follows the tokens. The brand-mark loader
recipe has no website equivalent: it is the canonical spec for the product
apps.

Note: the definitive home layout is the **vertical** one (`VerticalHome`,
`env.VERTICAL_HOME`, default `"false"`), opened by `HomeCover` and built from
`HomePaintPanel` sections registered in `SectionNavigation`. The horizontal
rail variant exists but is not the canonical landing pattern. Never cite the
private `src/app/casos-lab/**` route or the deleted `/casos`, `/evidencia`,
`/seguridad` pages.

### `consensus-salutis-brand-voice`

Sister skill: the design system says how the brand looks, the voice skill says how
it talks. Extracted from:

- The brand identity manual
- The production copy in the `consensus-salutis-website` repo (`home-cover.tsx`,
  `horizontal-home.tsx` → `VerticalHome`/`HeroPanel`,
  `clinical-process-showcase.tsx`, `product-strata/`, `volume-section.tsx`,
  `success-cases/success-cases-data.ts`, `contact-assistant/`,
  `platform-walkthrough.tsx`, and the blog posts in `src/content/blog/`)
- The functional documents in the `consensus-salutis` repo (`docs/`) — background
  only, and subject to the skill's own disclosure boundary: implementation terms
  (Convex, AI SDK, CRC, anchors, deltas, VFS, model names) never reach public copy

The website copy is the tone of record. When it changes, update
`references/examples-and-rewrites.md` and the quoted fragments to match. Every
quoted string, example and rewrite stays in Spanish; the skill prose is English.

## Language

- Skills are written in English
- The website content and brand manual are in Spanish; keep Spanish literals
  (UI copy, examples) as-is when quoting them
