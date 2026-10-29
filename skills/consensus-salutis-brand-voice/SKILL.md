---
name: consensus-salutis-brand-voice
description: >
  BinPar (formerly Consensus Salutis) brand voice and writing style guide for the BinPar
  institutional medical AI platform. Provides the tone identity (clinical sobriety), the four
  calibration dials, the impersonal-analytical narrator, the product naming rules, the ban on
  personifying the AI, the coined lexicon, clinical and regulatory red lines, the public
  disclosure boundary, the five blog archetypes with word budgets, and an actionable review
  mode with severities. Use when writing, reviewing, editing or auditing any copy for the BinPar
  clinical AI platform: blog MDX articles, website pages, proposals, decks, email, product
  notes. Also use when checking existing copy for voice compliance. Sister skill to
  consensus-salutis-brand-design-system: that one says how the brand looks, this one says how
  it talks.
---

> **Deprecated:** superseded by `binpar-brand-voice` in BinPar/skills (identity manual v1.0). Prefer it; this copy is no longer maintained.

# BinPar Brand Voice

> The product was named **Consensus Salutis** until the website rename (`05d5437`, 2026-10-06).
> The skill ID keeps the legacy `consensus-salutis-` prefix on purpose; the name in copy is
> **BinPar**.

## Identity: clinical sobriety

**BinPar** turns clinical guidelines, protocols and medical corpus into traceable answers for
healthcare organisations. Three capabilities stand behind it: BinPar (product and engineering),
Editorial Médica Panamericana (clinical knowledge) and AWS (resilient infrastructure). The copy
has to earn the trust that a hospital procurement committee demands.

The reference is **not a SaaS blog**. It is the editorial of a medical journal, or the preamble
of a clinical guideline. Authority comes from precision, never from enthusiasm.

Where the sister brand A2R sells *inspired possibility*, BinPar sells **defensibility**: the
reader should close the piece thinking *«esto lo puedo sostener delante de un comité»*. Anything
that does not serve that is cut.

> Sources: the production copy in **consensus-salutis-website** at `70613ae` (`home-cover.tsx`,
> `horizontal-home.tsx` → `VerticalHome`/`HeroPanel`, `clinical-process-showcase.tsx`,
> `success-cases/`, `product-strata/`, `volume-section.tsx`, `contact-assistant/`,
> `platform-walkthrough.tsx`, `contrast-footer.tsx`, the blog in `src/content/blog/`), the brand
> identity manual (Consensus Salutis era), and the functional documents in **consensus-salutis**
> (`docs/`). The website copy is the tone of record; the functional docs are background only and
> are subject to the disclosure boundary (`references/clinical-red-lines.md` §6). Where the site
> breaks a rule of this skill, the rule wins for new copy and the fragment is recorded as known
> debt (`references/examples-and-rewrites.md` §12).

**Language:** all customer-facing copy is **Spanish (es-ES)**. This skill is written in English;
every quoted string, example and rewrite stays in Spanish.

---

## Naming

| Rule | Detail |
|---|---|
| **Spelling** | **BinPar**: one word, capital B and P, in prose, `alt`, `aria-label`, metadata and email subjects. Never "Binpar", "BINPAR" typed, "Bin Par", "binPar" |
| **All caps** | Only through CSS `uppercase` on eyebrows and micro-labels; the source string stays "BinPar" |
| **Separator** | " · " between the name and a qualifier: "BinPar · Lecturas clínicas", "BinPar · Inicio". `<title>` follows each surface's template (website `%s \| BinPar`; product apps "BinPar — Chat" (es, en), "BinPar — Xat" (ca), "BinPar — Editor") |
| **Possessive** | "de BinPar": "Lecturas clínicas de BinPar", "el equipo de BinPar". No article before the name: "BinPar convierte…", never "la BinPar" |
| **Product or company** | The name covers both. When a sentence needs the difference: *la plataforma* for the product, *el equipo de BinPar* for the people. The legal entity, in legal text only, is **BinPar Team S.L.** |
| **Legacy name** | Never "Consensus Salutis", "Consensus" or "CS" in new copy. Only exception: one "formerly" note at first mention, "BinPar (antes Consensus Salutis)", where readers know the old name |
| **Addresses and IDs** | The domain stays `consensussalutis.com` (plus `app.` and `back.`); mailboxes such as `consensussalutis@binpar.com` and IDs such as the author slug `equipo-consensus-salutis` keep the legacy spelling. Quote them verbatim, never derive a name from them, never "fix" them |

