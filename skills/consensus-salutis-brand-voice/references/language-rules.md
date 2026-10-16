# Language Rules

> All customer-facing copy is Spanish (es-ES). Examples stay in Spanish.

## 1. Verbs: what the system may and may not do

The system performs **documentary operations**. It does not perform **cognitive or clinical acts**.
This is a tone rule and a liability rule at once: a verb that grants understanding grants agency,
and agency in a clinical setting means responsibility.

### Allowed

| Verb | Use for |
|---|---|
| **recupera** | bringing documents or fragments out of the corpus |
| **referencia** / **enlaza** | pointing at the source fragment or page |
| **sintetiza** | composing an answer from retrieved sources |
| **prioriza** | applying the organisation's documentary priorities |
| **contrasta** | putting retrieved sources against each other |
| **señala** | flagging something for human attention |
| **devuelve** | returning a result |
| **registra** / **versiona** | logging and versioning |
| **estructura** / **organiza** / **ordena** | arranging knowledge |
| **permite** / **facilita** | enabling a human action (the human keeps the verb of decision) |

### Banned

| Verb | Why |
|---|---|
| entiende, comprende | attributes understanding |
| sabe | attributes knowledge |
| interpreta | attributes clinical reading |
| juzga, valora | attributes judgement |
| decide, determina, resuelve | attributes the decision that belongs to the clinician |
| opina, cree, considera | attributes opinion |
| diagnostica, indica, prescribe, recomienda (a un paciente) | crosses the clinical red line |
| aprende de ti, se adapta a ti, te conoce | personification plus second person |
| razona, piensa, reflexiona | attributes cognition |

### The rewrite move

When a banned verb is the natural one, move the cognition to the human and leave the documentary
operation with the system.

| Off-brand | On-brand |
|---|---|
| "El sistema entiende la duda clínica." | "El profesional formula la duda; el sistema recupera el conocimiento relevante." |
| "La plataforma decide qué fuente es más fiable." | "La plataforma aplica las prioridades documentales definidas por la organización." |
| "La IA interpreta la guía." | "La respuesta enlaza el epígrafe de la guía que la sustenta; la interpretación es del clínico." |
| "El sistema sabe cuándo no tiene información." | "Entre las preguntas de control hay casos en los que la respuesta correcta es declarar información insuficiente." |

Same rule for nouns and adjectives: no *criterio del sistema*, no *opinión de la IA*, no
*respuesta inteligente*. "Inteligencia artificial" as the name of the technology is fine.
*inteligente* as a compliment to the product is not.

## 2. Coined lexicon

Six terms. Use the exact wording, always lowercase (they are concepts, not product names).

| Term | Definition | Use it when |
|---|---|---|
| **consenso verificable** | A conclusion anyone can trace back to its source. The flag term of the brand | Talking about the promise as a whole |
| **evidencia visible** | The source fragment is reachable from the answer, not merely asserted | Talking about citation and traceability |
| **gobierno del conocimiento clínico** | Roles, controlled publication, review and versioning over the corpus | Talking about who may change what |
| **preguntas de control** | The battery of questions that verifies the system has not degraded | Talking about evaluation and regression |
| **corpus vivo** | A knowledge base that changes, and therefore needs versioning | Talking about maintenance over time |
| **umbral de revisión** | The point at which an answer requires a human eye | Talking about supervision and escalation |

Rules of use:

- One flag term per piece is enough. Repeating *consenso verificable* five times reads as a slogan.
- Define a term the first time it appears in a piece, in one clause, then use it bare.
- Do not invent new coined terms without adding them here first.
- Current public product vocabulary (website `70613ae` and the product) is reused as-is:
  *respuestas clínicas trazables*, *fuentes verificables*, *evidencia trazable*, *consulta
  clínica*, *conversación con contexto*, *aportaciones*, *Bibliografía* (the references
  heading), *epígrafes clínicos*, *preguntas de evaluación*, *volumen y actualización*.
- Former website vocabulary (old plataforma page, rewritten in `79663ea`) stays allowed but is
  no longer quoted from the site: *ingesta multiformato*, *ciclo de publicación*, *roles
  institucionales*, *dashboard operativo*, *tests automáticos*, *gobierno del dato*.

### Public framing of the consultation: *comité*

*comité clínico* and *comité de expertos* are allowed public lexicon. Both are already public:
the home's chat mock ("Comité clínico", "Pregunta clínica al comité..."), process step 02
("Comité de expertos") and the product's own chat. They are the public face of what the
architecture calls orchestrator and experts, and the right target when rewriting *agentes
expertos* or *orquestador*.

