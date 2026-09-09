# Voice and Narrator

> Sources: brand identity manual; production copy in `consensus-salutis-website`
> (`src/app/plataforma/page.tsx`, `src/app/evidencia/page.tsx`, `src/app/seguridad/page.tsx`,
> `src/app/_components/horizontal-home.tsx` → `VerticalHome`).

## 1. Emotional core

One sentence per brand. A2R: *inspired possibility*. Consensus Salutis: **defensibility**.

The reader is a clinician, a systems lead, a quality manager or a medical director. They are not
looking for a reason to be excited. They are looking for something they can put in front of a
committee, an internal audit or a legal review without being embarrassed.

The test for any paragraph: **would a medical director sign under it?** If the sentence would
force them to defend a claim they cannot verify, cut it.

The production copy already states the boundary explicitly, and it is worth reusing verbatim as
a stance:

> "El producto se comunica como soporte a decisión y consulta de evidencia, no como sustituto
> del criterio profesional."
> — `src/app/evidencia/page.tsx`

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

> "Consensus Salutis transforma corpus médico, guías clínicas y documentación propia en una capa
> de consulta institucional con referencias, roles y procesos de validación."
> — `src/app/plataforma/page.tsx`

Nothing in that sentence is false. Nothing in it is anchored either. **Every claim needs one of
four anchors:**

| Anchor | What it looks like |
|---|---|
| **A role** | administrador, editor, supervisor, usuario final, comité de calidad, dirección médica |
| **A document** | guía clínica, protocolo de centro, criterio de derivación, versión publicada, epígrafe |
| **A decision** | qué se publica, qué se prioriza, cuándo se pasa a producción, cuándo se deriva |
| **A failure mode** | omitir una contraindicación, citar una fuente que no sostiene la conclusión, responder con más seguridad que la evidencia disponible |

Anchored rewrite of the paragraph above:

> "Un editor carga la guía en preproducción, un supervisor clínico la valida contra las preguntas
> de control y solo entonces pasa a producción. Cada respuesta posterior puede enlazar al
> epígrafe concreto que la sustenta."

Same length. Four anchors instead of zero.

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

The sample article gets this right in three words: *"No sustituyen el juicio clínico. Lo ordenan."*
Reuse the pattern.

| Cold | On-brand | Too warm |
|---|---|---|
| "El sistema determina la conducta adecuada." | "El sistema reúne la evidencia; la conducta la decide el equipo clínico." | "Sabemos lo duro que es tu día a día." |

No compliments to the reader. No "sabemos que". No empathy performance.

## 3. The impersonal analytical narrator

There is no author persona and no corporate "we". The grammatical subject of a Consensus Salutis
sentence is one of: the problem, the organisation, the professional, the document, the process, or
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
| "Hablemos de tu organización sanitaria" | "Una conversación sobre la organización sanitaria" |

Impersonal constructions that carry the weight: *conviene*, *exige*, *se comprueba*, *procede*,
*una revisión debería detenerse si*, *la práctica muestra que*.

### Product placement

The product is a character with a small role, and the piece must be readable as sector analysis
without it.

| Position | Rule |
|---|---|
| Opening (first 2 paragraphs) | **Never.** The problem opens the piece |
| Body | At most **two** mentions, and only where the product is the natural example of a general point |
| Closing | **Never as a sale.** The close returns to the general problem |

The name is *Consensus Salutis*, always in full, never abbreviated to "Consensus" or "CS" in
public copy.

Test: delete every product mention. If the piece collapses, it was a brochure.

### The typified exception: nota de producto

The **nota de producto** archetype is written in the third person of Consensus Salutis and may
place the product wherever it needs it, including the opening. It also takes a single CTA.

Everything else still applies: no personification, no efficacy claims, functional level only,
calibrated certainty. A product note is short (500-800 words) and factual: what shipped, what
problem it addresses, what the organisation has to do to use it.

## 4. Register notes for es-ES

- **Institutional, not academic.** Avoid *dicho esto*, *cabe señalar que*, *no es óbice*. The
  register is a clinical guideline's preamble, not a doctoral thesis.
- **No anglicisms where Spanish exists:** *insight* → *hallazgo*; *compliance* → *cumplimiento*
  (the noun *compliance* is tolerated in the security page's eyebrow because it is the buyer's
  own term, but prefer *cumplimiento* in body copy); *pipeline* → *proceso*; *deployment* →
  *despliegue*; *feature* → *capacidad*.
- **Keep the terms the sector actually uses:** Atención Primaria (capitalised as the level of
  care), guía clínica, protocolo, corpus, trazabilidad, gobierno del dato, SSO, RPO/RTO.
- **Numbers in Spanish convention:** thousands with a period (`30.000+`), decimals with a comma.