> Full detail: `references/voice-and-narrator.md` §3. The name as a graphic (logo files, the
> outlined wordmark, never typeset as a logo) belongs to the sister skill
> `consensus-salutis-brand-design-system` (its `references/logo-usage.md`).

---

## The four dials

Each dial has an operating rule. A piece that misses one is off-brand even if it reads well.

| Dial | Position | Rule |
|---|---|---|
| **Certainty** | Calibrated, never maximal | Declaring limits is *on-brand*. A brand that sells traceability cannot write overconfident prose. Prefer "puede enlazar", "se diseña para", "conviene comprobar" over absolutes |
| **Concreteness** | High — the weak point of today's copy | Every claim needs an operational anchor: a role, a document, a decision or a failure mode. Never a paragraph that only stacks nouns ("capa de consulta institucional con gobierno del dato") |
| **Rhythm** | Medium, not Hemingway | One idea per sentence, paragraphs of 3-5 lines. Medical Spanish tolerates subordination; what it does not tolerate is chained nominalisation |
| **Warmth** | Low but not cold | Respect for the professional's judgement is the brand's form of affection: **el sistema ordena, el clínico decide** |

> Full detail: `references/voice-and-narrator.md`

---

## Narrator

**Impersonal analytical.** No "nosotros", no author persona. The subject of the sentence is the
problem, the organisation, the document or the process.

- The product appears **only when it earns the slot**: never in the opening, never as a closing
  sale, at most a couple of times in the body. That is what makes a piece read as sector
  analysis instead of a brochure.
- **Typified exception:** the **nota de producto** archetype, written in the third person of
  BinPar.
- **No second person.** Neither "tú" nor "usted". Write about "los equipos clínicos", "las
  organizaciones sanitarias", "el profesional". It is the register that ages best and the one
  that fits the public healthcare buyer. The site's contact assistant and platform page use *tú*
  throughout: an observed exception there, not a rule here (known debt,
  `references/examples-and-rewrites.md` §3).

> Full detail: `references/voice-and-narrator.md`

---

## Never personify the AI

This is the deliberate break with `a2r-brand-voice`, which personifies on purpose ("it listens",
"it adapts"). Here that is both a tone liability and a legal one: *el sistema entiende / sabe /
juzga / decide* attributes agency, and with agency comes clinical responsibility.

| Allowed verbs | Banned verbs |
|---|---|
| recupera, referencia, sintetiza, prioriza, señala, devuelve, contrasta, enlaza, registra, versiona | entiende, sabe, interpreta, juzga, decide, opina, diagnostica, aprende de ti, comprende, razona |

Most of the production copy does this correctly: *"El profesional formula una duda clínica en
lenguaje natural"*, *"La respuesta reúne la orientación clínica y permite consultar las fuentes
que respaldan sus conclusiones"*. Keep it. The exception is the process walkthrough (an
*orquestador* that "construye una orientación conjunta", experts quoted in the first person):
known debt, never a model (`references/examples-and-rewrites.md` §12).

> Full verb tables: `references/language-rules.md`

---

## Coined lexicon

Six terms, reused consistently. The first three name the promise; the last three are operational
and already exist in the product.

| Term | Meaning |
|---|---|
| **consenso verificable** | Flag term: a conclusion anyone can trace back to its source |
| **evidencia visible** | The source fragment is reachable from the answer, not merely claimed |
| **gobierno del conocimiento clínico** | Roles, controlled publication and versioning over the corpus |
| **preguntas de control** | The battery that checks the system has not degraded |
| **corpus vivo** | A base that changes, and therefore needs versioning |
| **umbral de revisión** | When an answer requires a human eye |

**Allowed public framing:** *comité clínico* and *comité de expertos* for the multi-specialty
consultation, already public on the site and in the product. The committee keeps documentary
verbs (reúne, contrasta, sintetiza) and never reads as a human panel that reviewed the answer.

**Banned as vague, or for implying the professional is replaced (M7):** copiloto, asistente
virtual, agente, cerebro clínico, and *orquestado* / *orquestación* as an adjective or abstract
noun. **Banned as architecture vocabulary (H7, disclosure):** agentes expertos, orquestador,
sub-agente. The site still uses some of them: known debt, not precedent.

> Full detail, plus the buzzword ban list: `references/language-rules.md`

---

## Clinical and regulatory red lines

**High severity. Any one of these invalidates the piece.**

1. **Nothing that sounds like a diagnosis or a therapeutic indication.** The system does not
   diagnose, does not prescribe, does not recommend treatment for a specific patient.
2. **No claim of clinical efficacy without a source.** Never "mejora los resultados del paciente"
   or "reduce errores un X%" without a citable study. Figures only if they exist, and always with
   their context.
