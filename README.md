# ISTQB CT-GenAI — Complete Beginner's Study Pack

**Certified Tester Specialist Level — Testing with Generative AI (CT-GenAI), Syllabus v1.1**

> Your exam: **19 September**. These notes are built directly from the official ISTQB CT-GenAI
> Syllabus v1.1 (released 27/04/2026) and the official *Exam Structures & Rules* v1.19 blueprint.

---

## 1. The exam, in hard numbers

| Item | Value |
|---|---|
| Questions | **40** |
| Total points | **46** (not 40 — some questions are worth 2) |
| Pass mark | **30 / 46 = 65%** |
| Duration | **60 minutes** (**75 minutes** if English is not your native language — *claim this*) |
| Question types | Multiple choice, K1 / K2 / K3 |
| Prerequisite | **ISTQB CTFL (Foundation Level)** must already be held |
| Negative marking | **None** — never leave a blank |

### K-levels and what they cost you

| K-level | Questions | Points each | Total points | Time each |
|---|---|---|---|---|
| K1 (Remember) | 8 | 1 | 8 | ~1 min |
| K2 (Understand) | 26 | 1 | 26 | ~1 min |
| K3 (Apply) | **6** | **2** | **12** | ~3 min |
| **Total** | **40** | — | **46** | ~52 min |

**Read that again:** 6 questions carry 12 of the 46 points. K3 questions are scenario-based
("here is a test task — which technique applies?"). Getting all 6 K3 right is worth more than
getting all 8 K1 right.

---

## 2. THE MOST IMPORTANT TABLE IN THIS PACK

Official per-chapter distribution from the ISTQB Exam Structures & Rules document:

| Chapter | Topic | Questions | K1 | K2 | K3 | **Points** | % of exam |
|---|---|---|---|---|---|---|---|
| 1 | Introduction to GenAI for Software Testing | 7 | 1 | 6 | 0 | **7** | 15% |
| 2 | **Prompt Engineering for Effective Software Testing** | 11 | 0 | 6 | **5** | **16** | **35%** |
| 3 | **Managing Risks of GenAI in Software Testing** | 10 | 3 | 6 | 1 | **11** | **24%** |
| 4 | LLM-Powered Test Infrastructure | 5 | 0 | 5 | 0 | **5** | 11% |
| 5 | Deploying and Integrating GenAI in Test Organizations | 7 | 4 | 3 | 0 | **7** | 15% |
| | **TOTAL** | **40** | **8** | **26** | **6** | **46** | 100% |

### What this means for a beginner with 3 days

- **Chapter 2 + Chapter 3 = 27 of 46 points (59%).** The pass mark is 30.
  If you master Chapters 2 and 3 and then pick up just 3 more points anywhere else, you pass.
- **Chapter 2 holds 5 of the 6 K3 questions** (all in section 2.2). These are the
  "apply a prompting technique to a test task" questions. This is the single highest-value
  area in the whole exam.
- **Chapter 4 is only 5 points and is all K2.** Don't over-invest here. It is pure
  understanding — RAG, agents, fine-tuning, LLMOps. Read it twice, move on.
- **Chapter 5 is 4 K1 + 3 K2.** More than half of Chapter 5 is pure recall — cheap points.
  Memorise the lists and you bank 7 points quickly.

---

## 3. Your 3-day plan (16 → 19 September)

### Day 1 — Foundations + the big one
| Time | What |
|---|---|
| 1.0 h | `01-chapter-1-genai-foundations.md` — read + do the self-check |
| 2.0 h | `02-chapter-2-prompt-engineering.md` — sections 2.1 and 2.2 |
| 0.5 h | Memorise the **6 prompt components** and the **3 core techniques** cold |

### Day 2 — Highest-value material
| Time | What |
|---|---|
| 1.0 h | `02-chapter-2-prompt-engineering.md` — section 2.3 + re-do the 2.2.5 selection table |
| 1.5 h | `03-chapter-3-managing-risks.md` — full read |
| 0.5 h | `06-glossary.md` — first pass on all terms |
| 0.5 h | `08-practice-questions.md` — attempt Chapters 1–3 questions |

