# Voice and Narrator

> Sources: production copy in `consensus-salutis-website` at `70613ae`
> (`src/app/_components/home-cover.tsx`, `horizontal-home.tsx` → `VerticalHome`/`HeroPanel`,
> `clinical-process-showcase.tsx`, `volume-section.tsx`, `contact-assistant/`,
> `platform-walkthrough.tsx`, `src/app/layout.tsx`, `src/content/blog/authors.ts`); the former
> `evidencia` and `seguridad` pages (deleted in `79663ea`; quoted as at `2449496`); brand
> identity manual (Consensus Salutis era).

## 1. Emotional core

One sentence per brand. A2R: *inspired possibility*. BinPar: **defensibility**.

The reader is a clinician, a systems lead, a quality manager or a medical director. They are not
looking for a reason to be excited. They are looking for something they can put in front of a
committee, an internal audit or a legal review without being embarrassed.

The test for any paragraph: **would a medical director sign under it?** If the sentence would
force them to defend a claim they cannot verify, cut it.

The former evidencia page stated the boundary explicitly. The page is gone; the sentence stays
as the brand's standing position, owned by this skill, and is worth reusing verbatim:

> "El producto se comunica como soporte a decisión y consulta de evidencia, no como sustituto
> del criterio profesional."
> — former `src/app/evidencia/page.tsx` (website ≤ `2449496`)

The live echo is the site description in `src/app/layout.tsx`: *"Plataforma de IA médica
institucional para soporte a la toma de decisiones, evidencia clínica y gobierno del conocimiento
sanitario."*

## 2. The four dials in depth

### Certainty: calibrated, never maximal

Declaring limits is a brand asset, not a weakness. A platform whose entire promise is traceability
cannot write prose that outruns its evidence.

**Calibration vocabulary (use it):** puede enlazar, se diseña para, está previsto, conviene
comprobar, en los casos en que, dentro del corpus disponible, según configuración, salvo que.

**Absolutes to avoid:** siempre, nunca falla, garantiza, elimina el error, asegura la corrección,
cualquier pregunta, todo el conocimiento médico.

| Off-brand | On-brand |
|---|---|
| "Cada respuesta enlaza a su fuente original." | "Cada respuesta puede enlazar al fragmento o página original que sustenta la información clínica." |
| "El sistema garantiza que el conocimiento está actualizado." | "Las actualizaciones se incorporan en entornos controlados, pasan por revisión y se trasladan a producción cuando el equipo responsable lo decide." |

Note that the on-brand versions are longer. That is the trade the brand accepts: precision costs
words, and the words buy defensibility.

### Concreteness: high, and the weak point of today's copy

This is where existing copy fails most often. The failure mode is the paragraph that stacks
institutional nouns and says nothing checkable.

> "Una capa de IA seria, auditable y preparada para operar dentro de un sistema sanitario."
> — `src/app/_components/horizontal-home.tsx`, `HeroPanel` lede

Nothing in that sentence is false. Nothing in it is anchored either: three adjectives about the
product and no way to check any of them. **Every claim needs one of four anchors:**

| Anchor | What it looks like |
|---|---|
| **A role** | administrador, editor, supervisor, usuario final, comité de calidad, dirección médica |
| **A document** | guía clínica, protocolo de centro, criterio de derivación, versión publicada, epígrafe |
| **A decision** | qué se publica, qué se prioriza, cuándo se pasa a producción, cuándo se deriva |
| **A failure mode** | omitir una contraindicación, citar una fuente que no sostiene la conclusión, responder con más seguridad que la evidencia disponible |

Anchored rewrite of the sentence above:

> "Un editor carga la guía en preproducción, un supervisor clínico la valida contra las preguntas
> de control y solo entonces pasa a producción. Cada respuesta posterior puede enlazar al
> epígrafe concreto que la sustenta."

Longer, and every adjective became a checkable operation: *auditable* is now a validation step
with a role, *preparada* is a controlled path to production. Four anchors instead of zero.

### Rhythm: medium, not Hemingway

The A2R voice is punchy. This one is not. Medical Spanish reads subordination without friction;
what it cannot absorb is nominalisation in chains.

- **One idea per sentence.** Two clauses maximum, and the second should qualify the first, not
  add a new claim.
- **Paragraphs of 3-5 lines.** A one-line paragraph is a soundbite, and soundbites belong to the
  other brand.
- **No chained nominalisation.** "la implementación de la validación de la incorporación de
  contenidos" → "los contenidos se validan antes de incorporarse".
- **Verbs over noun phrases.** If a sentence's only verb is *ser*, *tener* or *permitir*, it is
  probably a nominalisation chain in disguise.

### Warmth: low but not cold

The brand's affection is respect for professional judgement. It shows up structurally, not
lexically: never in adjectives about the reader, always in what the system is allowed to do.

**The formula:** *el sistema ordena, el clínico decide.*

The sample article gets this right in two: *"Estos criterios no sustituyen el juicio clínico. Lo
ordenan."* Reuse the pattern.

| Cold | On-brand | Too warm |
|---|---|---|
| "El sistema determina la conducta adecuada." | "El sistema reúne la evidencia; la conducta la decide el equipo clínico." | "Sabemos lo duro que es tu día a día." |

No compliments to the reader. No "sabemos que". No empathy performance.

## 3. The impersonal analytical narrator

There is no author persona and no corporate "we". The grammatical subject of a BinPar sentence is
one of: the problem, the organisation, the professional, the document, the process, or
(sparingly) the system.

