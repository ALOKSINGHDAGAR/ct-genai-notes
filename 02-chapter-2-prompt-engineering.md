# Chapter 2 — Writing Prompts That Actually Work

**Worth 16 points out of 46 — more than any other chapter.**
**Eleven questions, and five of them are the 2-point "apply it" questions.**

---

## Read this bit first

If you only have time to learn one chapter properly, learn this one.

Here is why. The exam has six questions worth 2 points each instead of 1. They are called **K3**
questions, and they give you a situation and ask what you would do. **Five of those six live in this
chapter**, all in one section (section 2.2, "applying prompts to test tasks").

That one section is worth **10 points**. The pass mark is 30 out of 46.

So: this chapter is 16 points, and the next one is 11. Together that is 27 — almost a pass on its own.

---

## Part 1 — A good prompt has six parts

A prompt is just what you type to the AI. A **structured prompt** is one where you deliberately
include six things.

Think of it like briefing a new junior tester who has just joined and knows nothing:

| # | Part | What it does | The junior-tester version |
|---|---|---|---|
| 1 | **Role** | Tells the AI who to be | "You are an experienced test analyst" |
| 2 | **Context** | Background about the situation | "We're testing the checkout on an e-commerce site" |
| 3 | **Instruction** | The actual task — clear and direct | "Write test conditions for this user story" |
| 4 | **Input data** | The material to work on | *(paste the user story, screenshot, code, existing tests)* |
| 5 | **Constraints** | Limits and rules to follow | "Functional tests only. Max 10. Don't invent requirements" |
| 6 | **Output format** | How you want the answer laid out | "A table with ID, Steps, Expected Result" |

Read down that right-hand column and it flows naturally:
**who you are → where we are → what to do → what to work on → what not to do → how to hand it back.**

### Three things the exam likes to test here

**There are exactly six.** If an option adds a seventh — "examples", "temperature", "token limit",
"which model" — it is wrong. Examples *are* important, but they belong to a **technique** called
few-shot prompting, not to the structure.

**Instruction vs Constraints.** The Instruction is *what to do*. Constraints are *restrictions on
how it gets done*. The syllabus words it as: constraints "specify how instructions should be applied
to input data."

**Context vs Input data.** Context is background about the situation. Input data is the actual
material you want processed.

---

## Part 2 — Three techniques, and when to use each

On top of the six-part structure, there are three techniques. Only three are "core" in this syllabus.

### Technique 1: Prompt chaining — break it into steps and check each one

Instead of one big prompt, you send several smaller ones. **After each step, you check the answer
before moving on.**

Example, refining acceptance criteria:

```
Step 1 → "Find any ambiguities in this user story."
         ↓ you read it, fix anything wrong
Step 2 → "Now check whether each criterion is testable."
         ↓ you check again
Step 3 → "Now check whether anything is missing."
```

**Why it works:** each answer feeds the next one, and you catch mistakes early instead of finding
them buried in a big final output.

> **The one thing that defines prompt chaining is the checking between steps.** Not "several
> prompts" — lots of things involve several prompts. It's the verification. If a question mentions
> checking intermediate results, this is your answer.

**Use it for:** complicated tasks that need breaking down, where accuracy matters.

### Technique 2: Few-shot prompting — show it examples

You put examples in the prompt so the AI copies the pattern.

There is a family of these, and the exam definitely asks about it:

| Name | How many examples |
|---|---|
| **Zero-shot** | **None.** It works from what it already knows |
| **One-shot** | **Exactly one** |
| **Few-shot** | **More than one** |

That's it. That's the whole distinction. Free marks.

**Why it works:** examples give it a clear target, so the output comes back consistent and in the
shape you wanted.

**Use it for:** anything where the output has to follow a **specific format or repeating pattern** —
Gherkin given-when-then test cases, keyword-driven scripts, reports in a fixed layout.

### Technique 3: Meta prompting — ask the AI to write the prompt

Instead of writing the prompt yourself, you describe what you're trying to achieve and **ask the AI
to write the prompt for you**. Then you review and improve it.

**Why it works:** the AI knows a lot about what makes prompts effective, and it saves you the effort.

**Use it when:** you're facing a **new kind of task and aren't sure how to phrase it**, or you want
to optimise a prompt you already have.

