# Chapter 3 — Managing Risks of Generative AI in Software Testing

> ## ⭐ SECOND-HIGHEST VALUE CHAPTER
> **Exam weight: 10 questions, 11 points (24%) — 3×K1, 6×K2, 1×K3**
> Teaching time: 160 minutes.
> The single K3 here is **GenAI-3.1.2 — identify hallucinations, reasoning errors and biases in
> LLM output** (worth 2 points). The 3 K1s are cheap recall marks: **3.1.1, 3.1.4, 3.4.1**.

## Learning objectives

| LO | K | Objective |
|---|---|---|
| GenAI-3.1.1 | **K1** | **Recall** the definitions of hallucinations, reasoning errors and biases |
| GenAI-3.1.2 | **K3** | **Identify** hallucinations, reasoning errors and biases in LLM output |
| GenAI-3.1.3 | K2 | **Summarize** mitigation techniques for hallucinations, reasoning errors and biases |
| GenAI-3.1.4 | **K1** | **Recall** mitigation techniques for **non-deterministic behavior** of LLMs |
| GenAI-3.2.1 | K2 | **Explain** key data privacy and security risks |
| GenAI-3.2.2 | K2 | **Give examples** of data privacy and vulnerabilities in using GenAI |
| GenAI-3.2.3 | K2 | **Summarize** mitigation strategies for data privacy and security |
| GenAI-3.3.1 | K2 | **Explain** the impact of task characteristics and model usage on energy consumption |
| GenAI-3.4.1 | **K1** | **Recall** examples of AI regulations, standards and best practice frameworks |

## Keywords

**Testing terms:** security · vulnerability · data privacy
**GenAI terms:** hallucination · temperature · reasoning error · bias · context manipulation

---

# STEP 1 — The three defect types (GenAI-3.1.1, K1 — guaranteed question)

These three are constantly confused. Learn the **cause** of each, because that is how they are
distinguished.

| Defect | Definition | Cause | Manifestation in software testing |
|---|---|---|---|
| **Hallucination** | Output that appears **factually incorrect or irrelevant** to a given task. *(Glossary: "Wrong information created by an LLM.")* | The model generates **statistically plausible** text, not verified fact | **Fictitious or irrelevant test cases**; **incorrect or non-functioning test scripts**; test cases that **verify non-existent acceptance criteria** |
| **Reasoning error** | **Misinterpreting logical structures** — cause-and-effect, conditional logic, or step-by-step problem-solving — leading to incorrect conclusions | **LLMs lack true logical reasoning and rely on pattern matching** | **Test planning** and **test case prioritization** (tasks requiring logical reasoning); **mathematical reasoning** |
| **Bias** | Output that **favours certain types of information, approaches, or assumptions** | **Originates from the data on which the model was trained** | Generating **test data** or **refining acceptance criteria**; e.g. models trained mostly on English data **underrepresent non-English perspectives** |

### 🧠 The one-word discriminator
- **Hallucination → INVENTED** (something that is not there / not true)
- **Reasoning error → ILLOGICAL** (the steps or the logic are wrong)
- **Bias → SKEWED** (systematically leaning one way, because of training data)

### Two framing sentences
> "These defects result from the **nature of their training data** and the **inherent limitations
> of the transformer model**."

> "The **non-deterministic behavior of LLMs makes it difficult to fix these types of defects**;
> they may **appear to be fixed for one LLM output but reappear in another conversation** with
> the same LLM."

⚠️ That second sentence is a strong exam point: you **cannot "fix" a hallucination permanently**
the way you fix a code defect.

---

# ⭐ STEP 2 — Detecting them in LLM output (GenAI-3.1.2, **K3 — 2 points**)

This is a scenario question: you will be shown a situation and asked which detection approach
applies. **The detection methods are grouped by defect type — learn the grouping.**

> All of these are applied "through **review**, or a **combination of review and automated
> verification**."

## Hallucination detection (3 methods)
| Method | What it is |
|---|---|
| **Cross-verification** | Compare AI output with **existing documentation, requirements, and known system behavior**. Automated tools can cross-reference against **established data sources to flag discrepancies** |
| **Domain expertise consultation** | Engage **subject matter experts** to validate accuracy — essential for **nuanced insights automated systems might overlook** |
| **Consistency checks** | Verify outputs are **consistent with each other and with known information**; automated systems flag inconsistencies |

## Reasoning error detection (2 methods)
| Method | What it is |
|---|---|
| **Logical validation** | Evaluate the **logical flow** — consistency, coherence, structured reasoning — through **review cycles**. Automated tools can help, but **complex cases may require human judgment** |
| **Output testing** | **Run the generated test cases or scripts against the test objects** and verify the results. Can be **partially or fully automated** |

