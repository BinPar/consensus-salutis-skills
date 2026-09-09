# Review Checklist and Review Mode

Two uses: the checklist you run before delivering your own draft, and **review mode**, the
audit you produce when handed existing copy.

---

## 1. Severity map

| Severity | Meaning | Action |
|---|---|---|
| **HIGH** | Invalidates the piece. Clinical, regulatory, disclosure or personification | Must be fixed before publication. No exceptions |
| **MEDIUM** | Damages the voice. Abstraction, filler, narrator drift, banned lexicon, budget overrun | Fix, or justify in writing why it stays |
| **LOW** | Mechanical. Trailing period, punctuation, list count, heading depth | Fix in passing |

### HIGH findings

| Code | Rule |
|---|---|
| H1 | Reads as diagnosis or therapeutic indication for a patient |
| H2 | Efficacy claim or figure without a citable source and its context |
| H3 | Clinical outcome presented as technical signal, or the reverse |
| H4 | Implies CE marking, MDR, medical-device status, certification or AI Act conformity |
| H5 | Names a competitor, a model, or a model provider |
| H6 | Personifies the system: entiende, sabe, interpreta, juzga, decide, opina, razona, aprende de ti |
| H7 | Crosses the disclosure boundary: Convex, AI SDK, CRC, anchor, delta, VFS, table names, model slots, internal tags |
| H8 | Commercial fear framing |
| H9 | Attributes clinical responsibility to the system, or omits the professional's judgement where the sentence needs it |

### MEDIUM findings

| Code | Rule |
|---|---|
| M1 | Claim with no operational anchor (role, document, decision, failure mode) |
| M2 | Noun stacking / nominalisation chain |
| M3 | Paragraph that restates the previous one, or hedged non-claim |
| M4 | Second person: tú, usted, tu, tus, imperatives addressed to the reader |
| M5 | Corporate first person: nosotros, creemos, revisamos, hablemos |
| M6 | Product in the opening, in the close, or more than twice in the body (except nota de producto) |
| M7 | Banned lexicon: copiloto, asistente virtual, agente, cerebro clínico, segunda opinión |
| M8 | Corporate buzzword |
| M9 | Uncalibrated absolute: garantiza, elimina el error, siempre, cualquier pregunta |
| M10 | Word budget overrun, per piece or per section, beyond 15 % |
| M11 | Coined term used inconsistently, or a new coined term invented ad hoc |
| M12 | Closing with a CTA in a reflective archetype |
| M13 | Filler connective: por otro lado, en este sentido, cabe destacar, en definitiva |
| M14 | Unmarked anglicism where Spanish exists |

### LOW findings

| Code | Rule |
|---|---|
| L1 | Trailing period in a title or heading |
| L2 | Emoji |
| L3 | More than one em dash per paragraph, or em dash where parentheses fit |
| L4 | More than two lists per section, or a list replacing prose |
| L5 | More than one blockquote per piece |
| L6 | Heading depth beyond H3 outside marco/evidencia, or a section titled "Conclusión" |
| L7 | Number formatting not es-ES (thousands, decimals) |
| L8 | More than one image, or a keyword-list `alt` |
| L9 | `readTime` inconsistent with word count |
| L10 | Bold applied to a whole sentence, or more than once per paragraph |

---

## 2. Review mode output format

Diagnosis alone is not the deliverable. For every finding, quote the fragment verbatim and propose
the rewrite.

```
## Auditoría de voz — <pieza>

Arquetipo declarado: <marco | mecanismo | sector | evidencia | nota de producto>
Extensión: <N> palabras (presupuesto: <rango>)

| # | Fragmento | Código | Severidad | Reescritura propuesta |
|---|---|---|---|---|
| 1 | "..." | H7 | HIGH | "..." |
| 2 | "..." | M1 | MEDIUM | "..." |
| 3 | "..." | L1 | LOW | "..." |

**Veredicto:** <publicable | publicable con correcciones | reescritura>
```

Rules for the table:

- **Order by severity**, HIGH first. Within a severity, follow document order.
- **Quote verbatim**, trimmed to the offending clause. Do not paraphrase the "before".
- **Every row gets a rewrite.** "Eliminar" is a valid rewrite for filler. Say so explicitly.
- **One row per finding**, not per rule. A sentence with three defects gets three rows only if
  they need different rewrites; otherwise one row listing the codes.
- **Do not pad the table.** A clean piece with two LOW findings gets a two-row table and a
  *publicable* verdict.

### Verdict thresholds

| Verdict | Condition |
|---|---|
| **publicable** | No HIGH, at most two MEDIUM |
| **publicable con correcciones** | No HIGH, three or more MEDIUM, or any number of LOW |
| **reescritura** | Any HIGH, or MEDIUM findings that touch the thesis of the piece |

