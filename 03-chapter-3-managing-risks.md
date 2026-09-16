# Chapter 3 — When AI Gets It Wrong, and What To Do

**Worth 11 points out of 46 — second only to Chapter 2.**
**Ten questions: three easy recall ones, six understanding ones, one 2-point scenario.**

---

## What this chapter is really about

Chapter 1 told you the AI writes things that *sound* right. This chapter is about what happens when
"sounds right" and "is right" come apart — and what you do about it.

It covers four separate worries:

1. The AI makes things up, reasons badly, or leans one way
2. Your confidential data leaks
3. It burns a surprising amount of electricity
4. There are laws and standards you need to know about

Three of those 11 points come from **pure recall** questions, so there are easy marks here.

---

## Part 1 — The three ways AI output goes wrong

These three get confused constantly. The trick is to learn **the cause of each**, because that's
what separates them.

### Hallucination — it made something up

The AI produces something **factually wrong or completely irrelevant**. The official glossary
definition is blunt: **"Wrong information created by an LLM."**

**What it looks like in testing:**
- Test cases for features that don't exist
- Scripts that don't work
- Test cases checking **acceptance criteria that were never in the user story**

**Why it happens:** remember Chapter 1 — the model generates *statistically plausible* text. It has
no fact-checker inside it.

**One word: INVENTED.**

### Reasoning error — the logic doesn't hold up

The AI **misreads logical structure** — cause and effect, if-then conditions, step-by-step working —
and reaches a wrong conclusion.

**Why it happens — and this is the exam answer:**

> LLMs **lack true logical reasoning and rely on pattern matching.**

It isn't thinking through your problem. It's recognising that your problem *looks like* problems
it has seen, and producing something shaped like the answers to those.

**Where it shows up in testing:** **test planning** and **test case prioritisation** — jobs that
genuinely need logic. Also anything mathematical.

**One word: ILLOGICAL.**

### Bias — it leans one way

The output consistently **favours certain information, approaches or assumptions**.

**Why it happens:** it comes **from the training data**. Not from your prompt. Not from randomness.
From what the model was fed while learning.

The syllabus example: models trained mostly on English text **under-represent non-English
perspectives**.

**Where it shows up in testing:** generating test data, or refining acceptance criteria.

**One word: SKEWED.**

### Two sentences worth memorising

> These problems come from **the nature of the training data** and **the inherent limits of the
> transformer model**.

> Because the AI is **non-deterministic**, these are hard to fix — **a problem can look fixed in one
> conversation and come back in the next.**

That second one matters. **You can't "fix" a hallucination the way you fix a code defect.** It isn't
a bug sitting in a line of code — it's a property of how the thing works.

---

## Part 2 — Spotting them (this is the 2-point question)

You'll get a scenario and have to say what went wrong and how you'd catch it. The methods are
**grouped by problem type** — learn the grouping.

All of these work through **review**, or **review combined with automated checking**.

### Catching hallucinations — three methods

- **Cross-verification** — compare the output against **documentation, requirements and known system
  behaviour**. Tools can help by flagging mismatches against trusted sources.
- **Domain expertise consultation** — get a **subject matter expert** to check it. They catch the
  subtle things tools miss.
- **Consistency checks** — is the output consistent with itself, and with what you already know?

### Catching reasoning errors — two methods

- **Logical validation** — read through the reasoning and check it holds together. Tools help, but
  **complicated cases need a human.**
- **Output testing** — **just run it.** Execute the generated test cases or scripts against the
  actual system and see what happens. Can be automated.

### Catching bias — two approaches

- Check whether the generated testware **fairly reflects your test strategy and coverage
  requirements**
- Look for **whole test types going missing** — the syllabus example is
  **non-functional tests being under-represented**

### How much of this should you do?

> It **depends on the risk level** of the task you're using AI for.

Low-risk task, light checking. High-risk task, heavy checking. Sensible, and examinable.

### The decision table for the scenario question

| What the scenario describes | What it is | How you catch it |
|---|---|---|
| A test case mentions a field or requirement **that doesn't exist** | **Hallucination** | **Cross-verification** against the test basis |
| A prioritisation or estimate where **the logic doesn't add up** | **Reasoning error** | **Logical validation** or **output testing** |
| Generated tests **consistently skip a whole category** (e.g. non-functional) | **Bias** | **Review against the test strategy and coverage requirements** |

---

## Part 3 — Reducing the problem

First, *when* do these problems get worse? The syllabus says: when **prompts are poorly designed**,
or when you **haven't given it enough context**.

Which means the fix loops straight back to Chapter 2.

**Five mitigation techniques:**