The syllabus calls this **"pairing" with the AI** — you and the tool working together, like pair
programming or pair testing.

> **The giveaway:** in meta prompting, the AI produces **the prompt**, not the answer.

### You can combine them

The syllabus spells out this exact sequence:

1. **Meta prompting** writes you a first draft prompt
2. That draft has examples in it, which you adapt and improve → **few-shot prompting**
3. You split the job into smaller steps so you can check each one → **prompt chaining**

So in the exam, **don't reject an answer just because it names two techniques.**

---

## Part 3 — System prompt vs user prompt

Two different kinds of prompt, doing different jobs.

**The system prompt** is the standing instruction. A developer or tester sets it once at the start.
The person chatting usually **can't see or edit it**. It stays the same for the whole conversation
and sets the ground rules.

Example from the syllabus:

> "You are a professional software testing assistant. Always respond clearly, use formal language,
> and focus on ISTQB-aligned practices. Avoid speculation and cite testing principles when relevant."

**The user prompt** is what you type each time. It's visible, and it changes with every message.

Example from the syllabus:

> "List the key differences between black-box and white-box testing with examples."

| | System prompt | User prompt |
|---|---|---|
| Who writes it | Developer or tester | The person chatting |
| Can you see it? | **Usually not** | **Yes** |
| Does it change? | **No — constant all session** | **Yes — every message** |
| Usually contains | **Role, context, constraints** | **Instruction**, plus context and output format |

The model reads **both together** when answering.

> ⚠️ Trap: the system prompt controls **behaviour** — tone, how concise to be, rules to follow. It
> does **not** set temperature or random seed. Those are model settings, covered in Chapter 3.

---

## Part 4 — Using all this on real test tasks (the 10-point section)

This is where the five 2-point questions come from. The pattern is always the same: **a situation is
described, and you pick the right approach.**

The situations follow the normal test process you already know from Foundation Level.

### Test analysis

**You give it:** requirements, user stories, specifications, **GUI wireframes**.
**You get back:** **prioritised test conditions** — for example, acceptance criteria.

What it can do:

- **Find problems in the requirements** — inconsistencies, ambiguities, gaps
- **Turn requirements into test conditions** — breaking them into **measurable, testable statements**
- **Prioritise by risk** — using likelihood and impact, plus things like **regulatory compliance**,
  **user-facing features** (login, payments), and **past defect history**
- **Check coverage** — mapping requirements to test conditions to find gaps
- **Suggest test techniques** — boundary value analysis, equivalence partitioning, and so on

> **Remember this line:** the **quality of what you feed in directly determines the quality of what
> comes out.** Rubbish in, rubbish out — and the exam says it in almost those words.

### Test design and test implementation

Quick reminder from Foundation Level: *design* turns test conditions into test cases; *implementation*
builds the testware you need to run them.

What it can do:

- **Write draft test cases** from functional *and* non-functional requirements — suggesting
  preconditions, inputs, expected results, coverage criteria
- **Create synthetic test data** that looks like production data but **protects privacy** — realistic
  scenarios **without exposing anyone's real information**
- **Write automated scripts** from test cases, for **various automation frameworks**, and update them
  when requirements change
- **Schedule and prioritise execution** based on priority, risk, resources, and **dependencies
  between tests**

### Automated regression testing

Why regression is the natural fit: every release adds more regression tests, they get run constantly
in **CI/CD pipelines**, and that makes them **ideal candidates for automation**.

What it can do:

- **Write keyword-driven scripts** — where **pre-set keywords stand for common test steps**, and the
  AI maps them to test cases
- **Analyse code changes** to find **high-risk areas**, so you test where it actually matters
- **Self-healing tests** — **automatically fixing scripts when the UI or API changes slightly**, so a
  renamed button doesn't break your whole suite
- **Write test reports** with metrics, failures, trends and dashboards
- **Build better defect reports**, pulling in **logs, screenshots and environment details**

**GUI vs API — the exam contrasts these:**

| | What keeps breaking | How AI helps |
|---|---|---|
| **GUI tests** | The **UI changes constantly** | Adapts to **dynamic locators** and changed interactions |
| **API tests** | **Request/response formats, endpoints, authentication** change | Adapts to **evolving API specs**, generates varied test data |

> ⚠️ The syllabus insists: **GenAI makes mistakes. Check the output — how carefully depends on the
> risk.**