## Bias detection (2 approaches)
| Approach | What it is |
|---|---|
| **Review representation of strategy/coverage** | Check whether generated testware (test code, synthetic test data) **fairly and accurately represents the defined test strategy and coverage requirements** |
| **Assess bias related to test types** | E.g. **underrepresented non-functional tests** in the LLM output |

> **Closing sentence:** "The actual implementation of these detection methods will **depend on the
> estimated risk level** of hallucinations, reasoning errors or biases in the test task."

### 🎯 K3 decision rule
| The scenario shows… | It is a… | Detect by… |
|---|---|---|
| A test case referencing a requirement/field/button that does not exist | **Hallucination** | **Cross-verification** against the test basis |
| A prioritization or estimation whose arithmetic/logic does not follow | **Reasoning error** | **Logical validation**, or **output testing** |
| Generated test data covering only one demographic/language; no non-functional tests | **Bias** | **Review against the test strategy and coverage requirements** |

---

# STEP 3 — Mitigating hallucinations, reasoning errors and biases (GenAI-3.1.3, K2)

**When are these more likely?** "when prompts are **not properly designed**" or "when
**relevant contextual input data is lacking** for a given test task." *(Note how this points
straight back to Chapter 2.)*

**5 mitigation techniques:**

| # | Technique | Detail |
|---|---|---|
| 1 | **Provide complete context** | Ensure the prompt contains **all relevant information** (the 6 components) |
| 2 | **Divide prompts into manageable segments** | Use **prompt chaining**, verifying each output before the next. **Helps detect reasoning errors early** |
| 3 | **Use clear, interpretable data formats** | Avoid ambiguous formats; **structured, straightforward formats** help the model focus |
| 4 | **Select the appropriate GenAI model for the task** | Use an LLM **specifically trained for the task at hand** (links to 5.1.3) |
| 5 | **Compare results across models** | Evaluate the prompt with **several LLMs and compare outputs** to detect errors and select the most reliable result |

> **Forward reference:** "Chapter 4 introduces **two complementary techniques** for improving LLM
> results: **Retrieval-Augmented Generation and Fine-Tuning**." ⚠️ Know that these two are the
> *Chapter 4* answers to this problem — a question may test that link.

---

# STEP 4 — Mitigating non-determinism (GenAI-3.1.4, **K1** — easy mark)

**Cause (from Ch.1):** probabilistic sampling processes used during inference.
**Risk factor:** "particularly for **long outputs**, which increases the risk of variability."

> ⚠️ **Start here:** "**complete reproducibility cannot be guaranteed**" — but certain strategies
> reduce variability.

| Strategy | How it works | Trade-off |
|---|---|---|
| **Adjusting the temperature parameter** | **Lowering temperature** during inference **narrows the probability distribution**, reducing randomness → **more consistent outputs** | **Limits creativity and diversity**, making outputs **more repetitive or overly deterministic** |
| **Setting random seeds** | Some implementations allow a **seed value for the random number generator**, ensuring the same **pseudo-random** sequence → **improves reproducibility** | Only available in some implementations |

**Definition to memorise:** **Temperature** = "A parameter that **controls the randomness or
creativity** of an LLM's outputs."

Also: reducing hallucination/reasoning-error risk involves addressing non-determinism, e.g. by
**automating some aspects of output verification** to ensure a **structured and consistent
evaluation process**.

⚠️ **Traps:** (a) Low temperature does **not** improve accuracy or eliminate hallucinations — it
reduces *variability*. (b) Temperature is **not** set in the system prompt; it is a model
parameter. (c) Seeds give **pseudo-random** determinism, not guaranteed identical output in all
implementations.

---

# STEP 5 — Data privacy and security risks (GenAI-3.2.1, K2)

## Three data privacy concerns
| Concern | Detail |
|---|---|
| **Unintentional data exposure** | Models may **generate outputs that accidentally reveal sensitive information** |
| **Lack of control over data usage** | Tools may **store and process sensitive data without explicit user consent or control** → misuse or unauthorized access |
| **Compliance risks** | Using GenAI without complying with regulations such as **GDPR (Regulation (EU) 2016/679)** could lead to **legal disputes** |

## Three specific security risks
1. **LLM-powered test infrastructure can be vulnerable to security attacks** — data breaches,
   unauthorized access.
2. **Malicious actors can exploit vulnerabilities in LLMs** — manipulative attacks — to
   **alter their behavior or extract sensitive information**.
