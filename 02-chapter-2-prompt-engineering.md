# Chapter 2 — Prompt Engineering for Effective Software Testing

> ## ⭐ THE MOST IMPORTANT CHAPTER IN THE EXAM
> **Exam weight: 11 questions, 16 points (35%) — 0×K1, 6×K2, 5×K3**
> Teaching time: 365 minutes (45% of the course).
>
> **5 of the 6 K3 questions in the entire exam come from section 2.2.** Each K3 is worth
> **2 points**. Section 2.2 alone is worth **10 points** — a third of the pass mark.
> If you are short on time, study this chapter first and study it twice.

## Learning objectives

| LO | K | Objective |
|---|---|---|
| GenAI-2.1.1 | K2 | **Give examples** of the structure of prompts used in GenAI for software testing |
| GenAI-2.1.2 | K2 | **Differentiate** core prompting techniques for software testing |
| GenAI-2.1.3 | K2 | **Distinguish** between system prompts and user prompts |
| GenAI-2.2.1 | **K3** | **Apply** generative AI to **test analysis** tasks |
| GenAI-2.2.2 | **K3** | **Apply** generative AI to **test design and test implementation** tasks |
| GenAI-2.2.3 | **K3** | **Apply** generative AI to **automated regression testing** |
| GenAI-2.2.4 | **K3** | **Apply** generative AI to **test monitoring and test control** tasks |
| GenAI-2.2.5 | **K3** | **Select and apply** appropriate prompting techniques for a given context and test task |
| GenAI-2.3.1 | K2 | **Understand** the metrics for evaluating the results of GenAI on test tasks |
| GenAI-2.3.2 | K2 | **Give examples** of techniques for evaluating and iteratively refining prompts |

## Keywords

**Testing terms:** acceptance criteria · test script · test case · test condition · test data ·
test design · test report
**GenAI terms:** few-shot prompting · meta prompting · natural language processing ·
one-shot prompting · prompt · prompt chaining · prompt engineering · system prompt ·
user prompt · zero-shot prompting

---

# STEP 1 — The 6 components of a structured prompt (GenAI-2.1.1, K2)

**Memorise these six in order. This is the most quotable list in the syllabus.**

| # | Component | Definition (syllabus wording) | Example for a test task |
|---|---|---|---|
| 1 | **Role** | The **perspective or persona** the model should take. Helps it determine its responsibilities and adopt an appropriate **tone or approach**. | "You are an experienced ISTQB-certified test analyst." |
| 2 | **Context** | The **background information** the model needs to determine the test conditions — the test object, the functionality to be tested, relevant contextual information. | "We are testing the checkout flow of an e-commerce web app." |
| 3 | **Instruction** | **Directives** outlining the specific task. **Clear, imperative and concise**; includes a task description and relevant requirements. | "Generate test conditions for the following user story." |
| 4 | **Input data** | Any information needed to perform the task — **user stories, acceptance criteria, screenshots, code, existing test cases or output examples**. | The actual user story text + a GUI wireframe |
| 5 | **Constraints** | **Restrictions or special considerations** the LLM should adhere to. They **specify how instructions should be applied to input data**. | "Only functional tests. Maximum 10 test cases. Do not invent requirements." |
| 6 | **Output format** | The expected **format, structure or characteristics** of the response. | "Return a Markdown table with columns: ID, Precondition, Steps, Expected Result." |

### 🧠 Memory hook
**R-C-I-I-C-O** → **"Really CleverIpswich Inspectors Check Output"**
Or think of it as briefing a new junior tester:
*who you are → where we are → what to do → what to work on → what not to do → how to hand it back.*

### ⚠️ Traps
- The syllabus says **six** components. Options adding a 7th ("temperature", "model selection",
  "examples", "token limit") are wrong. **Examples belong to few-shot prompting — a *technique*,
  not a prompt *component*.**
- **Constraints vs Instruction**: Instruction = *what to do*. Constraints = *restrictions on how
  it is applied*. This distinction is examinable.
- **Context vs Input data**: Context = background about the situation. Input data = the actual
  artefacts to process.
- The structure "**should be combined with the implementation of prompting techniques**" — it is
  not either/or.

---

# STEP 2 — The 3 core prompting techniques (GenAI-2.1.2, K2)

Only **three** are "core" in this syllabus. Learn each definition and its distinguishing feature.

## 1. Prompt chaining
> **Breaking a task into a series of intermediate steps (multiple prompts).** The result of each
> step is **manually or automatically checked and refined** before proceeding to the next step.

