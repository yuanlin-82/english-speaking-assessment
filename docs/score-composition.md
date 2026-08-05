# Score composition (contract shape)

This document describes **how report scores are assembled**, not vendor measurement internals and not production coefficients.

---

## Two report modes (illustrative)

| Mode | Item coverage | Report grain |
| --- | --- | --- |
| **Brief** | Subset of item types (e.g. three of five) | Coarser dimensions (e.g. pronunciation accuracy / fluency / content completeness) |
| **Detailed** | Full type set | Finer sub-dimensions rolled into the same parent constructs |

Exact type counts, which types enter brief mode, and numeric weights are **product configuration**—omitted here.

---

## Ownership of inputs

| Input | Source | Public stance |
| --- | --- | --- |
| Pronunciation-accuracy scores | Speech scoring vendor | Use as typed inputs; do not reverse-engineer the vendor |
| Content-completeness scores | Vendor and/or task-specific rules | Same |
| Fluency | In-house chain ([fluency.md](fluency.md)) | Authoritative for the fluency axis in this stack |
| Per-type coefficients | Product policy | Shape: types can weight differently; values private |
| Missing-item policy | Product policy | Shape: unanswered items should shrink confidence or total via a **documented rule** (e.g. answered/expected scaling)—exact exponents private |

---

## Composition principles (safe to say publicly)

1. **Typed inputs** — do not average incompatible vendor floats without naming the construct.
2. **Fluency override** — if vendor exposes a fluency field, do not let it silently replace the in-house fluency axis.
3. **Missingness is first-class** — a high score on two of five items is not the same as a complete battery; composition should reflect coverage.
4. **Brief ≠ detailed with dropped rows** — brief mode is a deliberate subset of tasks and often coarser aggregation, not “hide three columns.”
5. **No CEFR / IELTS claim by default** — any band mapping is optional product packaging and easily oversold; this repo does not treat band tables as core methodology.

---

## What content completeness contributes in composition

**Content completeness** answers: *did this response satisfy the communicative / informational demand of the item?*  
That can dominate open tasks (paraphrase, listen–answer, content expression) and matter less for pure read-aloud—type coefficients exist partly for that reason.

---

## Link to dialogue products

Oral scores here are **ability evidence**. Whether the interview continues, stops follow-ups, or jumps items is a **routing** problem—documented separately in [ai-interview-decision-map](https://github.com/yuanlin-82/ai-interview-decision-map). Do not mix “fluency too low → ask another probe” into this composition doc unless a product explicitly wires them (and then document the wire as product policy, not as psychometrics).