3. **Attackers can intentionally introduce malicious input data** to mislead LLMs and
   **compromise their accuracy or security**.

---

# STEP 6 — The four attack vectors (GenAI-3.2.2, K2 — learn the table)

| Attack vector | Description | Syllabus example |
|---|---|---|
| **Context manipulation** | Sending requests designed to **extract confidential training data** | **Exceeding the LLM contextual window with long prompts** to overload the AI's memory, leading it to **reveal random snippets of its training data** |
| **Request manipulation** | **Introducing data that disrupts the AI's output** | **Images that lure the AI into a different context**, provoking hallucinations on e.g. acceptance criteria |
| **Data poisoning** | **Manipulating training data** | **Providing fake evaluations when rating** the results of an AI-generated test report |
| **Malicious code generation** | Manipulating an LLM to **generate backdoors** (e.g. external command calls) during use | Generation of code to **open a communication channel with a specific, malicious IP** |

### 🧠 Discriminators
- **Context manipulation → overload the context window to EXTRACT training data**
- **Request manipulation → corrupt the INPUT to disrupt the OUTPUT**
- **Data poisoning → corrupt the TRAINING data**
- **Malicious code generation → the OUTPUT itself is the weapon (backdoor)**

⚠️ Note that **context manipulation is a listed keyword** for this chapter — so its definition is
directly examinable at K1.

---

# STEP 7 — Mitigation strategies (GenAI-3.2.3, K2)

> Opening point: "Data protection regulations like GDPR **do not restrict the applications of
> GenAI explicitly** but **do provide safeguards that may limit what can be done**, particularly
> regarding **lawfulness and limitations on purposes of collection, processing, and storage**."
> ⚠️ Trap: an option saying "GDPR prohibits the use of GenAI in testing" is **wrong**.

## Core data privacy measures (4)
| Measure | Detail |
|---|---|
| **Data minimization** | Avoid processing sensitive data unless legally permitted; use **only the necessary amount of non-sensitive data** |
| **Data anonymization and pseudonymization** | **Masking or replacing sensitive information with non-identifiable data** |
| **Secure data storage and transmission** | **Strong encryption and access controls** |
| **Resources training** | Clear **training programs and policies** for responsible use, ethical practices, risk mitigation |

## Additional mitigation strategies (5)
| Strategy | Detail |
|---|---|
| **Systematic review of the generated output** | "**Human evaluation is essential** for ensuring quality and accuracy" |
| **Evaluation by comparison with another LLM** | Use several LLMs on a task and **compare their responses** |
| **Choice of a secure, operational environment** | Three options by confidentiality level: (1) **commercial secure offering from an LLM provider**, (2) **operate the LLM in a secure cloud**, (3) **install the LLM in the organization's own infrastructure** |
| **Regular security audits and vulnerability assessments** | Identify and address weaknesses |
| **Staying updated with security best practices** | Keep current with guidelines and technologies |

> **Two closing points:** the strategies are **complementary — a combination is required**. And it
> is **highly recommended to involve senior Security Engineers, Legal counsel, the CTO, or the
> CISO** if present in the organization.

---

# STEP 8 — Energy and environment (GenAI-3.3.1, K2)

The LO is: explain the impact of **task characteristics and model usage** on energy consumption.

| Point | Detail |
|---|---|
| **What drives consumption** | **The complexity of the task and the computational resources required** |
| **Where the load falls** | LLMs are **web-based services**; use increases load on **devices, networks, and data centers** |
| **The comparison to remember** | Generating **a single image** can consume **as much energy as fully charging a smartphone**; generating **text** consumes only **a small percentage of a smartphone's charge** |
| **Scale effect** | A single task seems negligible, but the **cumulative effect across millions of users results in substantial environmental strain** → significant **CO₂ emissions** |
| **Data quality caveat** | It is **hard to get accurate data** on the environmental impact of GenAI |
| **Best practice** | **Limiting unnecessary model interactions** is critical to mitigating environmental risk |

🧠 **Image ≫ text.** That contrast is the most likely question in this section.
(Chapter 5.2.1 adds: **select right-sized models** and optimize usage patterns.)

---

# STEP 9 — Regulations, standards and frameworks (GenAI-3.4.1, K1 — easy mark)

**Four items. Learn the *type* of each — that is the most common question form.**

