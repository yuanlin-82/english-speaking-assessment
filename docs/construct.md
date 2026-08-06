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
| **Pronunciation accuracy** | How clearly / accurately speech matches expected pronunciation targets | Often vendor score type; composed here |
| **Fluency** (family) | Speech rate, pauses, repair / hesitation; expert-aligned | **Self-built** evidence chain preferred when vendor “fluency” fails expert alignment |
| **Content completeness** | Whether the response covers required content vs a reference or task demand | Often vendor or hybrid; **operational**, not CAF complexity |

Finer indicators (e.g. rate vs pause vs repair; lexical/grammatical form or richness) may appear in detailed reports. Public docs state the **coarse axes and ownership**, not production weights.

**Content completeness** means task / information coverage—not “integrity” in the moral sense, and not CAF **complexity**. It is an **automation compromise**: open depth is hard to auto-score; large exams still use examiners for depth-like judgments; fully auto batteries constrain answer freedom—see [content-completeness.md](content-completeness.md).

Avoid bare labels **Accuracy** / **Integrity** on stakeholder reports: they overclaim or misread easily.

---

## CAF vs product dimensions

Applied linguistics often discusses **CAF**: complexity, accuracy, fluency. Large exams use related but different bundles (for example: pronunciation / lexis / grammar / fluency–coherence in one interview-style scale set; delivery / language use / topic development in another task-oriented set).

| CAF | Product report | Notes |
| --- | --- | --- |
| Accuracy (broad: form) | **Pronunciation accuracy** (narrower) | Product coarse axis emphasizes pronunciation; other form scores (lexis/grammar) may exist as fine indicators, not this label. |
| Fluency | Fluency family | Intent-aligned; utterance features (rate / pause / repair) owned when needed. |
| Complexity | *(not always a primary report axis)* | Lexical / syntactic richness may appear as supporting indicators; **content completeness** is **not** a substitute for complexity. |
| — | **Content completeness** | Operational: did the speaker meet the item’s content demand? |

Public stance: **content completeness ≠ complexity**. Do not over-read a hiring oral report as a full CAF profile or as any branded exam scale. Band-style packaging is optional product copy, not the core claim of this methodology.

**Pronunciation accuracy** is especially easy for non-specialist HR to hear as “sounds like British/American movie speech” or simply “not Chinese-accented.” That folk reading collides with reference-accent and **channel** effects—see [failure-case-pronunciation-accent-channel.md](failure-case-pronunciation-accent-channel.md).

---

## Perceived vs utterance fluency

For fluency specifically (see [fluency.md](fluency.md)):

- **Perceived fluency** — what raters hear (smoothness, effort, naturalness).
- **Utterance fluency** — measurable temporal and repair features (rate, pause, self-repair, fillers).

The product goal is to approximate **perceived** fluency via an **utterance** evidence chain, then validate against expert ratings—not to publish a single vendor “fluency” float as truth.

---

## Related but different: competency in English

If the business question is “can this person do the job, discussing it in English?”, that is a **competency interview under an English medium**—see the special note in [task-vs-interaction.md](task-vs-interaction.md) and the companion [decision map](https://github.com/yuanlin-82/ai-interview-decision-map).
