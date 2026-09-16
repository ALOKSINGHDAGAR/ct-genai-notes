# Chapter 5 — Deploying and Integrating Generative AI in Test Organizations

> **Exam weight: 7 questions, 7 points (15%) — 4×K1, 3×K2, 0×K3**
> Teaching time: only 80 minutes — the **shortest** chapter, but worth the **same 7 points as
> Chapter 1** (which gets 100 minutes).
>
> ## 💰 THIS IS THE BEST POINTS-PER-MINUTE CHAPTER IN THE EXAM
> **4 of the 8 K1 questions in the whole exam come from here** (LOs 5.1.1, 5.1.4, 5.2.2, 5.2.3).
> K1 = pure recall. Memorise the lists below and you bank 4 points for very little effort.
> Do not skip this chapter because it looks like "soft" management content.

## Learning objectives

| LO | K | Objective | Effort |
|---|---|---|---|
| GenAI-5.1.1 | **K1** | **Recall** the risks of **shadow AI** | Memorise 3 risks |
| GenAI-5.1.2 | K2 | **Explain** key aspects of a GenAI **strategy** for software testing | Understand |
| GenAI-5.1.3 | K2 | **Summarize** key criteria for **selecting LLMs/SLMs** | Memorise 4 criteria |
| GenAI-5.1.4 | **K1** | **Recall** key **phases** in adopting GenAI | Memorise 3 phases |
| GenAI-5.2.1 | K2 | **Explain** essential **skills and knowledge** for testers | Understand |
| GenAI-5.2.2 | **K1** | **Recall** strategies for **cultivating AI skills** in test teams | Memorise |
| GenAI-5.2.3 | **K1** | **Recognize** how **test processes and responsibilities shift** | Memorise |

## Keywords

**Testing terms:** none
**GenAI term:** **shadow AI**

---

# STEP 1 — Shadow AI (GenAI-5.1.1, **K1** — free mark)

**Definition (memorise verbatim):**
> "The use of GenAI tools or systems within an organization **without formal approval or oversight**."

## The three risks — memorise all three

| Risk | Detail |
|---|---|
| **Information security and data privacy weaknesses** | **Personal AI tools may lack robust security**, leading to potential **data breaches** |
| **Compliance and regulatory issues** | Using **unapproved AI tools** can cause **non-compliance with industry standards and regulations**, potentially resulting in **legal consequences** |
| **Vague intellectual property** | AI tools with **unclear licensing agreements** can expose users to **intellectual property disputes**, especially if **copyrighted data is processed without proper authorization** |

🧠 **S-C-I: Security, Compliance, IP.**

> **The solution sentence:** "A **strategy and steps for integrating and deploying GenAI** can help
> test organizations **avoid the risk of shadow AI**."

⚠️ **Trap:** the answer to shadow AI is **not** "ban all AI tools" — it is to provide an
**approved strategy and adoption roadmap**.

---

# STEP 2 — Key aspects of a GenAI strategy (GenAI-5.1.2, K2)

This LO says "Explain the key aspects to consider when **defining a GenAI strategy** for software
testing." Learn the six areas.

| # | Aspect | Detail |
|---|---|---|
| 1 | **Define measurable test objectives for GenAI** | e.g. **increasing test productivity, shortening test cycles, improving test quality** |
| 2 | **Select the right LLMs** | Aligned with those test objectives, **compatible with existing test infrastructure**, meeting **system scalability requirements** (see 5.1.3) |
| 3 | **Data quality** | "The effectiveness of LLM-powered testing depends on **accurate, relevant input data**, protected by robust security procedures." **Maintaining high quality input data is key to achieving results that can be trusted to be correct** |
| 4 | **Comprehensive training programs** | So test teams have the **technical AND ethical skills** to use GenAI tools effectively |
| 5 | **Specific metrics** | To **measure the effectiveness of GenAI results** (the Chapter 2.3.1 metrics) |
| 6 | **Process guidelines for compliance and ethics** | Including **rules for the use of sensitive data**, **transparency obligations** (e.g. **what was generated using GenAI**), and **quality gates with review of generated testware** |

⚠️ Note #6's three sub-items — they are very quotable:
**sensitive data rules + transparency about what was AI-generated + quality gates with review.**

🧠 **The strategy starts with measurable objectives** — that is the first thing, and a likely
"what comes first?" question.

---

# STEP 3 — Selecting LLMs/SLMs (GenAI-5.1.3, K2)

**Context first:** there is a wide range of LLMs/SLMs differing in:
- **Functional capabilities** — e.g. **multimodal input, reasoning capabilities**
- **Technical features** — e.g. **context window size**
- **Licensing types** — e.g. **commercial vs open source**