| Name | **Type** | Description | Application in software testing |
|---|---|---|---|
| **ISO/IEC 42001:2023** — *Information technology — Artificial intelligence — Management system* | **Standard** | Specifies requirements for **managing AI systems within an organization** | Promotes that GenAI in testing **adheres to recommended practices**, promoting **consistency and reliability** |
| **ISO/IEC 23053:2022** — *Framework for AI Systems Using Machine Learning* | **Standard** | Provides a framework for **AI lifecycle processes**, emphasizing **safety and transparency** | Framework for **data quality, transparency and safety** when using GenAI for testing |
| **EU AI Act** | **Regulation** | Legal framework addressing AI risks, **classifying applications by risk level** | Mandates compliance in **transparency, accountability, and bias mitigation** |
| **NIST AI Risk Management Framework (US)** | **Framework** | Guidelines for managing AI risks, focusing on **fairness, transparency, and security** | Supports **fairness** and **prevents biased test results** |

### 🧠 Memory hooks
- **42001 = "manage"** (management system — the 4 looks like a filing cabinet)
- **23053 = "lifecycle + ML"**
- **EU AI Act = the only REGULATION** (it is law) — and the only one that **classifies by risk level**
- **NIST = the US FRAMEWORK** — fairness/bias

> **Closing sentence:** test organizations must **stay updated** as AI technologies and regulatory
> landscapes continue to evolve.

⚠️ Remember from the syllabus introduction: **standards documents themselves are not examinable**
— only what is summarised in the syllabus, i.e. exactly the table above.

---

# ⚠️ Chapter 3 exam traps

1. **Hallucination = invented; reasoning error = illogical; bias = skewed by training data.**
2. **Bias comes from training data** — not from the prompt, not from temperature.
3. **Reasoning errors happen because LLMs pattern-match instead of truly reasoning.**
4. **You cannot permanently fix these defects** — non-determinism means they can reappear.
5. **Complete reproducibility cannot be guaranteed.** Low temperature reduces *variability*,
   not *error*, and it costs creativity/diversity.
6. **GDPR does not ban GenAI** — it provides safeguards limiting lawfulness and purpose.
7. **Context manipulation ≠ request manipulation.** Context manipulation *extracts training data*
   by overloading the context window.
8. **Data poisoning attacks the training data**, not the prompt.
9. **EU AI Act is a Regulation; NIST AI RMF is a Framework; ISO/IEC items are Standards.**
10. **Images cost far more energy than text.**
11. **Human evaluation is essential** — mitigation is never fully automated.
12. Mitigation strategies are **complementary; a combination is required.**

---

# ✅ Chapter 3 self-check

1. Define hallucination, reasoning error and bias in one line each.
2. Why do LLMs make reasoning errors?
3. Where does LLM bias originate?
4. Name the three hallucination detection methods.
5. Name the two reasoning-error detection methods.
6. What determines how thoroughly you implement detection methods?
7. Name the two techniques for mitigating non-deterministic behaviour, and the cost of the first.
8. What is the defining example of context manipulation?
9. Which attack vector involves manipulating training data?
10. Name the three secure operational environment options.
11. Which single item in the regulations table is a Regulation? Which is a Framework?
12. Which consumes more energy — generating an image or generating text?
13. Which two Chapter 4 techniques are named as complementary ways to improve LLM results?
14. Which roles should be involved for data privacy and security decisions?

<details><summary>Answers</summary>

1. **Hallucination** = output that appears factually incorrect or irrelevant to the task
   (invented). **Reasoning error** = misinterpreting logical structures such as cause-and-effect
   or conditional logic, leading to incorrect conclusions. **Bias** = output favouring certain
   types of information, approaches or assumptions.
2. Because they **lack true logical reasoning and rely on pattern matching**.
3. **The data on which the model was trained.**
4. **Cross-verification, domain expertise consultation, consistency checks.**
5. **Logical validation** and **output testing**.
6. **The estimated risk level** of hallucinations/reasoning errors/biases in that test task.
7. **Lowering the temperature** (cost: **limits creativity and diversity**, outputs become
   repetitive/overly deterministic) and **setting random seeds**.
8. **Exceeding the LLM context window with long prompts** to overload its memory, causing it to
   **reveal random snippets of training data**.
9. **Data poisoning.**
10. **(1)** Commercial secure offering from an LLM provider; **(2)** operate the LLM in a secure
    cloud; **(3)** install the LLM in the organization's own infrastructure.
11. Regulation = **EU AI Act**. Framework = **NIST AI Risk Management Framework**.
    (ISO/IEC 42001 and 23053 are Standards.)
12. **Generating an image** — roughly as much energy as fully charging a smartphone, versus a
    small percentage of a charge for text.
13. **Retrieval-Augmented Generation (RAG)** and **fine-tuning**.
14. **Senior Security Engineers, Legal counsel, the CTO, or the CISO.**
</details>
