# Examples and Rewrites

Every "before" on this page is real copy from `consensus-salutis-website`. The point is not that
the existing copy is bad. Most of it is on-brand, and several fragments are quoted elsewhere in
this skill as models. The point is to show the four or five failure modes that recur, on material
the team recognises.

---

## 1. Noun stacking with no operational anchor

**Before**, `src/app/plataforma/page.tsx`, hero body:

> "Consensus Salutis transforma corpus médico, guías clínicas y documentación propia en una capa
> de consulta institucional con referencias, roles y procesos de validación."

**Diagnosis:** MEDIUM. Nothing false, nothing checkable. Four institutional nouns
(*capa*, *referencias*, *roles*, *procesos*) and no role, document, decision or failure mode.
Three `de` phrases carrying the meaning.

**After:**

> "Consensus Salutis convierte guías, protocolos y documentación propia en una consulta que la
> organización gobierna: un editor carga el contenido, un supervisor clínico lo valida y cada
> respuesta posterior puede enlazar al epígrafe que la sustenta."

**What changed:** two roles, one document unit (*epígrafe*), one decision (*valida*), and the
verbs do the work. Same register, same length.

---

## 2. Trailing periods in titles

**Before**, the post frontmatter and the page heroes:

> "Cómo medir la fiabilidad de una respuesta clínica."
> "Conocimiento clínico gobernado por IA."
> "Un sistema operativo para el conocimiento clínico."
> "Precisión medible sin perder trazabilidad clínica."
> "Diseñado para operar donde la confianza no es decorativa."

**Diagnosis:** LOW, but systematic: every H1 in the site carries a period no other heading level
uses.

**After:** drop the period in all five. `excerpt` fields stay as they are: they are sentences and
keep their full stop.

---

## 3. Second person

**Before**, `VerticalHome`, contact section:

> "Hablemos de tu organización sanitaria."
> "Revisamos caso de uso, restricciones de seguridad, requisitos de integración y el nivel de
> evidencia necesario."

**Diagnosis:** MEDIUM. *tu* plus *hablemos* plus *revisamos*. Second person and corporate first
person in two lines. The second sentence is otherwise excellent: four concrete anchors, no filler.

**After:**

> "Una conversación sobre la organización sanitaria"
> "La primera reunión revisa el caso de uso, las restricciones de seguridad, los requisitos de
> integración y el nivel de evidencia necesario."

**Note:** contact and form sections are the hardest place to hold the impersonal narrator. The
move is to make the *meeting* the subject, not the reader.

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

## 6. Personification (a hazard, not a current defect)

The production copy is clean here. *"El sistema recupera"*, *"contrasta las fuentes
recuperadas"*, *"sintetiza una respuesta operativa y enlaza el fragmento"* are all correct. The
drift shows up in new drafts:

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

> "Consensus Salutis reduce los errores de consulta y mejora la seguridad del paciente."

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

**After**, following `src/app/seguridad/page.tsx`:

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

> "A diferencia de los chatbots genéricos, Consensus Salutis no inventa respuestas."

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