1. **Give it complete context** — put all the relevant information in the prompt (those six components)
2. **Break the prompt into smaller pieces** — use **prompt chaining** and check each step.
   **This catches reasoning errors early**
3. **Use clear, unambiguous data formats** — don't make it guess what your input means
4. **Pick the right model for the job** — one suited to that kind of task
5. **Compare across models** — run the same prompt through **several LLMs and compare** the answers

> **Worth knowing for a link question:** the syllabus points forward to **two more techniques in
> Chapter 4** — **Retrieval-Augmented Generation (RAG)** and **fine-tuning**.

---

## Part 4 — Getting consistent answers (easy recall marks)

Start with the honest bit:

> **Complete reproducibility cannot be guaranteed.**

You can reduce the variation, not eliminate it. And it gets worse with **long outputs**.

**Two ways to reduce it:**

### Lower the temperature

**Temperature** is a setting that **controls how random or creative** the output is.

Turn it down and the model **narrows its range of choices**, picking the safe, likely option more
often. Output becomes more consistent.

**But there's a cost**, and the exam tests it: it **limits creativity and diversity**, making
output **repetitive or overly deterministic**.

> ⚠️ Low temperature makes answers **more consistent. It does not make them more correct.** It does
> not stop hallucinations. Consistently wrong is still wrong.

### Set a random seed

Some systems let you fix the **seed** for the random number generator, so the same "random"
sequence gets used each time. That improves reproducibility — though it's **pseudo-random**, and not
every implementation offers it.

Also worth noting: **automating parts of your output checking** gives you a structured, consistent
way to evaluate, which helps manage the variability.

---

## Part 5 — Privacy and security risks

When you paste things into an AI tool, where does that information go?

### Three privacy worries

- **Unintentional data exposure** — the model might **accidentally reveal sensitive information** in
  its output
- **No control over how your data is used** — the tool might **store and process your data without
  your consent**
- **Compliance risk** — using AI carelessly can breach regulations like **GDPR**
  (Regulation (EU) 2016/679) and land you in **legal trouble**

### Three security worries

- Your **AI test infrastructure can be attacked** — breaches, unauthorised access
- **Attackers can exploit the LLM itself** to change its behaviour or **pull out sensitive
  information**
- **Attackers can feed in malicious data** to mislead the model and damage its accuracy

---

## Part 6 — Four ways people attack AI systems

Learn what makes each one different. The distinctions are the exam question.

### Context manipulation

**Sending requests designed to extract confidential training data.**

The syllabus example: **flood the model with extremely long prompts to overload its context window**,
and it may start **spitting out random fragments of its training data** — possibly including
sensitive material.

*Note: **context manipulation is a listed keyword**, so the definition itself is examinable.*

### Request manipulation

**Feeding in data that disrupts the output.**

The example: **images that trick the AI into the wrong context**, making it hallucinate about things
like acceptance criteria.

### Data poisoning

**Corrupting the training data.**

The example: **deliberately giving fake ratings** when scoring an AI-generated test report, so the
model learns the wrong lesson.

### Malicious code generation

**Manipulating the AI into writing backdoors.**

The example: getting it to generate code that **opens a channel to a specific malicious IP address**.

### The quick discriminators

- **Context manipulation** → overload the context window to **get training data out**
- **Request manipulation** → corrupt the **input** to wreck the **output**
- **Data poisoning** → corrupt the **training data**
- **Malicious code generation** → the **output itself** is the weapon

---

## Part 7 — Protecting yourself

### First, a correction people get wrong

> GDPR **does not explicitly prohibit** using GenAI. It **provides safeguards** that limit what you
> can do — particularly around **lawfulness, and the purposes of collecting, processing and storing
> data**.

⚠️ An exam option saying "GDPR bans GenAI in testing" is **wrong**.

### Four core privacy measures

- **Data minimisation** — **don't process sensitive data unless you're legally allowed to**, and use
  only as much non-sensitive data as you need
- **Anonymisation and pseudonymisation** — **mask or replace** identifying information
- **Secure storage and transmission** — **encryption and access controls**
- **Training and policies** — teach people to use these tools responsibly and ethically

### Five more mitigations

- **Review the output systematically** — **"human evaluation is essential"**, in the syllabus's own
  words
- **Compare against another LLM** — run it through a second model and see if they agree
- **Choose a secure environment** — three options depending on how confidential your work is:
  1. A **commercial secure offering** from an LLM provider
  2. Running the LLM in a **secure cloud**
  3. **Installing it on your own infrastructure** (most control)
- **Regular security audits and vulnerability assessments**
- **Keep up with security best practice**

> Two closing points: these are **complementary — you need a combination**, not one of them. And you
> should **involve senior Security Engineers, Legal counsel, the CTO or the CISO** if your
> organisation has them.