### Day 3 — Sweep up + revise
| Time | What |
|---|---|
| 0.75 h | `04-chapter-4-llm-infrastructure.md` |
| 0.75 h | `05-chapter-5-deploying-genai.md` (heavy recall — use the lists) |
| 0.5 h | `06-glossary.md` — second pass, self-test |
| 1.0 h | `08-practice-questions.md` — full set, then review every wrong answer |
| 0.5 h | `07-cheat-sheet.md` — final morning read |

---

## 4. How ISTQB writes questions (exam technique)

1. **Keywords are directly examinable.** The syllabus says every term listed under a chapter
   heading "shall be remembered, even if not explicitly mentioned in the learning objectives."
   That is what most of the 8 K1 questions test. `06-glossary.md` covers all of them.
2. **The K-verb tells you the question depth.** "Recall" → a definition question.
   "Explain"/"Summarize"/"Compare"/"Give examples" → K2, a scenario with distractors.
   "Apply"/"Practice"/"Select" → K3, a full scenario you must reason about.
3. **Distractors are usually true statements that don't answer the question asked.**
   Re-read the stem before choosing. Ask: *what is actually being asked?*
4. **Beware absolutes.** Options containing "always", "never", "guarantees", "eliminates"
   are almost always wrong for GenAI. GenAI is probabilistic — the syllabus repeatedly says
   things like "complete reproducibility cannot be guaranteed" and "plausible is not
   necessarily correct."
5. **The human stays responsible.** Any option suggesting GenAI output can be used without
   verification, or that GenAI replaces the tester, is wrong. Every chapter reinforces
   human verification.
6. **Time check:** 40 questions in 60 minutes = 90 seconds each. The 6 K3 questions need
   ~3 minutes each. So move fast on K1/K2 to bank time for the K3 scenarios.

---

## 5. Files in this pack

| File | Use |
|---|---|
| `01-chapter-1-genai-foundations.md` | Ch.1 — 7 points |
| `02-chapter-2-prompt-engineering.md` | Ch.2 — 16 points ⭐ highest value |
| `03-chapter-3-managing-risks.md` | Ch.3 — 11 points ⭐ second highest |
| `04-chapter-4-llm-infrastructure.md` | Ch.4 — 5 points |
| `05-chapter-5-deploying-genai.md` | Ch.5 — 7 points (mostly recall) |
| `06-glossary.md` | Every examinable term — targets the 8 K1 questions |
| `07-cheat-sheet.md` | One-page final revision, read on exam morning |
| `08-practice-questions.md` | 60 practice questions with explained answers |

---

## 6. Before you sit the exam

- Confirm with your exam provider that you are being examined on **v1.1** (released April 2026),
  not v1.0. These notes cover v1.1. The difference is minor, but check.
- Confirm your **CTFL certificate** is registered with the provider — it is a hard prerequisite.
- If English is not your first language, **request the 25% extra time (75 min) in advance**.
  It usually cannot be granted on the day.

---

## Attribution and scope

These are personal study notes. They summarise, and in places quote, the **ISTQB® Certified
Tester Specialist Level — Testing with Generative AI (CT-GenAI) Syllabus v1.1**, © International
Software Testing Qualifications Board (authors: Abbas Ahmad, Gualtiero Bazzana, Alessandro
Collino, Olivier Denoo, Bruno Legeard). ISTQB® is a registered trademark of the International
Software Testing Qualifications Board.

The exam blueprint figures come from the ISTQB® *Exam Structures & Rules* tables (v1.19).

Published here for **non-commercial, personal study use**, with the ISTQB acknowledged as the
source and copyright owner of the syllabus, per the terms in the syllabus copyright notice.
The official syllabus is available free from <https://istqb.org>.

The practice questions are original, written to drill the examinable points. They are **not**
official ISTQB exam questions.