3. **No medical-device or regulatory badge.** Never imply CE marking, MDR, health certification or
   AI Act conformity unless it is accredited.
4. **No comparisons with competitors, and no naming models.** Positioning is done by contrast of
   approach.

Distinguish **commercial fear** (banned: "no te quedes atrás") from **clinical risk analysis**,
which is legitimate and necessary here.

> Full detail with rewrites: `references/clinical-red-lines.md`

---

## Disclosure boundary

Public copy stops at the **functional level**: what the organisation gets and what guarantee it
has. Never the implementation.

**Banned in public material:** Convex, AI SDK, CRC, checksum, anchor, delta, VFS, table names,
model slots, model providers and versions, orchestrator/expert internals (*orquestador*, *agentes
expertos*; the public face is *comité de expertos*).

The mechanism may justify why a piece exists, but the text describes **the problem and the
guarantee**:

- ❌ "anchors con CRC-8 sobre un contador global"
- ✅ "una cita que sigue apuntando al párrafo correcto después de que el documento se actualice,
  y que puede verificarse"

> Full mapping from internal mechanism to public phrasing: `references/clinical-red-lines.md`

---

## Blog archetypes and budgets

| Archetype | Words | Closing |
|---|---|---|
| **marco** — criteria for deciding something | 1.400-1.800 | reflective |
| **mecanismo** — a problem and its guarantee | 1.200-1.600 | reflective |
| **sector** — regulation, adoption, trend | 1.000-1.400 | reflective |
| **evidencia** — how it is measured and what fails | 1.200-1.600 | reflective |
| **nota de producto** | 500-800 | CTA allowed |

Reflective closing, no call to action: conversion is done by the product pages. Only the
**nota de producto** takes a CTA.

> Section-by-section structure and budgets: `references/post-archetypes.md`

---

## Writing rules

These target what is in the website repo today.

- **No trailing period in titles.** The site does the opposite on purpose: the post title
  `"Cómo medir la fiabilidad de una respuesta clínica."` and every display heading
  (`"Respuestas clínicas trazables."`, `"De la consulta clínica a la evidencia."`) end with one.
  That is an observed exception on the site, not a rule. Never a period in new copy: H1, H2, H3,
  card titles, hero headlines or `excerpt`-adjacent titles.
- **No paragraph that restates the previous one.** The seed post
  `como-medir-la-fiabilidad-de-una-respuesta-clinica.mdx` is padded with LLM filler
  ("Estas señales no siempre indican un fallo grave, pero sí justifican una revisión"). Use it as
  a structural template, never as a quality standard.
- **No chained nominalisation.** Turn nouns back into verbs.
- **No emojis.**
- **Em dash sparingly**; parentheses for asides.
- **Word budget per section, not only per piece.**

> Full detail: `references/language-rules.md`

---

## Workflow: writing a piece

1. **Pick the archetype** and read its section in `references/post-archetypes.md`. Write down the
   word budget per section before writing a line.
2. **State the operational anchor.** Before drafting, name the role, document, decision or
   failure mode the piece revolves around. If you cannot name one, the piece has no thesis yet.
3. **Draft the opening without the product.** The first two paragraphs describe the problem as a
   sector problem.
4. **Draft the body** against the four dials. One idea per sentence. Every claim gets its anchor.
5. **Place the product at most twice**, in the body, and only where it is the natural example.
6. **Close reflectively.** No CTA (except nota de producto).
7. **Run the checklist** in `references/review-checklist.md`. Fix every HIGH before delivering.

## Workflow: reviewing existing copy (review mode)

Do not just diagnose. Produce a table of violations **with severity** and a proposed rewrite for
each fragment:

| # | Fragment (verbatim) | Rule | Severity | Proposed rewrite |
|---|---|---|---|---|

Severities: **HIGH** (invalidates the piece: clinical, regulatory, disclosure, personification),
**MEDIUM** (voice damage: abstraction, filler, narrator drift, banned lexicon),
**LOW** (mechanical: trailing period, em dash, budget overrun).

Order the table by severity. End with a one-line verdict: *publicable*, *publicable con
correcciones*, or *reescritura*.

> Full severity map and worked review: `references/review-checklist.md`

---

## Compliance checklist (short form)

- [ ] **Archetype** declared, and word budget respected per section
- [ ] **Certainty** calibrated: limits stated where they exist, no absolutes
- [ ] **Concreteness**: every claim has a role, document, decision or failure mode
- [ ] **Rhythm**: one idea per sentence, paragraphs of 3-5 lines
- [ ] **Warmth**: clinical judgement respected: el sistema ordena, el clínico decide
- [ ] **Narrator**: impersonal analytical, no "nosotros", no "tú"/"usted"
- [ ] **Name**: BinPar, exactly so; never Consensus Salutis / Consensus / CS / Binpar / BINPAR
      typed (one "antes Consensus Salutis" note allowed)
