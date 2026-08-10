# Stimulus and material selection (item bank)

How **source materials** are chosen for task-based oral items in an AI interview setting—not a dump of stems, audio, or video assets.

Pairs with [task-design.md](task-design.md) (what each item type is for) and [stimulus-packaging.md](stimulus-packaging.md) (how image + audio become the playable attachment).

---

## Why selection standards matter

Oral scores are only as fair as the stimuli. In hiring, bad materials commonly fail in three ways:

1. **Construct noise** — topic or wording loads culture, specialty knowledge, or reading load more than speaking fluency / coverage.  
2. **Non-comparable difficulty** — one stem in a type is much harder than peers, so composition is dominated by item luck.  
3. **Wrong job relevance** — classroom literature or trivia that does not resemble workplace English use.

Selection rules below are methodology shape for interview oral tasks (workplace-general scenes → constrained nonfiction materials → format-controlled difficulty). Exact cut tables and production stems stay private.

---

## Step 1 — Scenario filter (what situations to elicit)

Workplace oral needs map to a small set of **cross-industry** scene types (illustrative): presentation-like delivery, repeating key information, relaying instructions or opinions, summarizing points, stating a view.

**Keep a scene when it tends to be:**

| Criterion | Intent |
| --- | --- |
| **Cross-industry / general workplace** | Usable across sectors—not one niche only |
| **Hiring-relevant** | Tied to how English is actually used in early screening |
| **Not trivially replaceable by tools** | Still requires spoken performance |

**Drop or avoid:**

| Exclude | Why |
| --- | --- |
| **Domain-specific** oral banks as the default | Fairness across majors / industries collapses |
| **Fully tool-substitutable** tasks | Weak claim that the score reflects candidate speaking |
| **Obscure / niche topics** | Add construct-irrelevant difficulty without hiring value |

**Industry-specific English:** this oral module stays on **general workplace** materials. When a client needs sector English (finance jargon, clinical terms, …), product guidance is to use **English as the interview language for competency probing**—not to force a specialty oral battery into the task-based scorer. See [task-vs-interaction.md](task-vs-interaction.md).

Scene types then map onto item forms (read-aloud, listen–repeat, paraphrase, listen–answer, content expression)—see [task-design.md](task-design.md).

---

## Step 2 — Text / topic material standards

1. **Nonfiction workplace-adjacent content** — prefer expository / informational text over literary prose.  
2. **Difficulty matching via format controls** (primary operational lever for parallel items): target **text length**, **vocabulary band**, and **sentence patterns** within a type so stems stay roughly comparable. Readability indices / CEFR-aware lexicon checks support that gate; they do not replace format specs.  
3. **Vocabulary load** — prefer common workplace lexicon; avoid obscure material rather than maintaining a phoneme-avoidance checklist for vendors.  
4. **One primary speaking job** — material must fit the item type’s evidence lean.  
5. **Bounded answer space where automation needs it** — especially content completeness ([content-completeness.md](content-completeness.md)).  
6. **Minimize construct-irrelevant hooks** — contested politics, in-group slang, needless proper-noun piles.

No dedicated “avoid this phoneme / proper name for the speech vendor” policy beyond ordinary common-sense topic choice.

---

## Step 3 — Audio stimulus policy

Listening-side stems (listen–repeat, paraphrase, listen–answer, …) use **TTS-synthesized** audio in product practice:

| Parameter | Public shape |
| --- | --- |
| Voice | American English (US) orientation |
| Rate | Slightly slowed (about **0.9×**) for clarity in remote capture |

Human studio talent is not required for the default bank. Packaging still image + this audio into the playable file: [stimulus-packaging.md](stimulus-packaging.md).

---

## Step 4 — Presentation constraints

- A **static scene image** frames the situation; it is not a motion video narrative.  
- Keep scorable text/audio targets salient; prefer ASR-tolerant wording.  
- Quiet-room / device checks before capture still matter ([failure-case-pronunciation-accent-channel.md](failure-case-pronunciation-accent-channel.md)).

---

## Sampling, customization, and honesty about brief forms

| Practice | Shape |
| --- | --- |
| **Live draw** | Items are drawn from a typed pool (illustratively: on the order of **tens of items → a few administered**, e.g. ~50 → 3 in one brief configuration). Exact pool sizes stay private. Repeat risk is reduced by pool size, not claimed zero. |
| **Customization** | Special client needs → **new stems** under the same selection gates—not silent reuse of mismatched industry copy inside the oral scorer. |
| **Brief battery = screen, not a high-stakes oral exam** | A handful of short tasks under hiring price and remote conditions is **coarse**. Education-sector oral exams usually cost more and control environment far more tightly. Treat AI-interview oral scores as **early filter evidence**, not a full proficiency certificate. How to get faster, cheaper, *and* accurate oral decisions under those constraints remains an open product tension—not solved by pretending three clips equal a lab exam. |

Equivalence of random three-item draws is **not** fully validated as a psychometric claim here; format controls + pool hygiene are the practical mitigations.

---

## Bank hygiene

| Practice | Why |
| --- | --- |
| **Format-matched parallels within type** | Length / vocab / syntax gates for reuse |
| **Review before ship** | Scenario fit, difficulty band, bias / obscurity scan |
| **Separate competency dialogue banks** | Oral task stems ≠ English-medium competency stems |

---

## What this page does not publish

Production stems, JPG/MP3/MP4 files, pool IDs, exact Lexile/CEFR cut tables, and TTS vendor accounts. See [NOTICE.md](../NOTICE.md).

---

## One-line takeaway

> Prefer **general workplace** scenes and **format-controlled** nonfiction materials; package clear TTS audio with a scene still; treat short AI-interview oral batteries as **screening**, and send true industry-English needs to **competency-in-English** interviewing.