> **The important caveat:** "While **many benchmarks are available** to evaluate LLMs/SLMs for
> tasks such as NLP, code generation or image analysis, **only a few are specifically focused on
> software test tasks**." ⚠️ Likely exam point — you cannot just trust general benchmarks.

## The four selection criteria — memorise

| # | Criterion | Detail |
|---|---|---|
| 1 | **Model performance** | Evaluate performance for the **targeted test tasks** against **the organization's benchmarks**, using metrics such as those in **section 2.3.1** |
| 2 | **Fine-tuning potential** | Whether it is **possible and useful to fine-tune** with **domain-specific data** to increase **accuracy and relevance in specialized contexts** |
| 3 | **Recurring cost** | **Licensing fees and operational expenses** — must fit the organization's **budget for the targeted test tasks** |
| 4 | **Community and support** | **Active community support and detailed documentation** to aid **implementation and troubleshooting** |

🧠 **P-F-C-C: Performance, Fine-tuning, Cost, Community.**

*(The linked hands-on exercise estimates recurring cost from: number of **input and output
tokens**, the **prompts used**, and the **frequency of the task**, comparing at least one
commercial and one open-source-licensed model.)*

---

# STEP 4 — The three adoption phases (GenAI-5.1.4, **K1** — free mark)

**Memorise the names, the order, and one activity from each.**

| Phase | Name | Focus | Activities |
|---|---|---|---|
| **1** | **Discovery** | **Awareness and capability building** | **Training test teams on GenAI concepts**, **providing access to LLMs/SLMs**, **experimenting with initial use cases** to familiarize testers and **build confidence** |
| **2** | **Initiation and usage definition** | **Identifying and prioritizing practical use cases** | **Evaluating LLM-powered test infrastructure**, **developing expertise**, **ensuring alignment with the organization's needs** |
| **3** | **Utilization and iteration** | **Full integration into test processes** | **Continuous monitoring** of progress and related tools; **measurement and management of the transformation** to ensure **sustainable benefits and scalability** |

🧠 **D → I → U: Discover, Initiate, Utilize.**

## Two crucial closing points (high exam probability)
1. > "These phases **can run in parallel for different use cases**. For example, **test report
   > analysis may be further along the roadmap while test automation is in the early phases**."
   ⚠️ **They are NOT strictly sequential across the organization.** An option saying each phase
   must be fully completed before the next begins is **wrong**.
2. > "It's also important to **recognize and address early concerns such as fear of job
   > displacement**, which can **impact adoption and team morale**."

---

# STEP 5 — Essential skills and knowledge (GenAI-5.2.1, K2)

The LO is "Explain the essential skills and knowledge areas required for testers to work
effectively with generative AI."

## Skills
- **Mastering prompt engineering techniques**
- **Understanding model context windows**
- **Developing test review methods**
- **Combining domain and test expertise with AI skills**

## Key competencies
- **Assessing LLM capabilities**
- **Understanding prompt refinement techniques**
- **Evaluation of AI-generated testware**

## Essential knowledge
- The **inherent risks of GenAI** + awareness of **common mitigation strategies**
- **Data security implications of sharing testware with LLMs**
- **Data sanitization** — "**removing or masking sensitive, personal, or confidential information**"
- **Data privacy-preserving prompt engineering practices**

## Environmental considerations
- **Optimizing model selection and usage patterns** to reduce computational overhead
- **Selecting right-sized models for test tasks**
- **Balancing the benefits of GenAI automation with the impact on cost and energy consumption**

> **The framing sentence:** "Testers must **combine domain and test expertise with AI skills**."
> ⚠️ AI skills **supplement** testing expertise — they do not replace it. Any option suggesting
> testers no longer need traditional testing competence is wrong.

---

# STEP 6 — Building capabilities in test teams (GenAI-5.2.2, **K1** — free mark)

> "A **hands-on approach is essential** to strategically train test teams in GenAI for testing."

## The strategies to recall
| Strategy | Detail |
|---|---|
| **Practising with various LLMs/SLMs** | Not just one model |
| **Following structured learning paths** | — |
| **Gradually developing know-how through sharing** within the organization | — |
| **Guided exercises, peer learning, gradual integration** into daily test tasks | The focus is on **developing practical skills** |
| **Internal communities of practice** | Support **ongoing knowledge sharing**, with **regular meetings** to **highlight successful GenAI applications, discuss challenges, and refine best practices** |

## The progression
> "Test team members progress **from mastering basic prompt creation to using more focused
> techniques, such as test-specific prompts.**"

## ⭐ Definition you must know
**Prompt pattern** = "a **reusable template for crafting effective prompts** to guide GenAI toward
**consistent and reliable outputs**."

