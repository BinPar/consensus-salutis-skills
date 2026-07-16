# Consensus Salutis Skills

Agent skills for [Claude Code](https://claude.com/claude-code) for the **Consensus Salutis** brand and platform.

## Available skills

| Skill | Description |
|---|---|
| [`consensus-salutis-brand-design-system`](skills/consensus-salutis-brand-design-system/SKILL.md) | Brand design system reference and enforcement guide: color palette and design tokens, typography (Sora + Plus Jakarta Sans), logo usage, light/dark theming, UI component recipes, the signature signal-field motion system, and landing/blog page patterns. Extracted from the brand identity manual and the production website. |

Once installed, Claude automatically applies the skill whenever a task touches
Consensus Salutis visual design: building UI, generating CSS/tokens, creating
marketing assets, reviewing brand compliance, writing landing or blog pages, etc.

---

## Installation

### Option A — Claude Code plugin system (recommended)

Add this repository as a plugin marketplace and install the plugin:

```
/plugin marketplace add BinPar/consensus-salutis-skills
/plugin install consensus-salutis-skills@consensus-salutis-skills
```

To update later:

```
/plugin marketplace update consensus-salutis-skills
```

> The repo is private, so your `gh`/git credentials must have access to
> `BinPar/consensus-salutis-skills`.

### Option B — npx skills CLI

Install every skill from the repo:

```bash
npx skills add BinPar/consensus-salutis-skills
```

Install a specific skill only:

```bash
npx skills add BinPar/consensus-salutis-skills --skill consensus-salutis-brand-design-system -a claude-code -y
```

Install globally (available in all your projects):

```bash
npx skills add BinPar/consensus-salutis-skills -g
```

List what's available without installing:

```bash
npx skills add BinPar/consensus-salutis-skills --list
```

### Option C — manual (project-local)

Clone and copy the skill into the target project's `.claude/skills/` directory:

```bash
git clone git@github.com:BinPar/consensus-salutis-skills.git
mkdir -p <your-project>/.claude/skills
cp -r consensus-salutis-skills/skills/consensus-salutis-brand-design-system \
  <your-project>/.claude/skills/
```

Or for your user (all projects): copy into `~/.claude/skills/`.

---

## Verifying the installation

In a Claude Code session:

1. Run `/skills` (or check the available-skills list) — you should see
   `consensus-salutis-brand-design-system`.
2. Ask something on-brand, e.g. *"Genera los tokens CSS de Consensus Salutis"* —
   Claude should load the skill and answer with the exact `@theme` block,
   fonts, and light/dark rules.

You can also invoke it explicitly with `/consensus-salutis-brand-design-system`.

---

## What the skill contains

```
skills/consensus-salutis-brand-design-system/
├── SKILL.md                        # Main guide: identity, quick tokens, workflows,
│                                   # core rules, compliance checklist, examples
├── references/
│   ├── colors-and-tokens.md        # Palette, Tailwind v4 @theme block, semantic maps
│   ├── typography.md               # Sora + Plus Jakarta Sans, hierarchy, MDX recipe
│   ├── logo-usage.md               # Logo philosophy, variants, favicon, partner logos
│   ├── light-dark-mode.md          # Theme architecture, toggle, boot script
│   ├── ui-components.md            # Buttons, cards, header/footers, forms, chat mock
│   ├── motion-system.md            # Grid bg, SignalField, reveals, counters
│   ├── landing-patterns.md         # Canonical (vertical) home structure
│   └── blog-patterns.md            # Article model, cards, index & article pages
└── assets/
    ├── logos/                      # consensus-{light,dark}.svg + isotipos
    └── favicon/                    # Canonical favicon.svg + favicon.ico
```

Sources of truth: the brand identity manual (PDF) and the production
implementation in the `consensus-salutis-website` repository. When the website
changes (tokens, components, motion), update the references here to match.

---

## Creating a new skill

1. Copy the template:

```bash
cp template/SKILL.md.template skills/my-new-skill/SKILL.md
```

2. Edit `skills/my-new-skill/SKILL.md`:
   - Set `name` to match the directory name (`my-new-skill`)
   - Write a clear `description` (what it does AND when to use it)
   - Replace all placeholder sections

3. Register it in `.claude-plugin/marketplace.json`:

```json
"skills": ["./skills/consensus-salutis-brand-design-system", "./skills/my-new-skill"]
```

4. Commit and push. Naming rules and frontmatter validation live in
   [CLAUDE.md](CLAUDE.md).

## Skill structure

Each skill lives in its own directory under `skills/`:

```
skills/
└── my-skill/
    ├── SKILL.md          # Required — frontmatter + instructions
    ├── scripts/          # Optional — helper scripts
    ├── references/       # Optional — additional docs
    └── assets/           # Optional — templates, data files
```

## Resources

- [Agent Skills specification](https://agentskills.io/specification)
- [Claude Code skills docs](https://code.claude.com/docs/en/skills)
- [Plugin marketplaces](https://code.claude.com/docs/en/plugin-marketplaces)
