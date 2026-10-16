# Examples and Rewrites

Every "before" not marked as a draft is real copy from `consensus-salutis-website`, current at
`70613ae` (2026-10-16) unless marked *former* (pages deleted in `79663ea`; quoted as at
`2449496`). The
point is not that the existing copy is bad. Most of it is on-brand, and several fragments are
quoted elsewhere in this skill as models. The point is to show the four or five failure modes
that recur, on material the team recognises. §12 lists the current site copy that breaks a rule
of this skill: known debt, never a model.

---

## 1. Noun stacking with no operational anchor

**Before**, `src/app/_components/volume-section.tsx`, volume band intro:

> "Una base médica estructurada que incorpora las guías y protocolos de cada organización, con
> evaluación continua y validación clínica."

**Diagnosis:** MEDIUM. Nothing false, nothing checkable. Two nominalisations (*evaluación
continua*, *validación clínica*) hide who evaluates, against what, and who validates. No role, no
decision, no failure mode.

**After:**

> "Una base médica estructurada que incorpora las guías y protocolos de cada organización: un
> editor revisa cada cambio antes de publicarlo, y las preguntas de control comprueban en cada
> actualización que las respuestas críticas no se degradan."

**What changed:** the two nominalisations became two operations with their subjects. One role
(*editor*), one decision (*publicarlo*), one failure mode (*se degradan*) and a coined term
(*preguntas de control*). Same register.

---

## 2. Trailing periods in titles

**Before**, the post frontmatter and the site's display headings:

> "Cómo medir la fiabilidad de una respuesta clínica."
> "Respuestas clínicas trazables."
> "Tres capacidades. Una sola arquitectura."
> "El conocimiento avanza. La base se actualiza."
> "De la consulta clínica a la evidencia."

**Diagnosis:** LOW, but systematic, and deliberate on the site: every display heading carries a
period, and the two-line headings are two sentences. That is an observed exception on the site,
not a rule of this voice.

**After:** drop the period in all five, and join the two-line headings with a comma: "Tres
capacidades, una sola arquitectura". `excerpt` fields stay as they are: they are sentences and
keep their full stop. Full list in `language-rules.md` §5.

---

## 3. Second person

**Before**, `contact-assistant/contact-assistant.tsx` (the home's contact section and
`/contacto`) and `platform-walkthrough.tsx`:

> "Hablemos de tu organización."
> "¿Qué te gustaría explorar con BinPar?"
> "Hemos recibido tu consulta. Nuestro equipo te responderá en …"
> "Explora la interfaz, los paneles y tu área de usuario con una consulta de ejemplo."
> "Exploremos cómo integrar tus guías, protocolos y corpus médico en un entorno de consulta
> gobernado."

**Diagnosis:** MEDIUM (M4, M5). *tu*, *te*, *explora* plus *hablemos*, *nuestro equipo*,
*exploremos*. The site uses *tú* throughout its conversational contact assistant and the
platform page: an observed exception there, not a new rule. New copy stays impersonal.

**After:**

> "Una conversación sobre la organización sanitaria"
> "Caso de uso o necesidad de la organización"
> "Consulta recibida. La respuesta llegará a …"
> "Una consulta de ejemplo recorre la interfaz, los paneles y el área de usuario."
> "La primera reunión revisa cómo integrar las guías, los protocolos y el corpus médico de la
> organización en un entorno de consulta gobernado."

**Former model**, legacy `ContactPanel` (horizontal home only): *"Revisamos caso de uso,
restricciones de seguridad, requisitos de integración y el nivel de evidencia necesario."* Four
concrete anchors, no filler, one *revisamos* too many. Its rewrite is still the model: *"La
primera reunión revisa el caso de uso, las restricciones de seguridad, los requisitos de
integración y el nivel de evidencia necesario."*

**Note:** contact and form sections are the hardest place to hold the impersonal narrator. The
move is to make the *meeting* or the *message* the subject, not the reader.

---

## 4. Filler that restates the previous paragraph

**Before**, `src/content/blog/como-medir-la-fiabilidad-de-una-respuesta-clinica.mdx`:

> "Estas señales no siempre indican un fallo grave, pero sí justifican una revisión. A veces el
> problema está en la recuperación de documentos, otras en la síntesis, y otras en la propia
> estructura del corpus. La evaluación debe permitir distinguir esas causas para evitar
> correcciones superficiales."

**Diagnosis:** MEDIUM. The first sentence is a hedged non-claim. The second names three causes but
attaches no diagnostic to any of them. The third states an abstract requirement.

**After:**

> "Cada señal apunta a una capa distinta. Una fuente citada que no sostiene la conclusión apunta a
> la recuperación; una omisión de advertencias, a la segmentación del corpus; una variabilidad
> injustificada entre preguntas equivalentes, a la síntesis. El supervisor clínico decide cuál
> revisar primero, y ese orden es lo que evita correcciones superficiales."

**What changed:** each cause got its own observable symptom, and a role got the decision. Fewer
words, three anchors.

---

## 5. The same article's padding, section by section

The seed post is the structural template for MDX articles and should keep that role. As a
quality standard it is inflated: at ~1.500 words it carries roughly 300 words of restatement.

Recurring patterns to delete on sight:

| Fragment | Why it goes |
|---|---|
| "Esta mirada es especialmente importante cuando el sistema se integra en organizaciones sanitarias con múltiples equipos." | Generic importance claim, no anchor |
| "La precisión clínica responde a la pregunta de si el contenido es correcto. La trazabilidad responde a la pregunta de si puede revisarse. La utilidad responde a si ayuda a avanzar." | Restates the bullet list directly above it |
| "En organizaciones complejas, esa memoria evita repetir discusiones y convierte la revisión en un proceso acumulativo." | Nominalisation chain plus generic claim |
| "El resultado no es solo una puntuación: es una capacidad institucional para aprender, corregir y operar con seguridad." | Closing soundbite; belongs to the other brand |

The article's genuinely good sentences, to keep as models:

> "Una respuesta puede sonar correcta y, aun así, omitir una contraindicación, mezclar niveles de
> evidencia o perder el contexto operativo de una organización sanitaria."

Three named failure modes in one sentence. This is the target density.

> "Estos criterios no sustituyen el juicio clínico. Lo ordenan."

The warmth dial in five words.

> "Sin esa medición, cada actualización del conocimiento clínico se convierte en un acto de
> confianza difícil de auditar."

Clinical risk framing, not commercial fear. Exactly the distinction in `clinical-red-lines.md` §5.

---

## 6. Personification (a hazard, and one current defect)

Most of the production copy is clean here. Process steps 01 and 04 in
`clinical-process-showcase.tsx` keep the human and the document as subjects: *"El profesional
formula una duda clínica en lenguaje natural"*, *"La respuesta reúne la orientación clínica y
permite consultar las fuentes que respaldan sus conclusiones"*. The former step copy (*"El
sistema recupera"*, *"contrasta las fuentes recuperadas"*, *"sintetiza una respuesta operativa y
enlaza el fragmento"*) survives only in the legacy horizontal home and is still a model.

The current defect is the same showcase's committee scene: an *orquestador* that "construye una
orientación conjunta" and experts quoted in the first person. It is listed in §12 and is never a
model. The same drift shows up in new drafts:

| Draft | Fixed |
|---|---|
| "El sistema entiende la duda clínica y busca la respuesta." | "El profesional formula la duda en lenguaje natural; el sistema recupera el conocimiento relevante del corpus, las guías y los protocolos." |
| "La plataforma sabe qué fuente pesa más." | "La plataforma aplica las prioridades documentales que define la organización." |
| "La IA decide cuándo derivar a revisión humana." | "La organización fija el umbral de revisión; por encima de él la respuesta se señala para revisión humana." |

The third row is also the correct way to introduce the coined term *umbral de revisión*: define it
by who sets it.

---

## 7. Efficacy claims

**Before** (a draft sentence of the kind that gets requested):

> "BinPar reduce los errores de consulta y mejora la seguridad del paciente."

**Diagnosis:** HIGH. Red line 2, twice. No study, and *seguridad del paciente* is a clinical
outcome.

**After**, the defensible version:

> "El benchmark documentado no reporta fallos sobre el conjunto de preguntas citado, y se presenta
> como señal técnica contextualizada. El efecto sobre la práctica asistencial es lo que las
> preguntas de control permiten medir en cada organización."

**What changed:** the verifiable fact keeps its label; the clinical effect becomes something to be
measured rather than something claimed.

---

## 8. Regulatory badge

**Before** (a draft sentence):

> "Plataforma certificada y conforme al RGPD y al AI Act, lista para entornos sanitarios."

**Diagnosis:** HIGH. Red line 3. Two claimed conformities and an unqualified "certificada".

**After**, adapted from the former security page (`src/app/seguridad/page.tsx`, deleted in
`79663ea`):

> "Plataforma diseñada desde el inicio para privacidad, auditoría y despliegue en la Unión
> Europea. Las consultas no se usan para entrenar modelos globales, cada acción queda registrada y
> el historial de versiones permite reconstruir qué respondía el sistema en cada momento."

**What changed:** design orientation and verifiable controls replace conformity claims.

---

## 9. Disclosure boundary

**Before** (a draft paragraph for a **mecanismo** piece):

> "Cada unidad de conocimiento lleva un identificador con CRC-8 sobre un contador global, de modo
> que el sistema valida la referencia sin consultar la base de datos."

**Diagnosis:** HIGH. Four banned terms and an implementation description.

**After:**

> "Cada fragmento del corpus conserva una identidad estable: si el documento se reordena o se
> reescribe, la referencia sigue apuntando al mismo contenido, y cualquier parte del sistema puede
> comprobar que la cita es válida."

**What changed:** the guarantee survives; the mechanism disappears. Note that the guarantee is
*more* interesting to the buyer than the mechanism was.

---

## 10. Competitor positioning

**Before** (a draft opening):

> "A diferencia de los chatbots genéricos, BinPar no inventa respuestas."

**Diagnosis:** MEDIUM (implicit competitor category, product in the opening) and it hands the
reader the word *inventa* applied to a category the brand belongs to.

**After:**

> "Un sistema de propósito general responde con lo que ha visto. Una consulta institucional
> responde con lo que la organización ha publicado, y puede señalar de dónde viene cada
> conclusión."

**What changed:** contrast of approach, no category insult, product absent from the opening, and
the coined term *evidencia visible* is one sentence away.

---

## 11. A full opening, on-brand

For a **mecanismo** piece on documentary traceability, ~180 words, no product, no mechanism:

> "Una cita clínica envejece peor que el texto que la sostiene. El documento se actualiza, un
> epígrafe se reordena, un párrafo se reescribe, y la referencia sigue existiendo: apunta a un
> lugar que ya no dice lo que decía cuando se citó.
>
> En una consulta puntual el problema pasa desapercibido. En una organización sanitaria, no.
> Cuando una respuesta se incorpora a un informe, se discute en un comité o se revisa en una
> auditoría interna, lo que se examina no es la respuesta: es su procedencia. Una referencia que
> no se puede reconstruir convierte una conclusión revisable en una conclusión que solo puede
> creerse.
>
> El corpus clínico es, por definición, un corpus vivo. Las guías se actualizan, los protocolos de
> centro cambian, los criterios de derivación se ajustan. Un sistema que responda sobre esa base
> tiene dos obligaciones que suelen confundirse: mantener el contenido al día, y mantener
> localizable lo que respondió antes de estarlo."

**Why it works:** no product, no mechanism, three anchors (informe, comité, auditoría), the coined
term *corpus vivo* defined in passing, clinical risk framing without commercial fear, and the last
sentence sets up the piece's distinction.

---

## 12. Known debt in the current site copy

Website `70613ae` (2026-10-16). The website copy is the tone of record for the name, the claims
and the product vocabulary. Where it breaks a rule of this skill, the rule wins for new copy and
the fragment is listed here. Never quote these fragments as models. In review mode, flag them
with their codes like any other finding (the verdict follows the usual thresholds) and take the
rewrite from this table.

Decisions behind the table:

- *comité clínico* and *comité de expertos* are allowed public lexicon, and the target for most
  rewrites below (`language-rules.md` §2).