A HIGH finding always forces *reescritura*, even if it is a single word. That is the point of the
severity.

---

## 3. Pre-delivery checklist

Run in this order. Steps 1-4 are cheap and catch most of it.

### Mechanical pass

- [ ] No trailing period in H1, H2, H3, H4, card titles, hero headlines, metric labels
- [ ] No emojis
- [ ] Em dashes: at most one per paragraph; parentheses used for asides
- [ ] At most two lists per section; at most one blockquote per piece; at most one image
- [ ] Heading depth respects the archetype; no section titled "Conclusión" in reflective pieces
- [ ] Numbers in es-ES convention
- [ ] `excerpt` and, if overridden, `readTime` in the post frontmatter consistent with the piece

### Narrator pass

- [ ] Search the draft for `tú`, `tu `, `tus`, `usted`, `puedes`, `tienes`. Zero hits
- [ ] Search for `nosotros`, `creemos`, `revisamos`, `hablemos`, `nuestro`. Zero hits outside a
      nota de producto
- [ ] Product name appears zero times in the opening and the close, at most twice in the body
- [ ] Deleting every product mention leaves the piece standing

### Personification pass

- [ ] Search for `entiende`, `comprende`, `sabe`, `interpreta`, `juzga`, `decide`, `determina`,
      `opina`, `razona`, `aprende` with the system as subject. Zero hits
- [ ] Every decision in the text has a human or an organisation as its subject

### Red-line pass

- [ ] No sentence that states what should be done to a patient
- [ ] Every figure has its source and its context; technical signal labelled as such
- [ ] No certification, marking or conformity claimed
- [ ] No competitor, model or provider named
- [ ] Fear framing is clinical risk, never commercial pressure

### Disclosure pass

- [ ] Search for `Convex`, `AI SDK`, `CRC`, `checksum`, `anchor`, `delta`, `VFS`, `prompt`,
      `embedding`, `RAG`, `chunk`, `orquestador`, `sub-agente`, `tool`. Zero hits
- [ ] No sentence that only makes sense to someone who has read the repository

### Voice pass

- [ ] Archetype declared; word budget per section written down and respected
- [ ] Every claim has a role, document, decision or failure mode attached
- [ ] No paragraph restates the previous one; no hedged non-claims
- [ ] `de` count per sentence under three
- [ ] Limits stated where they exist; no absolutes
- [ ] One idea per sentence; paragraphs of 3-5 lines
- [ ] *el sistema ordena, el clínico decide* holds throughout
- [ ] Coined terms used consistently; no new ones invented
- [ ] Closing is reflective, no CTA (except nota de producto, one CTA)

---

## 4. Worked review

Input fragment (a draft hero for a product page):

> "Consensus Salutis es el copiloto clínico que entiende tus dudas y te da la respuesta correcta,
> reduciendo errores diagnósticos. Certificado para entornos sanitarios europeos."

Output:

```
## Auditoría de voz — hero de producto (borrador)

Arquetipo declarado: nota de producto
Extensión: 28 palabras (presupuesto: 500-800 para la pieza completa)

| # | Fragmento | Código | Severidad | Reescritura propuesta |
|---|---|---|---|---|
| 1 | "reduciendo errores diagnósticos" | H2, H3 | HIGH | Eliminar. Sin estudio citable no procede. Si hay que hablar de rendimiento: "el benchmark documentado se presenta como señal técnica contextualizada" |
| 2 | "Certificado para entornos sanitarios europeos." | H4 | HIGH | "Diseñado para operar en entornos sanitarios europeos: despliegue en la Unión Europea, auditoría completa y trazabilidad de acciones" |
| 3 | "entiende tus dudas" | H6, M4 | HIGH | "recupera el conocimiento relevante para la duda que formula el profesional" |
| 4 | "el copiloto clínico" | M7 | MEDIUM | "la capa de consulta clínica" |
| 5 | "te da la respuesta correcta" | M9, M4, H9 | HIGH | "devuelve una síntesis con la referencia al fragmento que la sustenta; la conclusión la sostiene el criterio profesional" |

**Veredicto:** reescritura

Propuesta completa:

"Consensus Salutis convierte guías, protocolos y documentación propia en una consulta clínica
trazable. Cada respuesta puede enlazar al fragmento original que la sustenta, y el criterio
profesional decide. Diseñado para operar en la Unión Europea, con auditoría completa e historial
de versiones."
```

Note what the review does: it names codes, it quotes verbatim, it rewrites every row, and it ends
with a full replacement because the verdict was *reescritura*. A verdict of *publicable con
correcciones* ends with the table only.