### Test monitoring and test control

Why AI suits this: monitoring means wading through **huge amounts of data, often unstructured**, that
is already sitting in your test management tools.

- **Monitoring** — spotting trends, predicting risks, **flagging when things drift off plan**
- **Control** — suggesting you **reprioritise tests, adjust the schedule, move resources**
- **Completion reports** — what went well, lessons learned
- **Dashboards and plain-English summaries** so everyone can see progress

Quick reminder: **monitoring = watching and measuring. Control = doing something about it.**

---

## Part 5 — Picking the right technique (the question you will definitely get)

This is the highest-probability 2-point question in the exam. Learn this until it's automatic.

| Technique | Best for | Named examples in the syllabus |
|---|---|---|
| **Prompt chaining** | **Complex tasks needing accuracy, with a human check at each step** | Test analysis, test design, test automation |
| **Few-shot prompting** | **Repetitive work, or a strict output format** | **Gherkin test cases**, **keyword-driven testing**, reports in a fixed format |
| **Meta prompting** | **Flexible or unfamiliar tasks; writing a prompt for something new** | **Test report analysis**, **anomaly detection** |

### How to answer these in the exam

Read the scenario and hunt for the giveaway words:

**Points to prompt chaining:**
complex · multi-step · "verify each step" · "break it down" · intermediate results · needs accuracy

**Points to few-shot prompting:**
specific format · Gherkin · given-when-then · keyword-driven · repetitive · "like these examples"

**Points to meta prompting:**
"not sure how to write the prompt" · new task · optimise the prompt · flexible · test report
analysis · anomaly detection

---

## Part 6 — Measuring whether the AI did a good job

Seven metrics. The exam likes to swap the examples around, so learn what each one actually measures.

| Metric | Plain meaning | Testing example |
|---|---|---|
| **Accuracy** | Is it **right overall**, compared to a proper standard? | Do the test cases cover all the requirements? |
| **Precision** | Is it right **for one specific purpose**? | Do the test cases correctly find anomalies? |
| **Recall** | Did it find **everything** it should have? | Do the tests cover valid **and** invalid equivalence partitions? |
| **Relevance and Contextual Fit** | Does it **suit this situation**? | Do the tests match the test basis and domain requirements? |
| **Diversity** | Is there **variety, or is it repetitive**? | Do the tests cover different user behaviours and edge cases? |
| **Execution Success Rate** | Does it **actually run as-is**? | How many generated scripts run without syntax errors? |
| **Time Efficiency** | Did it **save time** versus doing it manually? | AI time vs human time for the same tests |

The three that get confused are the first three:
- **Accuracy** = correct overall
- **Precision** = correct for one specific objective
- **Recall** = found all of them

### One rule you must remember

> Because the AI is **non-deterministic**, these metrics have to be based on
> **statistically relevant data**.

In plain terms: **running it once proves nothing.** You might have got lucky or unlucky. You need
enough runs to be meaningful. This is a favourite exam point.

You can measure manually by reviewing, or automatically by comparing output against a known-good
reference. And beyond these seven general metrics, you can add **task-specific metrics** of your own.

---

## Part 7 — Improving a prompt that isn't working

Five techniques:

1. **Iterative modification** — start with a basic prompt and keep tweaking it based on what you get
   back, adding context or changing wording
2. **A/B testing** — write two or more versions and **compare them against your metrics** to see
   which wins
3. **Output analysis** — study the mistakes. Understanding **what kind of errors** you get tells you
   what to fix in the prompt
4. **Gather user feedback** — ask the testers using it whether the output is actually useful and
   clear
5. **Adjust length and specificity** — try longer, try shorter

> ⚠️ On that last one: **more context is not always better.** The syllabus says plainly that
> "in other cases shorter prompts may yield better generalization." Any option saying "always give
> as much context as possible" is wrong.

### And share what works

Teams that share their prompts build **prompt libraries**, standardise quality, and stop repeating
the same mistakes. This connects to Chapter 5, where it becomes an organisational practice.

---

## Traps to watch for