| Rule | On-brand | Off-brand |
|---|---|---|
| Documentary verbs only | "el comité de expertos reúne las aportaciones de cada especialidad" | "el comité opina", "el comité decide la pauta" |
| Specialties and their corpus, not people | "consulta los corpus de Cardiología, Farmacología y Nefrología" | "un comité de especialistas revisa el caso" |
| Never a human sign-off | "la respuesta reúne las aportaciones con su procedencia; el clínico decide" | "validado por un comité de expertos" |

A committee that "validates" or "reviews" an answer claims a human review that did not happen.
That is HIGH (H9), not a lexicon slip.

### Banned lexicon

**Because they are vague or imply the professional is replaced (M7):**

- copiloto
- asistente virtual
- agente (in customer-facing copy)
- cerebro clínico
- segunda opinión (implies a clinical opinion)
- IA que piensa como un médico
- orquestado, orquestación (as an adjective or abstract noun: "orquestado por IA" names no
  component)

**Because they name the architecture (H7, a disclosure breach, `clinical-red-lines.md` §6):**

- orquestador
- agentes expertos (internally it is the architecture's term)
- sub-agente

The home hero ("orquestado por IA", M7) and the process walkthrough ("agentes expertos",
"orquestador", H7) still use them: known debt (`examples-and-rewrites.md` §12), never precedent.

**Corporate buzzwords (M8):**

- solución integral, solución end-to-end, solución escalable
- disruptivo, revolucionario, puntero, de vanguardia, next-generation
- sinergia, apalancar, cambio de paradigma
- ecosistema (unless it literally means a set of integrated systems)
- transformación digital as a standalone promise
- futurism: el futuro de la salud, ya está aquí, la sanidad del futuro

**Commercial fear (H8, see `clinical-red-lines.md` §5 for the legitimate alternative):**

- "no te quedes atrás"
- "el futuro no espera"
- "tus competidores ya están..."
- "no puedes permitirte..."

## 3. Rhythm and syntax

- **One idea per sentence.** Two clauses maximum; the second qualifies the first.
- **Paragraphs of 3-5 lines.** Under 2 lines reads as a soundbite; over 6 loses the clinician.
- **Sentence length target:** 15-28 words. A 40-word sentence is a paragraph that lost its period.
- **Verb-first thinking.** If the only verbs are *ser*, *haber*, *tener* or *permitir*, rewrite.

### Nominalisation chains

The single most common defect in institutional Spanish. Any string of two or more `de` phrases
carrying the meaning is a chain.

| Chain | Rewrite |
|---|---|
| "la implementación de la validación de la incorporación de contenidos" | "los contenidos se validan antes de incorporarse" |
| "la mejora de la trazabilidad de las respuestas del sistema" | "las respuestas quedan trazables" |
| "el establecimiento de criterios de aceptación de la revisión" | "el equipo fija qué respuestas acepta" |
| "una capa de consulta institucional con gobierno del dato" | "una consulta que la organización gobierna: quién publica, quién valida, qué versión responde" |

Mechanical test: count `de` in a sentence. Three or more, and the sentence needs verbs.

### Connectives to avoid

*Por otro lado*, *en este sentido*, *cabe destacar*, *es importante señalar*, *como hemos visto*,
*en definitiva*. They are filler that announces a transition instead of making one. Prefer a
concrete link: *La consecuencia operativa es...*, *El caso contrario...*, *Cuando el corpus
cambia...*.

## 4. The filler ban

The seed post is the reference for what **not** to do. Its padding pattern: a paragraph
makes a point, and the next paragraph restates it in different words with a hedge attached.

> "Estas señales no siempre indican un fallo grave, pero sí justifican una revisión."
> — `src/content/blog/como-medir-la-fiabilidad-de-una-respuesta-clinica.mdx`

That sentence adds no anchor, no example and no consequence. It exists to fill space.

**Detection heuristics:**

| Symptom | Example opener |
|---|---|
| Restates the previous paragraph | "En otras palabras...", "Es decir, ..." |
| Announces its own obviousness | "Como es lógico", "Evidentemente" |
| Hedged non-claim | "No siempre X, pero sí Y" with no criterion for telling them apart |
| Generic importance claim | "Esto es especialmente importante en organizaciones complejas" |
| Empty enumeration | "clínicos, responsables de sistemas, equipos legales y dirección" with nothing said about any of them |

**The fix is always the same:** delete, or add the missing anchor. "Estas señales justifican una
revisión" becomes useful the moment it says *who* reviews and *what they look at first*:

> "Una fuente citada que no sostiene la conclusión apunta a la recuperación; una omisión de
> advertencias, a la segmentación del corpus. El supervisor clínico decide cuál de las dos
> revisar primero."

## 5. Titles and headings

- **Zero trailing periods.** H1, H2, H3, H4, card titles, hero headlines, `excerpt` titles,
  metric labels used as titles. Never a period.
- Sentence case, not title case: *"Del documento fuente a la decisión: evidencia visible en cada
  consulta"*.
- A colon is the preferred way to carry a subtitle. One colon per title.
- No question marks in H1. A question is allowed as an H2 when the section answers it.
- Numbered H2 (`## 1. ...`) is acceptable in **marco** and **evidencia** archetypes, where the
  piece is a set of criteria. Avoid elsewhere.
- Headings carry the anchor too: *"Señales de alerta"* is fine; *"Consideraciones adicionales"*
  is not.

### The trailing-period debt on the site

Every display heading on the site carries a trailing period, and the two-line headings are two
sentences with the second in the accent colour. That is the site's deliberate style since the
redesign, recorded here as an observed exception, not a rule. New copy drops the period; when a
two-line heading needs two clauses, join them with a comma. Titles to fix when touched:

| Current | Where | Fixed |
|---|---|---|
| "Cómo medir la fiabilidad de una respuesta clínica." | post frontmatter | "Cómo medir la fiabilidad de una respuesta clínica" |
| "Respuestas clínicas trazables." | cover H1, accent line (`home-cover.tsx`) | "Respuestas clínicas trazables" |
| "Conocimiento clínico orquestado por IA." | home hero H2 (`horizontal-home.tsx`) | Period and lexicon: `examples-and-rewrites.md` §12 |
| "El futuro de la salud. Ya está aquí." | casos H2 (`territorial-case-definitive-two.tsx`) | A rewrite, not a period fix: `examples-and-rewrites.md` §12 |
| "Tres capacidades. Una sola arquitectura." | arquitectura H2 (`product-strata-scene.tsx`) | "Tres capacidades, una sola arquitectura" |
| "El conocimiento avanza. La base se actualiza." | volumen H2 (`volume-section.tsx`) | "El conocimiento avanza, la base se actualiza" |
| "De la consulta clínica a la evidencia." | plataforma H1 (`platform-walkthrough.tsx`) | "De la consulta clínica a la evidencia" |
| "El conocimiento de tu organización, en cada consulta." | plataforma CTA H2 | "El conocimiento de cada organización, en cada consulta" (also M4) |
| "Hablemos de tu organización." | contacto H2 (`contact-assistant.tsx`) | `examples-and-rewrites.md` §3 (also M4, M5) |

`excerpt` fields are full sentences and **do** take a period.

## 6. Punctuation and formatting

| Item | Rule |
|---|---|
| **Em dash (—)** | Sparingly. Parentheses for asides. Never two em dashes in one paragraph |
| **Emojis** | Never, anywhere |
| **Bold** | For the operative term of a paragraph, at most once per paragraph. Never a whole sentence |
| **Italics** | For a term being defined or quoted as language, not for emphasis |
| **Bullet lists** | Allowed for criteria, checks and enumerated failure modes. Not for prose that lost its paragraph. Maximum two lists per article section |
| **Numbered lists** | For sequences and criteria that will be referenced later |
| **Blockquotes** | At most one per article, for the piece's load-bearing sentence |
| **Quotation marks** | Spanish angle quotes «» for quoted speech; straight double quotes for terms in code or UI |
| **Percentages** | `30 %` with a space is the RAE form; the repo uses `30%`. Follow the repo |
| **Numbers** | Thousands with a period (`30.000`), decimals with a comma (`8,5`) |
| **Acronyms** | Expand on first use unless the buyer uses it daily (SSO, RPO, RTO, MIR, IA are safe) |

## 7. Word budgets per section

Budget the piece, then budget its sections. Overrun is a MEDIUM finding in review.

| Section | Share of the piece |
|---|---|
| Opening (problem statement, no product) | 10-15 % |
| Each body section | 20-25 % |
| Closing (reflective) | 10 % |

A 1.400-word **marco** piece is therefore roughly: 180-word opening, three 320-word sections,
140-word close. Write the numbers down before drafting.
