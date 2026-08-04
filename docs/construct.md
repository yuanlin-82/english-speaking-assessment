# Constructs

## Main axis: how speaking evidence is elicited

Before naming report dimensions, fix the **elicitation family**. Measurement research does not crown a single best format; **task-based** and **interaction-based** batteries are both legitimate. Well-known admissions speaking exams are familiar *examples* of each family—not formal labels for them.

See [task-vs-interaction.md](task-vs-interaction.md) for the comparison, and for why **English-medium competency interviews** must not be collapsed into interaction-based oral testing.

This repo’s primary shipped path is **task-based** oral scoring.

---

## What we are trying to measure (task reports)

In hiring / interview products, “English speaking ability” is usually a **report construct**: something stakeholders can read next to job fit, not a full SLA or CEFR battery.

Coarse product axes often look like:

| Construct (product language) | Typical evidence | Ownership in this stack |
| --- | --- | --- |
| **Accuracy** (family) | Pronunciation / form / wording signals (may be split into finer indicators in detailed reports) | Often vendor score types + composition here |
| **Fluency** (family) | Speech rate, pauses, repair / hesitation; expert-aligned | **Self-built** evidence chain preferred when vendor “fluency” fails expert alignment |
| **Integrity / completeness** | Whether the response covers required content vs a reference or task demand | Often vendor or hybrid; **operational**, not CAF complexity |

Finer indicators (e.g. rate vs pause vs repair; lexical/grammatical richness) may roll into these axes. Public docs state the **families and ownership**, not production weights.

“Integrity” / content completeness means **task / content adequacy**, not moral integrity and not CAF **complexity**.

---

## CAF vs product dimensions

Applied linguistics often discusses **CAF**: complexity, accuracy, fluency. Large exams use related but different bundles (for example: pronunciation / lexis / grammar / fluency–coherence in one interview-style scale set; delivery / language use / topic development in another task-oriented set).

| CAF | Product report | Notes |
| --- | --- | --- |
| Accuracy | Accuracy family | Name-aligned; measurement may still be vendor-defined for some sub-scores. |
| Fluency | Fluency family | Intent-aligned; utterance features (rate / pause / repair) owned when needed. |
| Complexity | *(not always a primary report axis)* | Lexical / syntactic richness may appear as supporting indicators; product “integrity” is **not** a substitute for complexity. |
| — | Integrity / completeness | Operational: did the speaker meet the item’s content demand? |

Public stance: **integrity ≠ complexity**. Do not over-read a hiring oral report as a full CAF profile or as any branded exam scale. Band-style packaging is optional product copy, not the core claim of this methodology.

---

## Perceived vs utterance fluency

For fluency specifically (see [fluency.md](fluency.md)):

- **Perceived fluency** — what raters hear (smoothness, effort, naturalness).
- **Utterance fluency** — measurable temporal and repair features (rate, pause, self-repair, fillers).

The product goal is to approximate **perceived** fluency via an **utterance** evidence chain, then validate against expert ratings—not to publish a single vendor “fluency” float as truth.

---

## Related but different: competency in English

If the business question is “can this person do the job, discussing it in English?”, that is a **competency interview under an English medium**—see the special note in [task-vs-interaction.md](task-vs-interaction.md) and the companion [decision map](https://github.com/yuanlin-82/ai-interview-decision-map).