- *agente*, *agentes expertos*, *orquestador*, *orquestado* and *sub-agente* stay banned in new
  copy. *orquestador*, *agentes expertos* and *sub-agente* name components (H7); *agente*,
  *orquestado* and *orquestación* are banned lexicon (M7).
- *tú*, *nosotros* and trailing periods are observed exceptions on the site, not new rules.

| # | Fragment (verbatim) | Where | Codes | Suggested rewrite |
|---|---|---|---|---|
| 1 | "El sistema selecciona los agentes expertos adecuados y consulta sus corpus médicos, adaptados a la organización y la especialidad." | process step 02, `clinical-process-showcase.tsx` | H7 | "El comité de expertos reúne las especialidades que la consulta necesita, y cada una se consulta sobre su propio corpus médico, adaptado a la organización." |
| 2 | "El orquestador reúne las aportaciones de los expertos, contrasta sus matices y límites y construye una orientación conjunta para la consulta." | process step 03, same file; node label "Orquestador" in `clinical-process-visuals.tsx` | H7 | "La síntesis del comité reúne las aportaciones de cada especialidad, contrasta sus matices y límites y conserva la procedencia de cada una." Label: "Síntesis del comité" |
| 3 | "Conocimiento clínico orquestado por IA." | home hero H2, `horizontal-home.tsx` (`HeroPanel`) | M7, L1 | "Conocimiento clínico consultable con IA, trazable hasta su fuente" |
| 4 | "no asumiría que el edema es exclusivamente renal" | committee scene expert quote (`expertDetails`, `clinical-process-showcase.tsx`) | H6, H9 | Attribute to the specialty and its source, never an expert's first person: "Nefrología señala, con su fuente, el límite de atribuir el edema solo a la causa renal" |
| 5 | "Paciente de 68 años con diabetes tipo 2, hipertensión y enfermedad renal crónica…" taken to "Revisar AINE, IECA/ARA-II y diuréticos por riesgo renal e hiperpotasemia." and "Evitar atribuir el edema solo a la ERC o asumir causalidad por ibuprofeno." | committee scene cards, `clinical-process-data.ts`, `clinical-process-showcase.tsx` | H1 | Keep the demo at question-and-document level: the cards name the cited epígrafe, not the action. "Epígrafe citado: AINE en insuficiencia renal" |
| 6 | "El futuro de la salud. Ya está aquí." | casos H2, `success-cases/territorial-case-definitive-two.tsx` | M8, M9, M1, L1 | "IA médica que ya forma parte del sistema sanitario" (the section's own unrendered `casesIntro.title` in `success-cases-data.ts`, without the period; the organisations named on the map are its anchor) |
| 7 | "BinPar la IA médica institucional que conecta guías, protocolos y corpus médico con la práctica clínica." | cover lede, `home-cover.tsx` | L11 | "BinPar es la IA médica institucional que conecta guías, protocolos y corpus médico con la práctica clínica." |
| 8 | "Hablemos de tu organización.", "¿Cómo te llamas?", "Explora la interfaz…", "Exploremos cómo integrar tus guías…" | `contact-assistant/`, `platform-walkthrough.tsx` | M4, M5 | §3 |
| 9 | "Estamos en Madrid." / "Escríbenos o consulta cómo llegar a nuestras oficinas." | `/contacto`, `contacto/_components/contact-details.tsx` | M5, M4, L1 | "Oficinas en Madrid" / "Dirección, correo de contacto y cómo llegar" |
| 10 | "BINPAR / SISTEMA INTEGRADO" | architecture graphic SVG label, `product-strata/strata-rotatable-graphic.tsx` | M15 | Source string "BinPar / Sistema integrado" with CSS `uppercase` |
| 11 | A trailing period on every display heading | whole site | L1 | §2 and `language-rules.md` §5 |

**Rows 4 and 5:** the scenes replay a real captured consultation, so the answer text is product
output, not marketing copy, and the answers themselves are outside this skill. The debt is the
framing around them: an expert quoted in the first person, and cards that state what to do for a
described patient. A demo that stays at the level of the question, the specialties consulted and
the cited epígrafes makes the same point inside the red lines.
