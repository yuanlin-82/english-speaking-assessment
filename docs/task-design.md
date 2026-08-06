# Task design (interview-oriented)

Speaking items are designed so each type **elicits a different evidence profile**—closer to evidence-centered design (ECD) than to “random oral drills.”

Illustrative item types used in this product family (names are descriptive; production titles may differ):

| Type | Rough job | Primary evidence lean |
| --- | --- | --- |
| **Read-aloud** | Controlled production from text | Pronunciation accuracy under known target; limited content freedom |
| **Listen–repeat** | Immediate imitation | Pronunciation accuracy + short-span fluency under memory load |
| **Paraphrase** | Reformulate heard / given meaning | Content completeness of meaning + productive fluency under rewording |
| **Listen–answer** | Comprehend then respond | Content completeness / answer relevance; fluency under Q&A pressure |
| **Content expression** | Open / semi-open speaking on a prompt | Content completeness of coverage; fluency under planning load |

Counts per type and which types appear in **brief** vs **detailed** reports are product policy (see [score-composition.md](score-composition.md)). Exact stems and audio assets are omitted.

Answer freedom is **bounded on purpose**: automated **content completeness** needs scorable targets or constrained meaning spaces. Fully open depth / complexity stays largely with human examiners in large oral exams—see [content-completeness.md](content-completeness.md).

---

## Design principles (public)

1. **One primary job per item** — do not ask one clip to prove every construct.
2. **Interview relevance** — prompts should feel like workplace / interview communication, not pure classroom drills, where the product allows.
3. **Comparable difficulty within type** — so composition across items is not dominated by a single outlier stem.
4. **Separate dialogue routing from oral scoring** — multi-turn **competency** interview follow-ups (including English-track) live in [ai-interview-decision-map](https://github.com/yuanlin-82/ai-interview-decision-map). Those turns look like “English dialogue” but target **job evidence**, not language performance under an interaction-based oral-proficiency model. See [task-vs-interaction.md](task-vs-interaction.md).

---

## What task design does *not* fix

Bad stems cannot be rescued by fancy composition. Conversely, good stems still need:

- reliable ASR / segmentation for fluency features,
- honest vendor score interpretation,
- missing-item and short-speech policies.

Those are scoring-contract concerns, not ECD alone.
