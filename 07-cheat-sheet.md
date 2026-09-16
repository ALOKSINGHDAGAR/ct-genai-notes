# CT-GenAI — One-Page Cheat Sheet

> **Read this on the morning of 19 September.** Nothing else.

---

## Exam facts
**40 questions · 46 points · pass 30 (65%) · 60 min** (75 min with +25% language allowance)
**No negative marking — answer every question.**
K1 = 8 q (1 pt) · K2 = 26 q (1 pt) · **K3 = 6 q (2 pts each = 12 pts)**

**Points by chapter:** Ch1 = 7 · **Ch2 = 16** · **Ch3 = 11** · Ch4 = 5 · Ch5 = 7

---

## The 6 prompt components — R.C.I.I.C.O
**Role · Context · Instruction · Input data · Constraints · Output format**
*Instruction = what to do. Constraints = restrictions on how it's applied.*

## The 3 core techniques — and when to pick each

| Technique | Pick it when the scenario says… |
|---|---|
| **Prompt chaining** | complex · multi-step · **verify each step** · decompose · intermediate results |
| **Few-shot prompting** | **specific output format** · Gherkin / given-when-then · keyword-driven · repetitive pattern |
| **Meta prompting** | **unsure how to write the prompt** · new task · optimize prompt · **test report analysis · anomaly detection** |

**Examples count:** zero-shot = **0** · one-shot = **1** · few-shot = **>1**
**They can be combined:** meta → few-shot → chaining.

## System vs user prompt
**System** = hidden, set once by developer/tester, constant, holds **role + context + constraints**.
**User** = visible, changes every turn, holds **instruction + output format**.

---

## The 7 evaluation metrics — A.P.R.R.D.E.T
**Accuracy** (overall correctness vs a standard) · **Precision** (correct for a *specific objective*) ·
**Recall** (finds *all* relevant instances) · **Relevance & Contextual Fit** · **Diversity** ·
**Execution Success Rate** (runs without syntax errors) · **Time Efficiency**

⚠️ **Metrics must be based on statistically relevant data** — because GenAI is non-deterministic.

## The 5 prompt-refinement techniques
Iterative modification · **A/B testing** · Output analysis · Integrate user feedback ·
**Adjust length and specificity** *(shorter is sometimes better!)*

---

## The 3 defect types
| | Cause | Detect by |
|---|---|---|
| **Hallucination** = INVENTED | Statistically plausible ≠ correct | **Cross-verification · domain expert · consistency checks** |
| **Reasoning error** = ILLOGICAL | **Pattern matching, not true reasoning** | **Logical validation · output testing** |
| **Bias** = SKEWED | **Training data** | Review vs **test strategy & coverage requirements** |

## Mitigating non-determinism
**Lower temperature** (⚠️ costs creativity/diversity) · **set random seeds**
⚠️ **Complete reproducibility cannot be guaranteed.**

## The 4 attack vectors
**Context manipulation** = overload context window → **extract training data**
**Request manipulation** = corrupt input → disrupt output
**Data poisoning** = corrupt **training data**
**Malicious code generation** = LLM writes a **backdoor**

## The 4 regulations/standards/frameworks
**ISO/IEC 42001:2023** = *Standard* — AI **management system**
**ISO/IEC 23053:2022** = *Standard* — AI **lifecycle, ML**, safety & transparency
**EU AI Act** = ***Regulation*** — classifies by **risk level**
**NIST AI RMF** = ***Framework*** (US) — **fairness**, transparency, security

## Energy
**Image generation ≈ fully charging a smartphone. Text ≈ a small % of a charge.**
Drivers: **task complexity + computational resources**. Mitigate: **limit unnecessary interactions**.

---

## Chapter 4 — RAG vs Fine-tuning
| | **RAG** | **Fine-tuning** |
|---|---|---|
| Weights | **Unchanged** | **Updated** (supervised, labeled examples) |
| Knowledge | **Retrieved at runtime** | **Baked in at training** |
| Best for | **Latest enterprise specs/requirements/test data** | **Org-specific format, vocabulary, specialized reasoning** |

**RAG = 2 steps: Retrieval → Generation.** Chunks = **256–512 tokens**. Stored in a **vector database**.

**Agent vs chatbot:** the **agent ACTS by invoking tools**. Chatbot only answers.
**Critical task → semi-autonomous agent** (periodic human oversight).
**Multi-agent coordination = orchestration.**

**Fine-tuning challenges — B.O.O.C:** Bias · **Overfitting** · **Opacity** · Computational cost

**Architecture:** Front-end → Back-end (auth, retrieval, prompt prep, **post-processing**) → LLM.
**Relational DB = structured test data. Vector DB = semantic retrieval.**

**3 LLMOps approaches:** AI chatbot · test tool with GenAI · in-house development.
⚠️ **Not mutually exclusive.**

---

## Chapter 5 — cheap recall marks
**Shadow AI** = used **without formal approval or oversight**.
Risks — **S.C.I**: **Security/privacy · Compliance · Intellectual property**.
Cure = **a strategy and roadmap** (not a ban).

**3 adoption phases — D.I.U:** **Discovery** (awareness, training, experiment) →
**Initiation and usage definition** (identify & prioritize use cases) →
**Utilization and iteration** (full integration, continuous monitoring).
⚠️ **Can run in parallel for different use cases.**
⚠️ **Address fear of job displacement early.**

**4 LLM/SLM selection criteria — P.F.C.C:** **Performance · Fine-tuning potential · Cost · Community/support**
⚠️ **Few benchmarks target software test tasks specifically.**

**Prompt pattern** = **reusable template** for effective prompts.
**Data sanitization** = removing/masking sensitive, personal or confidential information.

**Tester evolves to:** AI-assisted test specialist → **review AI output · refine prompts · maintain prompt libraries**
**Test manager:** **AI-based test strategy · AI-based risk management · monitoring & control of AI-based test processes**
→ leads **hybrid teams of people and GenAI agents**.

---

## 🚨 The 10 "always wrong" answer patterns

1. Anything saying GenAI output **does not need verification**.
2. **"Always" / "never" / "guarantees" / "eliminates"** — GenAI is probabilistic.
3. **"A larger context window is always better."** (Costs complexity and time.)
4. **"Longer prompts are always better."** (Sometimes shorter generalizes better.)
5. **"Lower temperature eliminates hallucinations."** (It reduces *variability* only.)
6. **"Complete reproducibility can be achieved."** (It cannot.)
7. **"GDPR prohibits GenAI in testing."** (It provides safeguards, not a ban.)
8. **"Testers no longer need traditional testing skills."** (They combine both.)
9. **"An organization must choose one LLMOps approach."** (Not mutually exclusive.)
10. **"Adoption phases must complete sequentially."** (They can run in parallel.)

---

## ⏱️ Exam-day timing plan

| Phase | Time | What |
|---|---|---|
| Pass 1 | ~35 min | Answer all **K1/K2** questions (34 of them) at ~60 s each. Flag anything slow. |
| Pass 2 | ~18 min | The **6 K3 scenario questions** at ~3 min each — these are worth **12 points**. |
| Pass 3 | ~7 min | Review flagged questions. **Ensure nothing is blank.** |

**On a K3 question:** identify the *test activity* (analysis / design / regression / monitoring),
then identify the *trigger words*, then match to the technique table above.

**Good luck — you only need 30 of 46.**