- **Why it works:** greater accuracy, because **each response informs the next prompt**.
- **Use when:** tasks are **complicated and require decomposition into subtasks** and
  **systematic checking of intermediate LLM outputs**.
- Also allows **dynamic interactions** in test processes.
- **Signature feature: verification between steps.** If a question mentions checking intermediate
  results, the answer is prompt chaining.

## 2. Few-shot prompting
> **Providing the LLM with examples in the prompt.**

Learn the whole family — this is a guaranteed question:

| Technique | Number of examples in the prompt |
|---|---|
| **Zero-shot** prompting | **No example** — relies on the model's pre-existing knowledge |
| **One-shot** prompting | **Exactly one** example, demonstrating the expected result for a given input |
| **Few-shot** prompting | **More than one** (a few), to further consolidate the desired response behaviour |

- **Why it works:** gives a **clear reference**, ensuring results are **consistent and in line
  with expectations**.
- **Use when:** examples can illustrate the required behaviour, letting the model
  **generalize effectively and produce reliable results**.
- **Signature feature: a specific output pattern or format must be matched.**

## 3. Meta prompting
> **Leverages the AI's ability to generate or refine its own prompts.** In an iterative cycle,
> the LLM generates prompts that are **evaluated and refined by the tester**.

- **Why it works:** it **takes advantage of the LLM's knowledge about optimized prompts** and
  **reduces the manual effort required to design effective prompts**.
- **Use when:** **efficiency and prompt optimization are critical**, or when
  **the tester is unsure how to craft an effective prompt** — they can **co-create it** with the LLM.
- The syllabus calls this **"pairing" with the GenAI tool** — a new way of collaborating,
  analogous to **pair programming and pair testing**.
- **Signature feature: the LLM writes the prompt, not the answer.**

> ✅ **They can be combined.** The syllabus gives this exact worked example:
> use **meta prompting** to create an initial prompt → that prompt may contain examples to adapt
> and enhance (**few-shot prompting**) → finally divide the task into smaller subtasks to enable
> validation of intermediate steps (**prompt chaining**).

---

# STEP 3 — System prompt vs user prompt (GenAI-2.1.3, K2)

| | **System prompt** | **User prompt** |
|---|---|---|
| **Who writes it** | The **developer or tester** | The **chatbot's user** |
| **Visibility** | **Not visible or editable by the user** in most interfaces | **Directly visible** |
| **Lifetime** | **Stays constant throughout the interaction session** | **Changes with each interaction** |
| **Purpose** | Defines the LLM's **behavior, personality, and operational parameters**; **sets the rules for the entire conversation** | The **actual input or question**; forms the **immediate context for each response** |
| **Typically contains** | **Role, context and constraints** | **Explicit instructions**, plus relevant context and **output format** instructions |

**"Operational parameters"** = how the LLM responds: using a formal tone, keeping answers concise,
respecting domain-specific rules, avoiding certain behaviour.

**Syllabus example of a system prompt:**
> "You are a professional software testing assistant. Always respond clearly, use formal language,
> and focus on ISTQB-aligned practices. Avoid speculation and cite testing principles when relevant."

**Syllabus example of a user prompt:**
> "List the key differences between black-box and white-box testing with examples."

**Typical usage:** set the system prompt **once at the start**, then send **successive user
prompts** for each interaction. **The LLM generates responses by considering both together.**

⚠️ Trap: "operational parameters" in the system prompt means **behavioural rules (tone, concision,
domain rules)** — it does **not** mean temperature or seed. Those are model **hyperparameters**
(Chapter 3.1.4).

---

# ⭐ STEP 4 — Section 2.2: APPLYING GenAI TO TEST TASKS (5 × K3 = 10 points)

This section maps GenAI onto the **standard ISTQB test process** you already know from CTFL.
For each activity, learn **inputs → tasks → outputs**.

## 2.2.1 Test analysis with GenAI (K3)

**Input data:** requirements, user stories, technical specifications, **GUI wireframes**, other
relevant information.
**Output:** typical test analysis work products — **prioritized test conditions (e.g. acceptance criteria)**.