Communities of practice promote continuous improvement by **sharing prompt pattern libraries** and
**documenting lessons learned** across projects and domains.

🧠 **Hands-on > theory. Communities of practice + prompt pattern libraries.**

---

# STEP 7 — How roles evolve (GenAI-5.2.3, **K1** — free mark)

> "The integration of GenAI **transforms the traditional test processes of testers and test
> managers** within test organizations."

## The tester
| From | To |
|---|---|
| **Test design and test execution specialists** | **AI-assisted test specialists** |

Combining **expertise in test techniques** with **skills to guide and verify AI-generated testware**.

**Expanded tasks:**
1. **Review of the overall AI-based output**
2. **Prompt refinement**
3. **Maintenance of test-specific prompt libraries**

## The test manager
**Updated responsibilities:**
1. **Development of an AI-based test strategy**
2. **AI-based risk management**
3. **Monitoring and control of AI-based test processes**

**Focus areas:**
- **Balancing human and AI capabilities**
- **Establishing AI governance frameworks for use cases**
- **Ensuring teams maintain BOTH traditional testing competencies AND AI literacy**

> **The headline sentence — highly quotable:**
> "Test managers will **not only lead human testers but also coordinate with GenAI-powered test
> agents**, requiring **new management skills for overseeing hybrid teams of people and GenAI tools**."

🧠 **Tester = guide + verify. Manager = strategy, risk, governance, hybrid teams.**

---

# ⚠️ Chapter 5 exam traps

1. **Shadow AI = used without formal approval or oversight.** Risks: **security/privacy,
   compliance, IP**.
2. **The cure for shadow AI is a strategy and roadmap**, not prohibition.
3. **Adoption phases can run in parallel for different use cases.**
4. **Strategy begins with measurable test objectives.**
5. **Few benchmarks target software test tasks specifically** — don't rely on general benchmarks.
6. **Testers must keep traditional testing competence** and add AI literacy — never replace.
7. **Fear of job displacement must be actively addressed** — it is in the syllabus.
8. **Prompt pattern = reusable template.** Know this definition.
9. **Test managers coordinate hybrid teams** of humans and GenAI agents.
10. **Training must cover technical *and ethical* skills.**
11. **Transparency obligations** include disclosing **what was generated using GenAI**.

---

# ✅ Chapter 5 self-check

1. Define shadow AI and name its three risks.
2. What prevents shadow AI?
3. Name three measurable test objectives a GenAI strategy might set.
4. What three things must process guidelines cover?
5. Name the four criteria for selecting an LLM/SLM.
6. Why can't you rely on published LLM benchmarks for test tasks?
7. Name the three adoption phases in order, with the focus of each.
8. Can the adoption phases overlap?
9. What human concern does the syllabus say must be addressed early?
10. What is data sanitization?
11. Define a prompt pattern.
12. What supports ongoing knowledge sharing in test teams?
13. Name the three expanded tasks of the tester.
14. Name the three updated responsibilities of the test manager.

<details><summary>Answers</summary>

1. **The use of GenAI tools or systems within an organization without formal approval or
   oversight.** Risks: **(1)** information security and data privacy weaknesses,
   **(2)** compliance and regulatory issues, **(3)** vague intellectual property.
2. **A strategy and steps for integrating and deploying GenAI** (an approved adoption roadmap).
3. **Increasing test productivity, shortening test cycles, improving test quality.**
4. **Rules for the use of sensitive data**, **transparency obligations** (what was generated using
   GenAI), and **quality gates with review of generated testware**.
5. **Model performance, fine-tuning potential, recurring cost, community and support.**
6. Because **only a few benchmarks are specifically focused on software test tasks** — you must
   evaluate against **the organization's own benchmarks** for the targeted tasks.
7. **(1) Discovery** — awareness and capability building; **(2) Initiation and usage definition** —
   identifying and prioritizing practical use cases; **(3) Utilization and iteration** — full
   integration, continuous monitoring and management of the transformation.
8. **Yes** — they **can run in parallel for different use cases**.
9. **Fear of job displacement**, which can impact adoption and team morale.
10. **Removing or masking sensitive, personal, or confidential information.**
11. **A reusable template for crafting effective prompts** to guide GenAI toward **consistent and
    reliable outputs**.
12. **Internal communities of practice**, with regular meetings and **shared prompt pattern
    libraries**.
13. **Review of the overall AI-based output, prompt refinement, and maintenance of test-specific
    prompt libraries.**
14. **Development of an AI-based test strategy, AI-based risk management, and monitoring and
    control of AI-based test processes.**
</details>