1. **Six components.** Examples are a technique, not a component.
2. **Zero-shot = 0, one-shot = 1, few-shot = more than one.** Don't lose these marks.
3. **Prompt chaining is defined by the checking between steps.**
4. **Meta prompting produces the prompt, not the answer.**
5. **System prompt: set once, hidden, constant. User prompt: visible, changes every turn.**
6. **One run proves nothing** — metrics need statistically relevant data.
7. **Shorter prompts sometimes work better.**
8. **Always check the output**, proportionate to the risk.
9. **Techniques combine.** Two-technique answers can be correct.

---

## Quick self-check

1. List the six parts of a structured prompt in order.
2. Which part sets restrictions on how the instruction is applied?
3. Zero-shot, one-shot, few-shot — how many examples in each?
4. What single thing defines prompt chaining?
5. When is meta prompting the right choice?
6. Name three things a system prompt usually holds.
7. Test cases must come out in strict Gherkin format, for many user stories. Which technique?
8. A complex prioritisation with dependencies, checked at each stage. Which technique?
9. A tester doesn't know how to phrase a prompt for a brand-new task. Which technique?
10. Which metric asks "does the script actually run?"
11. Which metric asks "did it find all of them?"
12. Why do metrics need statistically relevant data?
13. What's the three-step order for refining acceptance criteria with chaining?
14. What breaks GUI regression tests, and what breaks API regression tests?

<details><summary>Answers</summary>

1. **Role, Context, Instruction, Input data, Constraints, Output format.**
2. **Constraints.**
3. **Zero-shot = none. One-shot = exactly one. Few-shot = more than one.**
4. **You check and refine the result of each step before moving to the next.**
5. When the task is **flexible or new**, when you want to **optimise a prompt**, or when you're
   **unsure how to phrase one** and want to build it with the AI.
6. **Role, context and constraints** (plus general instructions about expected output).
7. **Few-shot prompting** — strict repeating output format.
8. **Prompt chaining** — complex, needs accuracy with a check at each step.
9. **Meta prompting.**
10. **Execution Success Rate.**
11. **Recall.**
12. Because the AI is **non-deterministic** — one output isn't representative.
13. **Ambiguities → testability → completeness**, checking and correcting at each step.
14. **GUI:** constant UI changes (AI adapts to dynamic locators and changed interactions).
    **API:** changing request/response formats, endpoints and authentication (AI adapts to evolving
    specs and generates varied data).
</details>

---

# Practice questions — Chapter 2

*Sixteen questions. The real exam asks **11** from this chapter — 6 worth 1 point and
**5 worth 2 points**. The 2-point ones are marked **[SCENARIO]** below; give those the most attention.*

**1.** Which of the following is a component of a structured prompt?
- a) Temperature
- b) Output format
- c) Token limit
- d) Model selection

**2.** In a structured prompt, what is the purpose of Constraints?
- a) To describe the background situation of the test object
- b) To specify how instructions should be applied to input data
- c) To define the persona the model should adopt
- d) To supply the user stories to be processed

**3.** A prompt provides a single worked example of the required output. This is:
- a) Zero-shot prompting
- b) One-shot prompting
- c) Few-shot prompting
- d) Meta prompting

**4.** Which statement describes meta prompting?
- a) Splitting a task into steps and verifying each one
- b) Providing several examples so the model copies a pattern
- c) Using the model to generate or refine prompts, which the tester then evaluates
- d) Setting a hidden instruction that persists across the session

**5.** Which best describes the relationship between system and user prompts?
- a) The system prompt changes with every interaction; the user prompt stays constant
- b) The model considers both together when generating a response
- c) The user prompt overrides the system prompt
- d) Only one of the two can be used in any given session

**6. [SCENARIO]** A tester must produce test cases for 40 user stories, all in the same
organisation-specific table format with fixed column headings. Which technique is most appropriate?
- a) Zero-shot prompting
- b) Few-shot prompting
- c) Meta prompting
- d) Increasing the context window

**7. [SCENARIO]** A test analyst needs GenAI to analyse a complex set of requirements, and wants to
confirm the output is correct at each stage before building on it. Which technique fits best?
- a) Few-shot prompting
- b) Prompt chaining
- c) Zero-shot prompting
- d) Lowering the temperature

**8. [SCENARIO]** A team is introducing GenAI for a test activity nobody has automated before, and
no one is confident how to phrase the request. Which technique should they start with?
- a) Meta prompting
- b) Few-shot prompting
- c) Prompt chaining
- d) Fine-tuning

