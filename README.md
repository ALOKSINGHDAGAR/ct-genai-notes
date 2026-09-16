# ISTQB CT-GenAI — Study Notes in Plain English

**Certified Tester Specialist Level — Testing with Generative AI (CT-GenAI), Syllabus v1.1**

Written for someone who is **new to AI**. No jargon without an explanation, no assumed background.
Everything here comes from the official ISTQB syllabus and the official exam blueprint.

---

## Start here: what the exam actually is

| | |
|---|---|
| **Questions** | 40 |
| **Points** | **46** — not 40, because some questions are worth 2 |
| **To pass** | **30 out of 46** (65%) |
| **Time** | 60 minutes — **75 minutes if English isn't your first language** |
| **Prerequisite** | You must already hold **ISTQB Foundation Level (CTFL)** |
| **Negative marking** | **None.** Never leave a question blank |

### Why 40 questions gives 46 points

Questions come at three difficulty levels:

| Level | What it asks | How many | Points each |
|---|---|---|---|
| **K1 — Remember** | Recall a definition or a list | 8 | 1 |
| **K2 — Understand** | Explain or compare something | 26 | 1 |
| **K3 — Apply** | **Here's a situation — what would you do?** | **6** | **2** |

Those six K3 questions are worth **12 points between them**. Getting all six right is worth more
than getting all eight recall questions right. They are the ones to prepare for.

---

## The table that should decide how you study

This is the official per-chapter split from ISTQB's exam blueprint:

| Chapter | Topic | Questions | **Points** | Share |
|---|---|---|---|---|
| 1 | Getting started with generative AI | 7 | **7** | 15% |
| 2 | **Writing prompts that work** | 11 | **16** | **35%** |
| 3 | **When AI gets it wrong** | 10 | **11** | **24%** |
| 4 | Building AI into your test setup | 5 | **5** | 11% |
| 5 | Rolling AI out across a team | 7 | **7** | 15% |
| | **Total** | **40** | **46** | |

### What that means in practice

**Chapters 2 and 3 are worth 27 points. You need 30 to pass.** Master those two, then pick up just
3 points anywhere else, and you're through.

**Five of the six 2-point questions are in Chapter 2**, all in one section — applying prompting
techniques to test tasks. That single section is worth 10 points. It is the most valuable thing in
the syllabus.

**Chapter 4 is only 5 points**, all straightforward understanding. It has the most technical-sounding
words, which makes beginners over-study it. Don't. Read it twice and move on.

**Chapter 5 is the best value for effort.** It gets the least teaching time in the syllabus but is
worth the same as Chapter 1 — and **four of its seven questions are pure recall**. Learn four short
lists, bank four points.

---

## A three-day plan

**Day 1 — foundations, then straight into the big one**
- Chapter 1 in full (about an hour)
- Chapter 2, parts 1 to 4
- Memorise the **six prompt components** and the **three techniques** before you sleep

**Day 2 — the highest-value material**
- Chapter 2, parts 5 to 7 (the metrics and technique-picking)
- Chapter 3 in full
- First pass through the glossary
- Try the Chapter 1–3 questions in the mock

**Day 3 — sweep up and revise**
- Chapter 4, then Chapter 5 (the easy recall marks)
- Second glossary pass
- The full 40-question mock, then review every wrong answer
- Read the cheat sheet last

---

## What's in this repo

| File | What it's for |
|---|---|
| `01-chapter-1-genai-foundations.md` | What AI is and how an LLM works — **7 points** |
| `02-chapter-2-prompt-engineering.md` | Writing prompts, applying them to test tasks — **16 points** |
| `03-chapter-3-managing-risks.md` | Hallucinations, privacy, energy, regulations — **11 points** |
| `04-chapter-4-llm-infrastructure.md` | RAG, agents, fine-tuning, LLMOps — **5 points** |
| `05-chapter-5-deploying-genai.md` | Strategy, adoption, skills, roles — **7 points** |
| `06-glossary.md` | Every examinable term, with a plain-English version of each |
| `07-cheat-sheet.md` | One page. Read it on the morning of the exam |
| `08-practice-questions.md` | A 40-question mock weighted exactly like the real exam, plus drills |

Each chapter file has the same shape: what the chapter is about → the material in steps → traps to
watch for → a self-check quiz with answers.

---

## How ISTQB writes questions

Five things worth knowing before you sit down:

**1. The keywords are examinable on their own.** The syllabus says every term listed under a chapter
heading "shall be remembered, even if not explicitly mentioned in the learning objectives." That's
where most of the eight recall questions come from. The glossary covers all of them.

**2. Wrong options are usually true statements that don't answer the question.** They're not obvious
nonsense. Re-read what's actually being asked before you choose.

**3. Absolutes are nearly always wrong.** Options containing "always", "never", "guarantees" or
"eliminates" almost never survive, because AI is probabilistic. The syllabus itself says things like
"complete reproducibility cannot be guaranteed" and "plausible is not necessarily correct."

**4. The human stays responsible.** Any option suggesting AI output can be used without checking, or
that AI replaces the tester, is wrong. Every chapter repeats this.

**5. Watch the clock.** 40 questions in 60 minutes is 90 seconds each — but the six 2-point questions
need about three minutes each. Move quickly through the easy ones to bank time for those.

### Timing plan

| Pass | Time | What |
|---|---|---|
| 1 | ~35 min | All 34 one-point questions, about a minute each. Flag anything slow |
| 2 | ~18 min | The six 2-point scenarios, about three minutes each |
| 3 | ~7 min | Review flagged questions. **Check nothing is blank** |

---

## Before the exam

- **Check which version you're being examined on.** These notes cover **v1.1** (April 2026). Confirm
  with your exam provider.
- **Make sure your CTFL certificate is registered** with the provider — it's a hard prerequisite.
- **If English isn't your first language, request the 25% extra time in advance.** It usually can't
  be granted on the day.

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