| Task | Detail |
|---|---|
| **Identify potential defects in the test basis** | Analyse for **inconsistencies, ambiguities, or incomplete information**; compare similar requirement patterns or apply knowledge from previous defect reports to **flag anomalies and suggest improvements** |
| **Generate test conditions** from the test basis | Uses **natural language processing** to interpret meaning and break requirements into **measurable, testable statements** |
| **Prioritize test conditions based on risk level** | Using **risk likelihood and risk impact**; considers **regulatory compliance**, **user-facing features** (login, payment processing), and **historical defect data** |
| **Support coverage analysis** | **Map requirements and user stories to test conditions** to find gaps; useful where gaps lead to **escaped defects** |
| **Suggest test techniques** | e.g. **boundary value analysis, equivalence partitioning**, based on the type of requirement |

> **Closing sentence (examinable):** "The **quality and relevance of inputs** provided to the LLM
> in relation to the task to be completed **directly impact the accuracy and precision of the output**."

**Which technique for test analysis?** The syllabus exercises use:
- **Structured multimodal prompting** (text + GUI wireframe) → generate acceptance criteria
- **Prompt chaining + human verification** → progressively refine acceptance criteria in this
  order: **(1) identify ambiguities → (2) evaluate testability → (3) evaluate completeness**

## 2.2.2 Test design and test implementation with GenAI (K3)

Recall from CTFL: **test design** = elaborating/refining test conditions into test cases and
testware. **Test implementation** = creating or acquiring the testware needed to run the tests.

| Task | Detail |
|---|---|
| **Test case generation** | NLP creates draft test cases from **functional and non-functional** requirements; suggests **preconditions, inputs, expected results, coverage criteria** — from basic functional verification to complex **end-to-end** testing |
| **Test data synthesis** | Creates **representative, data privacy-preserving synthetic test data** resembling production data, covering **extreme situations** — **simulating realistic scenarios without exposing sensitive information** |
| **Automated test script generation** | Generates manual test procedures and automated scripts from structured test cases, **compatible with various test automation frameworks**; scripts can be **updated or extended** for new requirements |
| **Test execution scheduling and prioritization** | Analyses test cases and their **interdependencies**, optimizing schedules by **priority, associated risks, resource availability and test objectives** |

**Techniques used in the syllabus exercises:**
- **Prompt chaining + structured prompts + meta prompting** → functional test case generation
  (step 1: generate from acceptance criteria in a given format; step 2: **verify completeness via
  a coverage table**; step 3: **meta-prompt** for end-to-end test procedures)
- **Few-shot prompting** → **Gherkin-style (given-when-then)** test conditions and test cases
- **Prompt chaining** → **test case prioritization** with priorities and dependencies

## 2.2.3 Automated regression testing with GenAI (K3)

**Why regression?** "As each new iteration or release is completed, the number of regression test
cases **often increases**, making them **ideal candidates for automation, particularly in CI/CD
pipelines due to the high frequency of test execution**."

| Task | Detail |
|---|---|
| **Automated test script implementation with keyword-driven automation** | **Pre-defined keywords represent common test steps**; GenAI **maps keywords to specific test cases** and generates scripts |
| **Impact analysis and test optimization** | Analyse **code changes to identify high-risk areas** → **targeted regression testing** where most needed |
| **Self-healing and adaptive tests** | **Automatically adjust test scripts to handle minor UI or API changes**, preventing unnecessary failures and keeping suites stable |
| **Automated test reporting and insights** | Detailed, timely reports with success metrics, failures, key insights; **dashboards** showing trends and **predictive insights on potential failure points** |
| **Enhanced defect reporting and root cause analysis** | Automatic compilation of comprehensive defect reports with **test logs, screenshots, and test environment data** |

### GUI vs API regression — learn the contrast

| | **GUI regression tests** | **API regression tests** |
|---|---|---|
| **Challenge** | Frequently **unstable due to recurrent UI changes** | **Changing request/response formats, endpoints, and authentication** |
| **GenAI helps by** | Adapting scripts to **dynamic locators and modified interactions** | Adapting scripts to **evolving API specifications** and **generating diverse test data** |

> ⚠️ **Mandatory caveat:** "the testers must be aware that **GenAI can make mistakes**. The
> generated output must therefore be **carefully checked, depending on the associated risk**."

## 2.2.4 Test monitoring and test control with GenAI (K3)

**Why GenAI fits:** test monitoring requires "**retrieval of large quantities of (sometimes
unstructured) data, which are often already available in test management tools**."