- [ ] **Product placement**: absent from the opening and the close, at most twice in the body
- [ ] **No personification**: no entiende/sabe/juzga/decide/interpreta
- [ ] **Lexicon**: coined terms used consistently; no copiloto/asistente/agente/cerebro clínico;
      no agentes expertos/orquestador/orquestado; *comité clínico* allowed, never as a human panel
- [ ] **Red line 1**: nothing that reads as diagnosis or therapeutic indication
- [ ] **Red line 2**: no efficacy claim or figure without a citable source and its context
- [ ] **Red line 3**: no CE/MDR/certification/AI Act conformity implied
- [ ] **Red line 4**: no competitors, no model names
- [ ] **Fear**: risk analysis yes, commercial fear no
- [ ] **Disclosure**: no Convex/AI SDK/CRC/anchor/delta/VFS/table names/model slots
- [ ] **Titles**: zero trailing periods
- [ ] **No restating**: no paragraph that reformulates the previous one
- [ ] **No nominalisation chains**, no emojis, em dash sparingly
- [ ] **Closing**: reflective, no CTA (except nota de producto)

> Full checklist with severities: `references/review-checklist.md`

---

## Reference index

| File | Topic | Read when... |
|---|---|---|
| `references/voice-and-narrator.md` | Four dials in depth, impersonal narrator, the product-note exception, emotional core | Setting or checking the voice of a piece |
| `references/language-rules.md` | Allowed/banned verbs, coined lexicon, buzzwords, rhythm, nominalisation, titles, punctuation | Writing sentences, choosing words, fixing style |
| `references/clinical-red-lines.md` | Diagnosis, efficacy, regulatory, competitors, disclosure boundary | Any claim about what the system does or achieves |
| `references/post-archetypes.md` | The five archetypes: structure, section budgets, openings, closings | Planning a blog piece |
| `references/examples-and-rewrites.md` | Before/after on real repo copy; known debt in the site copy (§12) | Learning the voice by contrast; reviewing site copy |
| `references/review-checklist.md` | Severities, review table format, worked audit | Auditing existing copy |

---

## Examples

### Example 1: writing a blog article

**Request:** *"Escribe el post sobre trazabilidad documental para el blog"*

**Expected behaviour:** Identify the archetype (**mecanismo**, 1.200-1.600 words). Open with the
sector problem, a citation that stops pointing at the right paragraph after the document is
updated, with no product mention. Use *evidencia visible* and *corpus vivo* consistently.
Describe the guarantee, never the anchor/CRC mechanism. Mention BinPar at most twice in the
body. Close reflectively, no CTA. H1 and all headings without a trailing period.

### Example 2: auditing existing copy

**Request:** *"Revisa la home contra la voz de marca"*

**Expected behaviour:** Produce the severity table. Flag *"El sistema selecciona los agentes
expertos adecuados…"* and *"El orquestador reúne las aportaciones de los expertos…"* as HIGH
(H7, architecture vocabulary), the first-person expert quote *"no asumiría que el edema es
exclusivamente renal"* as HIGH (H6), *"Conocimiento clínico orquestado por IA."* as MEDIUM (M7)
plus LOW (L1), *"El futuro de la salud. Ya está aquí."* as MEDIUM (M8, M9), *"Una capa de IA
seria, auditable y preparada para operar dentro de un sistema sanitario."* as MEDIUM (M1, no
operational anchor), *"Hablemos de tu organización."* as MEDIUM (M4, M5), and the cover lede
*"BinPar la IA médica institucional…"* as LOW (L11, missing *es*). These are recorded known debt:
flag them anyway and take the rewrites from `references/examples-and-rewrites.md` §12. Each row
carries a proposed rewrite. End with a verdict.

### Example 3: a product note

**Request:** *"Anuncia las preguntas de control en el blog"*

**Expected behaviour:** Use the **nota de producto** archetype (500-800 words). Third person of
BinPar is allowed here, and so is a single CTA. Still no personification, still no efficacy
claim, still functional level only.

### Example 4: a request that crosses a red line

**Request:** *"Di que reducimos los errores diagnósticos un 30%"*

**Expected behaviour:** Decline the claim, name red line 2, and offer the defensible alternative:
report the documented technical signal with its context (`references/clinical-red-lines.md`
§2), or state the figure only with a citable study attached.
