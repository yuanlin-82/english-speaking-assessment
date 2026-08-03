# Constructs

## What we are trying to measure

In hiring / interview products, “English speaking ability” is usually a **report construct**: something stakeholders can read next to job fit, not a full SLA or CEFR battery.

This workstream separates:

| Construct (product language) | Typical evidence | Ownership in this stack |
| --- | --- | --- |
| **Accuracy** | Pronunciation / form correctness signals from speech scoring | Vendor score type; composed here |
| **Fluency** | Speech rate, pauses, repair / hesitation phenomena; expert-aligned | **Self-built** evidence + models |
| **Integrity** | Whether the response completes the communicative task / covers required content | Vendor (or hybrid) score type; composed here |

“Integrity” here means **task / content adequacy**, not moral integrity and not CAF **complexity**.

---

## CAF vs product dimensions

Applied linguistics often discusses **CAF**: complexity, accuracy, fluency.

| CAF | Product report | Notes |
| --- | --- | --- |
| Accuracy | Accuracy | Roughly aligned in name; measurement is still vendor-defined. |
| Fluency | Fluency | Aligned in intent; **implementation is owned** because vendor fluency did not track expert ratings well enough for this use case. |
| Complexity | *(not a primary report axis)* | Lexical / syntactic complexity may appear in research or supporting features; product “integrity” is **not** a substitute for complexity. |
| — | Integrity | Operational: did the speaker do the task? Useful for short interview clips; theoretically different from CAF. |

Public stance: be explicit that **integrity ≠ complexity**, so readers do not over-read the report as a full CAF profile.

---

## Perceived vs utterance fluency

For fluency specifically (see [fluency.md](fluency.md)):

- **Perceived fluency** — what raters hear (smoothness, effort, naturalness).
- **Utterance fluency** — measurable temporal and repair features (rate, pause, self-repair, fillers).

The product goal is to approximate **perceived** fluency via an **utterance** evidence chain, then validate against expert ratings—not to publish a single vendor “fluency” float as truth.
