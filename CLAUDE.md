# Consensus Salutis Skills Repository

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

The `consensus-salutis-brand-design-system` skill is extracted from two sources:

- The brand identity manual PDF (logo, philosophy, palette, Plus Jakarta Sans)
- The production website implementation in the `consensus-salutis-website` repo
  (`src/styles/globals.css`, `src/app/layout.tsx`, `src/app/_components/`)

When the website implementation changes (tokens, components, motion), update the
skill references to match. The website code wins over the PDF for implementation
details; the PDF wins for brand-identity rules (logo construction, core palette).

Note: the definitive home layout is the **vertical** one (`VerticalHome`,
`env.VERTICAL_HOME`). The horizontal rail variant exists but is not the canonical
landing pattern.

## Language

- Skills are written in English
- The website content and brand manual are in Spanish; keep Spanish literals
  (UI copy, examples) as-is when quoting them