| Task | Detail |
|---|---|
| **Test monitoring and metrics analysis** | Automate monitoring; **analyse trends to predict potential risks** and **alert teams of deviations from the plan** |
| **Test control** | Insights for **reprioritizing tests, adjusting test schedules, and reallocating resources** |
| **Test completion insights and continuous learning** | Generate **test completion reports**, highlighting **successes and lessons learned** |
| **Enhanced test metrics visualization and reporting** | **Dynamic dashboards and natural language summaries** so all stakeholders can access relevant metrics |

**Remember the CTFL distinction:** **monitoring = gathering/comparing information**;
**control = taking corrective action** (reprioritize, reschedule, reallocate).

---

# ⭐⭐ STEP 5 — CHOOSING THE RIGHT TECHNIQUE (GenAI-2.2.5, K3)

**This is the highest-probability K3 question in the exam.** A scenario will describe a test task,
and you must pick the technique. Learn this table until it is automatic.

| Technique | Recommended use case | Key features & applications |
|---|---|---|
| **Prompt chaining** | **Complex tasks requiring precision with human verification at each step** | **Breaks tasks into smaller steps.** Useful for **test analysis, test design and test automation**, where each test step is checked for functional correctness |
| **Few-shot prompting** | **Repetitive or specific/constrained output format tasks** | **Provides examples** for repetitive generation with a **specific pattern** — e.g. **Gherkin-style test cases (scenario-based)**, **keyword-driven testing**, or **test reporting with a specific output format** |
| **Meta prompting** | **Flexible, dynamic tasks; useful for crafting prompts for new tasks** | **General description of the objective**, guiding the LLM to create the prompt. Useful for complex tasks such as **test report analysis and anomaly detection** |

### 🎯 Decision rules for the exam

Read the scenario and look for the trigger word:

| If the scenario says… | Choose |
|---|---|
| "complex", "multi-step", "verify each step", "break down", "intermediate results", "decompose" | **Prompt chaining** |
| "specific format", "consistent pattern", "Gherkin", "given-when-then", "keyword-driven", "repetitive", "like these examples" | **Few-shot prompting** |
| "not sure how to write the prompt", "new task", "optimize the prompt", "flexible", "dynamic", "anomaly detection", "test report analysis" | **Meta prompting** |

⚠️ **Do not forget combinations are valid.** If the scenario has several of these characteristics,
an option combining techniques may well be correct. The syllabus explicitly endorses
**meta → few-shot → chaining** as a sequence.

---

# STEP 6 — Evaluating GenAI results (GenAI-2.3.1, K2)

**7 metrics.** Learn each definition *and* its testing example — ISTQB loves to swap the examples.

| Metric | Definition | Testing example |
|---|---|---|
| **Accuracy** | Overall **correctness** of the output against expert-written test cases, requirements or other standards | Degree to which generated test cases **cover all specified requirements** |
| **Precision** | Correctness of the output **with respect to a specific objective** | Degree to which generated test cases **correctly identify anomalies** |
| **Recall** | Ability to **identify all relevant instances** within a dataset | Degree to which generated test cases cover **valid and invalid equivalence partitions** of a data class |
| **Relevance and Contextual Fit** | Whether the output is **applicable and appropriate for a given context** | Degree to which test cases are **consistent with the test basis** and integrate **domain-specific requirements** |
| **Diversity** | A **wide range of inputs and scenarios** are covered, **avoiding repetition** | Degree to which test cases cover **various user behaviours** and **explore edge cases** |
| **Execution Success Rate** | Proportion of generated artefacts that can be **executed successfully as is** | How many generated scripts run **without syntax errors or output format issues** |
| **Time Efficiency** | **Time saved compared to manual test efforts** | Time for AI to generate test cases **vs** time a human would take manually |

**Memory hook — "A PRRDET":** Accuracy, Precision, Recall, Relevance, Diversity, Execution
success rate, Time efficiency.

### Two closing sentences you must know
1. Testers may evaluate these **manually (reviews)** or **automate** them, e.g. by **comparing
   LLM output against a predefined reference**.
2. > "Given the **non-deterministic nature** of GenAI, the **metrics must be based on
   > statistically relevant data**."
   ⚠️ **A single run proves nothing.** This is a favourite exam point.
3. Beyond these general metrics, **task-specific metrics** can be tailored to specific test activities.

---

# STEP 7 — Refining prompts iteratively (GenAI-2.3.2, K2)

**5 techniques:**

