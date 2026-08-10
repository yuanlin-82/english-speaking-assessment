# Task-based vs interaction-based speaking assessment

There is **no settled verdict** in language assessment that interactive dialogue is always better than constrained tasks (or the reverse). Formal categories here are **elicitation families**, not exam brands.

| Family (formal) | How evidence is elicited | Trade-offs |
| --- | --- | --- |
| **Task-based** (often semi-direct) | Fixed prompts / input materials → timed responses (often to a recorder or system) | Stronger standardization and scalable automated scoring; weaker live interactional authenticity |
| **Interaction-based** (interview / examiner-mediated) | Examiner (human or system) turns, follow-ups, topic push | Higher interactional authenticity; examiner effects, unequal probing, harder automation |

Familiar large-scale exams are only **illustrations**, not definitions of the categories—for example, many readers associate machine-delivered speaking *tasks* with one well-known admissions test family, and face-to-face *speaking interviews* with another. Real exams mix formats internally; do not treat brand names as taxonomy.

Neither family “wins.” Choice follows **construct**, **use**, and **operational constraints** (standardization, cost, ASR quality, need for adaptive pressure).

---

## What this repo’s shipped path is

The methodology documented here is primarily **task-based**: controlled item types (read-aloud, listen–repeat, paraphrase, listen–answer, content expression) → multi-indicator scores → report composition.