### Banned narrator moves

| Move | Example | Why |
|---|---|---|
| Corporate "nosotros" | "Creemos que la trazabilidad es esencial." | Turns analysis into a manifesto |
| First person singular | "En mi experiencia..." | There is no author persona |
| Second person | "Si tu organización necesita..." | Ages badly, wrong register for a public healthcare buyer |
| Rhetorical questions to the reader | "¿Y si tu equipo pudiera...?" | Brochure move |
| Direct imperative | "Revisa tus preguntas de control." | Instructs the clinician instead of respecting their judgement |

### How to write around the second person

| Instead of | Write |
|---|---|
| "puedes comprobar si..." | "conviene comprobar si..." |
| "tu organización" | "la organización", "las organizaciones sanitarias" |
| "tu equipo clínico" | "el equipo clínico", "los equipos clínicos" |
| "necesitas versionar el corpus" | "un corpus vivo exige versionado" |
| "Hablemos de tu organización" | "Una conversación sobre la organización sanitaria" |

Impersonal constructions that carry the weight: *conviene*, *exige*, *se comprueba*, *procede*,
*una revisión debería detenerse si*, *la práctica muestra que*.

The site's contact assistant ("¿Cómo te llamas?", "Nuestro equipo te responderá…") and platform
page ("Explora la interfaz…") use *tú* and *nosotros* throughout. That is an observed exception
on the site, not a rule of this voice: still M4/M5 in review, rewrites in
`examples-and-rewrites.md` §3.

### Product placement

The product is a character with a small role, and the piece must be readable as sector analysis
without it.

| Position | Rule |
|---|---|
| Opening (first 2 paragraphs) | **Never.** The problem opens the piece |
| Body | At most **two** mentions, and only where the product is the natural example of a general point |
| Closing | **Never as a sale.** The close returns to the general problem |

Test: delete every product mention. If the piece collapses, it was a brochure.

### The product name

The name is **BinPar**: one word, capital B and P, as the website writes it since the rename
(`05d5437`, 2026-10-06). The product formerly named *Consensus Salutis* and
the company now share one brand.

| Case | Write | Never |
|---|---|---|
| Prose, `alt`, `aria-label`, metadata, email subjects | "BinPar" | "Binpar", "BINPAR", "Bin Par", "binPar", "Consensus Salutis", "Consensus", "CS" |
| Eyebrow or micro-label in caps | "BinPar" with CSS `uppercase` (as the chat mock and process scenes do) | "BINPAR" typed in the source |
| Name plus qualifier | "BinPar · Lecturas clínicas", "BinPar · Inicio", "BinPar · Nuevo chat" | "BinPar - Lecturas clínicas", "BinPar: Inicio" |
| Possessive | "Lecturas clínicas de BinPar", "el equipo de BinPar", "Oficinas de BinPar" | "la BinPar", "el BinPar" |
| Legal text (privacy, contracts) | "BinPar Team S.L." | "BinPar S.L.", or the bare name in a legal clause |
| Footer legal line | "© BinPar · Todos los derechos reservados" | "© BinPar all rights reserved" (English; survives only in the legacy horizontal home band) |
| A reader who knows the old name | "BinPar (antes Consensus Salutis)", once, at first mention | the old name anywhere else |

The home's architecture graphic types "BINPAR / SISTEMA INTEGRADO" in an SVG label: known debt
(`examples-and-rewrites.md` §12), not an exception to the caps rule.

`<title>` follows each surface's own template: `%s | BinPar` on the website; "BinPar — Chat"
(es, en), "BinPar — Xat" (ca) and "BinPar — Editor" in the product apps. Do not invent new
separators.

**Lowercase `binpar`** exists only in identifiers: URLs, file names, email domains, event names.

**Legacy spelling that stays.** The domain `consensussalutis.com` (and the product's `app.` and
`back.` subdomains), mailboxes such as `consensussalutis@binpar.com`, the blog author slug
`equipo-consensus-salutis` (displayed as "Equipo BinPar") and the IDs of these skills. They are
addresses and identifiers, not the name: quote them verbatim, never rewrite them, never derive a
name from them.

**Product or company.** "BinPar" names both, and most sentences do not need the difference. When
one does, *la plataforma* is the product and *el equipo de BinPar* the people.

### The typified exception: nota de producto

The **nota de producto** archetype is written in the third person of BinPar and may place the
product wherever it needs it, including the opening. It also takes a single CTA.

Everything else still applies: no personification, no efficacy claims, functional level only,
calibrated certainty. A product note is short (500-800 words) and factual: what shipped, what
problem it addresses, what the organisation has to do to use it.

## 4. Register notes for es-ES

- **Institutional, not academic.** Avoid *dicho esto*, *cabe señalar que*, *no es óbice*. The
  register is a clinical guideline's preamble, not a doctoral thesis.
- **No anglicisms where Spanish exists:** *insight* → *hallazgo*; *compliance* → *cumplimiento*
  (the former security page used *compliance* in an eyebrow because it is the buyer's own term;
  the current site says *cumplimiento*, and so does new copy); *pipeline* → *proceso*;
  *deployment* → *despliegue*; *feature* → *capacidad*.
- **Keep the terms the sector actually uses:** Atención Primaria (capitalised as the level of
  care), guía clínica, protocolo, corpus, trazabilidad, gobierno del dato, SSO, RPO/RTO.
- **Numbers in Spanish convention:** thousands with a period (`30.000+`), decimals with a comma.