| Technique | What you do |
|---|---|
| **Iterative prompt modification** | Start with a base prompt and **iteratively modify based on actual results** — gradually adding context or adjusting wording (e.g. terminology) to improve specificity and relevance |
| **A/B testing of prompts** | Create **multiple versions** and evaluate **which produces better results based on predefined metrics** — determines which **phrasing or structure** works best |
| **Output analysis** | Examine output for **inaccuracies or inconsistencies** (e.g. against the test basis). **Understanding the types of errors helps refine prompts to avoid similar defects in future** |
| **Integrate user feedback** | Gather input from **testers** on the **usefulness and clarity** of output (e.g. level of detail of generated tests) |
| **Adjust prompt length and specificity** | Experiment with different lengths and detail levels. **Sometimes more context helps; in other cases shorter prompts yield better generalization** |

⚠️ Note the last one carefully: **longer is NOT always better.** An option saying "always provide
as much context as possible" is wrong.

### The organizational payoff (bridges to Chapter 5)
> Sharing practices across the test team **standardizes prompt techniques**, maintains
> **consistent quality**, and promotes a **culture of learning and iterative improvement** —
> e.g. by **sharing prompt libraries**.

---

# ⚠️ Chapter 2 exam traps

1. **Six** prompt components — not five, not seven. **Examples are a technique, not a component.**
2. **Zero-shot = 0 examples, one-shot = 1, few-shot = more than one.** Easy marks; don't lose them.
3. **Prompt chaining's defining feature is verification between steps** — not just "multiple prompts".
4. **Meta prompting = the LLM generates/refines the prompt**, not the answer.
5. **System prompt is set once and is hidden**; user prompt changes every turn and is visible.
6. **Metrics must be based on statistically relevant data** because output is non-deterministic.
7. **Shorter prompts sometimes win.** Beware "always add more context".
8. **GenAI output must always be checked** — proportionate to the associated risk.
9. **Accuracy vs Precision vs Recall**: Accuracy = overall correctness vs a standard;
   Precision = correctness for a *specific objective*; Recall = found *all* relevant instances.
10. **Techniques combine.** Don't reject a combined option just because it names two techniques.

---

# ✅ Chapter 2 self-check

1. List the six components of a structured prompt, in order.
2. Which component specifies restrictions on how instructions apply to input data?
3. Distinguish zero-shot, one-shot and few-shot prompting.
4. What single feature most distinguishes prompt chaining from simply sending several prompts?
5. When is meta prompting especially beneficial?
6. Name three things a system prompt typically contains.
7. A team must generate test cases in a strict Gherkin given-when-then format. Which technique?
8. A tester must estimate test effort and prioritize a complex test suite with dependencies,
   checking the logic at each stage. Which technique?
9. A tester does not know how to phrase a prompt for a brand-new test-report-analysis task.
   Which technique?
10. Which metric measures whether generated scripts run without syntax errors?
11. Which metric measures coverage of valid and invalid equivalence partitions?
12. Why must evaluation metrics be based on statistically relevant data?
13. Give the recommended three-step prompt-chaining order for refining acceptance criteria.
14. Name the two distinct challenges of GUI vs API regression testing.

<details><summary>Answers</summary>

1. **Role, Context, Instruction, Input data, Constraints, Output format.**
2. **Constraints.**
3. **Zero-shot** = no examples (relies on pre-existing knowledge); **one-shot** = one example;
   **few-shot** = more than one example.
4. **The result of each step is checked (manually or automatically) and refined before proceeding
   to the next step.**
5. When **efficiency and prompt optimization are critical**, or when the **tester is unsure how to
   craft an effective prompt** and wants to co-create it with the LLM ("pairing").
6. **Role, context and constraints** (plus general instructions, e.g. on expected output).
7. **Few-shot prompting** — specific/constrained output format with a repeating pattern.
8. **Prompt chaining** — complex task needing precision with human verification at each step.
9. **Meta prompting** — flexible/dynamic task, crafting a prompt for a new task; the syllabus
   names test report analysis and anomaly detection explicitly.
10. **Execution Success Rate.**
11. **Recall.**
12. Because GenAI is **non-deterministic** — outputs vary for the same input, so a single sample
    is not representative.
13. **(1) Identify ambiguities → (2) evaluate testability → (3) evaluate completeness**, with
    manual verification and correction at each step.
14. **GUI:** instability from recurrent UI changes (GenAI adapts to dynamic locators and modified
    interactions). **API:** changing request/response formats, endpoints and authentication
    (GenAI adapts to evolving API specs and generates diverse test data).
</details>