**9. [SCENARIO]** A tester wants GenAI to analyse recent code changes so that regression testing can
be concentrated where the risk is highest. Which application is this?
- a) Self-healing and adaptive tests
- b) Impact analysis and test optimization
- c) Test data synthesis
- d) Enhanced defect reporting

**10. [SCENARIO]** GenAI is asked to produce synthetic customer records that resemble production
data for testing a payments flow, without exposing any real customer information. Which test
activity does this support?
- a) Test analysis
- b) Test design and test implementation
- c) Test monitoring and test control
- d) Test completion reporting

**11.** Which is a test analysis task supported by GenAI?
- a) Generating automated test scripts from structured test cases
- b) Prioritizing test conditions based on risk likelihood and impact
- c) Automatically adjusting scripts for changed UI locators
- d) Creating dashboards of test progress

**12.** Which metric evaluates whether generated output is applicable and appropriate for the given
situation?
- a) Diversity
- b) Relevance and Contextual Fit
- c) Recall
- d) Accuracy

**13.** Which metric would you use to check that generated test cases are not repetitive and explore
edge cases?
- a) Precision
- b) Diversity
- c) Execution Success Rate
- d) Time Efficiency

**14.** A tester runs a prompt once, gets an excellent result, and concludes the prompt is reliable.
What is wrong with this?
- a) Nothing — a single successful result is sufficient evidence
- b) LLM output is non-deterministic, so metrics must be based on statistically relevant data
- c) Metrics can only be applied to automated tests
- d) Accuracy cannot be evaluated without fine-tuning

**15.** Which is a recognised technique for iteratively refining prompts?
- a) Increasing the temperature until output varies
- b) A/B testing of prompt versions against predefined metrics
- c) Removing all constraints to avoid limiting the model
- d) Always making the prompt as long as possible

**16.** Why does the syllabus recommend sharing prompt practices across a test team?
- a) It reduces the energy consumption of the model
- b) It standardizes prompt techniques and maintains consistent quality
- c) It removes the need to verify generated output
- d) It allows the team to bypass quality gates

<details><summary>Answers and explanations</summary>

| Q | Ans | Why |
|---|---|---|
| 1 | **b** | The six are Role, Context, Instruction, Input data, Constraints, Output format. Temperature and token limits are model settings, not prompt components. |
| 2 | **b** | Constraints "help to specify how instructions should be applied to input data". (a) is Context, (c) is Role, (d) is Input data. |
| 3 | **b** | One example = one-shot. None = zero-shot. More than one = few-shot. |
| 4 | **c** | Meta prompting leverages the model's ability to generate or refine its own prompts, in an iterative cycle with the tester. (a) is chaining, (b) is few-shot, (d) is a system prompt. |
| 5 | **b** | The LLM generates responses by considering the unchanging system prompt and the current user prompt together. |
| 6 | **b** | Few-shot is recommended for repetitive tasks with a specific or constrained output format. |
| 7 | **b** | Prompt chaining is for complex tasks requiring precision with human verification at each step. |
| 8 | **a** | Meta prompting suits flexible, dynamic tasks and is explicitly recommended for crafting prompts for new tasks — including when the tester is unsure how to write one. |
| 9 | **b** | Impact analysis and test optimization: analysing code changes to identify high-risk areas, enabling targeted regression testing. |
| 10 | **b** | Test data synthesis sits within test design and test implementation — privacy-preserving synthetic data resembling production data. |
| 11 | **b** | Prioritizing test conditions by risk is a test analysis task. (a) is test implementation, (c) is regression testing, (d) is test monitoring. |
| 12 | **b** | Relevance and Contextual Fit — whether output is applicable and appropriate for a given context. |
| 13 | **b** | Diversity — covering a wide range of inputs and scenarios, avoiding repetition, exploring edge cases. |
| 14 | **b** | Given the non-deterministic nature of GenAI, metrics must be based on statistically relevant data. One run is not evidence. |
| 15 | **b** | A/B testing creates multiple prompt versions and evaluates which performs better against predefined metrics. (d) is wrong — shorter prompts sometimes generalize better. |
| 16 | **b** | Sharing standardizes prompt techniques, maintains consistent quality, and builds a culture of iterative improvement — e.g. through shared prompt libraries. |

</details>