---

## Part 8 — The environmental cost

Training and running these models takes **serious computing power**, and that means electricity and
CO₂.

**What drives the consumption:** **how complex the task is**, and **how much computing it needs**.

**The comparison to remember** — this is almost certainly your exam question:

> Generating **one image** with a powerful model can use **about as much energy as fully charging a
> smartphone**.
> Generating **text** uses only **a small percentage** of a phone charge.

**Images cost far more than text.**

Two other points:
- **Accurate figures are hard to come by** — the syllabus admits this
- One request is negligible, but **millions of users add up to substantial environmental strain**

**What to do:** **limit unnecessary interactions with the model.** Don't fire off ten prompts where
one careful one would do.

---

## Part 9 — Laws, standards and frameworks (easy recall marks)

Four items. **The most common question is about which type each one is** — so learn the type column
first.

| Name | Type | What it does | For testing |
|---|---|---|---|
| **ISO/IEC 42001:2023** | **Standard** | How to **manage AI systems in an organisation** | Keeps GenAI testing consistent and reliable |
| **ISO/IEC 23053:2022** | **Standard** | A framework for the **AI lifecycle using ML**, focused on **safety and transparency** | Covers data quality, transparency, safety |
| **EU AI Act** | **Regulation** | Legal framework that **sorts AI applications by risk level** | Requires **transparency, accountability, bias mitigation** |
| **NIST AI Risk Management Framework** | **Framework** | US guidance on AI risk, focused on **fairness, transparency, security** | Helps prevent biased test results |

### The shortcuts

- **Two ISO standards** — 42001 is about **managing**, 23053 is about the **lifecycle**
- **The EU AI Act is the only law** — and the only one that **sorts by risk level**
- **NIST is the American framework** — think fairness and bias

And remember from the syllabus introduction: **the standards documents themselves are not
examinable.** Only what's summarised in that table. So don't go reading ISO 42001.

---

## Traps to watch for

1. **Hallucination = invented. Reasoning error = illogical. Bias = skewed by training data.**
2. **Bias comes from training data** — not the prompt, not the temperature.
3. **Reasoning errors happen because it pattern-matches instead of reasoning.**
4. **You can't permanently fix these** — they can reappear in the next conversation.
5. **Complete reproducibility is impossible.** Low temperature reduces *variation*, not *error*, and
   costs you creativity.
6. **GDPR doesn't ban GenAI.**
7. **Context manipulation extracts training data. Request manipulation corrupts input.**
8. **Data poisoning attacks the training data**, not the prompt.
9. **EU AI Act = Regulation. NIST = Framework. ISO/IEC = Standards.**
10. **Images use far more energy than text.**
11. **Human review is essential** — you never fully automate the checking.
12. **You need a combination of mitigations**, not just one.

---

## Quick self-check

1. Define hallucination, reasoning error and bias in one line each.
2. Why do LLMs make reasoning errors?
3. Where does bias come from?
4. Name the three ways to detect a hallucination.
5. Name the two ways to detect a reasoning error.
6. What decides how thoroughly you check?
7. Name the two ways to reduce non-determinism, and the cost of the first.
8. What's the classic example of context manipulation?
9. Which attack targets training data?
10. Name the three secure environment options.
11. Which of the four governance items is a Regulation? Which is a Framework?
12. Image or text — which uses more energy?
13. Which two Chapter 4 techniques are named as ways to improve results?
14. Which senior roles should be involved in privacy and security decisions?

<details><summary>Answers</summary>

1. **Hallucination** — output that's factually wrong or irrelevant (invented).
   **Reasoning error** — misreading logical structure and reaching a wrong conclusion.
   **Bias** — output that systematically favours certain information or assumptions.
2. They **lack true logical reasoning and rely on pattern matching**.
3. **The data the model was trained on.**
4. **Cross-verification, domain expertise consultation, consistency checks.**
5. **Logical validation** and **output testing**.
6. **The estimated risk level** of the task.
7. **Lowering the temperature** (cost: **limits creativity and diversity**, output becomes
   repetitive) and **setting random seeds**.
8. **Overloading the context window with very long prompts** so the model reveals fragments of its
   **training data**.
9. **Data poisoning.**
10. **(1)** A commercial secure offering from a provider; **(2)** a secure cloud;
    **(3)** your own infrastructure.
11. Regulation = **EU AI Act**. Framework = **NIST AI RMF**. (Both ISO/IEC items are Standards.)
12. **Generating an image** — roughly a full phone charge, versus a small percentage for text.
13. **Retrieval-Augmented Generation (RAG)** and **fine-tuning**.
14. **Senior Security Engineers, Legal counsel, the CTO, or the CISO.**
</details>