An **interaction-based oral proficiency** path (examiner-style turns aimed at language ability) is **theoretically coherent** but **not** shipped here as an assessment product—see [interactive oral](#interactive-oral-theoretically-sound-hard-to-ship-as-assessment) below.

---

## Interactive oral: theoretically sound, hard to ship as assessment

For **interaction-based measurement of oral ability** (not competency-in-English interviewing), a trained examiner does roughly this:

1. While listening, **decode the speech** and **update a running judgment of oral level**—largely in parallel, not as two offline stages.  
2. Choose the **next probe** so its **cognitive–linguistic demand** fits that running judgment (stretch, scaffold, or hold).  
3. Treat probing as **measurement**, not chat: suitable questions are how the examiner **approaches the candidate’s true level**.

**Product premise (author stance).**  
If a “conversational oral test” **cannot** implement assess-while-probing—i.e. cannot control next-probe **demand** from the previous turn’s oral performance—it does **not** meet the precondition for selling that dialogue as an **oral-ability assessment**. Looking like an interview is not enough. Task-based batteries remain **logically coherent** under a different contract: fixed / semi-fixed tasks → scores, without claiming examiner-style demand adaptation inside chat.

Under the interactive construct, follow-ups that never adjust demand are not merely “less natural.” They fail the measurement logic: the dialogue can **look** like an oral interview while **not** tracking ability the way adaptive human examining does.

**Theory (why it is feasible in principle).**  
Interactive / interviewer-mediated speaking assessment and adaptive language testing both assume that **elicitation demand** should respond to emerging evidence of ability. Human examiners implement a compressed, online version of that idea (“human IRT”-like behavior): estimate and choose the next demand together.

**Technology (why live stacks struggle—and what is *not* claimed).**  
Typical voice pipelines wait for **ASR finalization** (or a late stable hypothesis) before “understanding” and generation. Human examining does **not** wait for a full transcript to start judging. On top of that, the hot path must, within roughly **sub-second** budgets suitable for TTS dialogue:

- update a **reversible** view of the last turn’s oral performance, and  
- select or constrain the **next probe’s demand**, and  
- emit one **speakable** interviewer utterance.

Those steps contend with the same latency envelope as stop brakes and follow-up generation.

This is **not** a claim that LLMs are incapable of *wording* easier or harder follow-ups. Models can be prompted or cascaded to change surface demand. The open issue is whether that yields **assessment-grade** control: stable direction, reversible updates, path-comparable scores, under ASR timing and live UX—not merely fluent chat. Stronger LLMs alone do not remove the **ordering problem** (assessment gated on ASR) or the **joint real-time demand-control** problem. This repo does not report a definitive experiment; it records the product bar and the engineering bind.

**Boundaries (what this section does *not* say).**

- It does **not** claim task-based oral batteries are invalid—they use a **different** elicitation contract.  
- It does **not** require competency follow-ups to adapt **language demand**; those turns optimize **job-evidence gaps** ([ai-interview-decision-map](https://github.com/yuanlin-82/ai-interview-decision-map)).  
- It does **not** ship an interactive oral engine here—only names why that path is parked as a **measurement product**.

---

## Stakeholder frictions (HR and “good enough”)

### “It chats, so it must be like a speaking exam”

Non-measurement stakeholders often use a short heuristic: *if the AI follows up coherently, it feels like a face-to-face oral exam—so it must be measuring speaking.* Market products that **look** conversational amplify that heuristic.

Useful pushback without jargon:

- Coherent chat shows **interaction skill of the system**, not automatic **oral-ability measurement**.  
- Examiner-mediated oral tests hitch value to **demand that moves with performance**. Many LLM demos optimize for continuity and helpfulness, which can work against controlled elicitation.  
- Relaxing the brand (“we don’t need to match a famous exam”) does **not** relax the physics of assessment: if scores still rank candidates, “roughly like dialogue testing” is not a cheaper measurement design—it is often a **vaguer claim with the same hard requirements**.

### Task-based scores vs free conversation in a live recap

Task-based paths have a **real** stakeholder pain: a candidate may do well on scaffolded tasks yet struggle in open English chat with an English-speaking interviewer who does not think in constructs. That interviewer may conclude “they can’t speak,” and treat the machine score as wrong.

Both sides can be locally true:

| Setting | What is being sampled |
| --- | --- |
| Task battery | Production under **standard stimuli** and time boxes |
| Free recap chat | Production under **social pressure**, topic shifts, and little scaffolding |

Related ≠ identical. Do not use unstructured chat as the sole acceptance test of task scores—or use task scores to guarantee polished small talk. If the hiring process cares about unscaffolded dialogue, add an explicit **conversation observation** step (human or separate module) instead of forcing one number to mean both.

---

## Special note: English-medium competency interviews

Stakeholders (especially HR) often label all of the following as “English interview”:

1. Task-based oral scoring  
2. Interaction-based **oral proficiency** testing (probes aimed at language performance)  
3. **Competency / job interviews conducted in English** (probes aimed at work evidence; English is the medium)

**(2) and (3) are especially easy to confuse** because both look like multi-turn English dialogue.

| | Interaction-based **oral** test | English-medium **competency** interview |
| --- | --- | --- |
| **Target construct** | Language ability (delivery, range, fluency under interactive load, …) | Job-related competencies / behavioral evidence |
| **Why follow up** | Elicit more **language evidence** (stretch, scaffold, check authenticity of polished speech) | Close **evidence gaps** (STAR holes, contradictions, weak examples) |
| **What “good answer” means** | Extended, clear, appropriate English performance | Relevant, specific proof of capability—even if wording is plain |
| **Failure mode if mixed** | Treat thin content as “low English,” or fluent emptiness as “strong hire signal” | Same confusion in reverse |

**Rule of thumb:** oral ability is more **foundational**; competency shown *in English* is closer to **oral accessibility × competency evidence quality**. A fluency breakdown can cap how much competency evidence you can observe; fluent speech does not create competency.

**Product routing for “industry English”:** keep the task-based oral bank on **general workplace** materials. When a client needs sector language (jargon-heavy finance, clinical, …), prefer **competency interviewing in English** over stuffing specialty passages into the oral scorer ([stimulus-selection.md](stimulus-selection.md)).

Routing contracts for competency-style follow-ups (including English-track locale constraints) live in:

- [ai-interview-decision-map](https://github.com/yuanlin-82/ai-interview-decision-map)

Do not read that repo as an oral-proficiency examiner engine, and do not read this repo’s task scores as competency grades.

---

## Same LLM follow-ups, different evidence gaps

A fair question: *if both pipelines use an LLM to generate the next probe, why can competency follow-ups collect job evidence while “oral” follow-ups are held to a stricter bar?*

**Shared shape.** Both can be described as **closing evidence gaps** after a turn: current evidence is not enough for the decision the product claims to make, so the next ask should target what is missing—not small talk.

**Different gaps.**

| | Competency follow-up | Interactive oral-ability follow-up |
| --- | --- | --- |
| **Gap type** | Empty **job-evidence cells** (e.g. action, result, personal contribution, decision criteria) | Insufficient information for an **oral-level judgment**, or the current **elicitation demand** fails to yield usable language samples |
| **What the next probe usually changes** | *Which content* to dig | Often the **cognitive–linguistic demand** of the ask (stretch / scaffold / hold)—not only a finer content slot |
| **“Gap closed” looks like** | The episode / reasoning is scorable for hiring | Performance under an appropriate demand supports estimating oral ability |

So it is not that LLM follow-ups “work for competency but cannot produce any language evidence.” Speech always leaves raw traces. The issue is whether unconstrained, demand-uncontrolled chat yields **assessment-grade** oral measurement. Competency probing is not magic either: without a typed strategy contract, LLMs also fail to close job-evidence gaps—that is what the [decision-map](https://github.com/yuanlin-82/ai-interview-decision-map) is for.

**Finer, but not only finer.** Oral probes are often more sensitive to wording and demand. That is only half the story: the gap is frequently a **demand / information** gap for ability estimation, not merely a higher-resolution version of STAR cells.

**One line for stakeholders.**  
Competency follow-ups close **job-evidence** gaps; interactive oral follow-ups (when sold as ability measurement) must close **ability-evidence** gaps—commonly by adjusting next-probe **demand**. Same generator family, different contracts.

**Language’s role (without a philosophy-of-mind claim).**  
In competency interviews, language is mainly a **channel / means**: it carries experiences and judgments so assessors can score **job evidence**—English is not the construct being graded. In oral-ability assessment, language performance is the **object / end**: scores target speaking dimensions (e.g. pronunciation, fluency, coverage). Poor English in a competency interview often shows up as **harder-to-harvest evidence**; in an oral test it *is* the signal under measure. This is a product and measurement distinction, not a claim that “language is the vehicle of thought.”

---

## One-line stakeholder framing

**Tasks** ask: *under standard stimuli, what English can this person produce?*  
**Interaction-based oral tests** ask: *under interactive pressure, does that English hold?*  
**English competency interviews** ask: *using English as the channel, what job-relevant evidence do we get?*
