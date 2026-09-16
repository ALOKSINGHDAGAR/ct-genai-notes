# Chapter 5 — Rolling AI Out Across a Test Team

**Worth 7 points out of 46.**
**Seven questions — and four of them are pure recall.**

---

## Why you should not skip this chapter

It looks like soft management waffle. It isn't, for one reason:

**Four of the eight recall questions in the entire exam come from this chapter.**

Recall questions just ask you to remember a list. No reasoning, no scenarios. Learn four short lists
and you bank four points.

And look at the value: Chapter 5 gets **80 minutes** of teaching time but is worth the **same
7 points as Chapter 1**, which gets 100 minutes. **Best points-per-minute in the exam.**

The four recall topics are: **shadow AI risks**, **adoption phases**, **building team skills**, and
**how roles change**. Learn those lists cold.

---

## Topic 1 — Shadow AI (recall — learn this list)

### The definition, word for word

> **Shadow AI:** using GenAI tools in an organisation **without formal approval or oversight.**

In practice: a tester quietly pasting company code into a free AI site on their personal account,
because it makes their job easier and nobody told them not to.

### The three risks

1. **Security and privacy weaknesses** — **personal AI tools may not be secure**, which can lead to
   **data breaches**
2. **Compliance and regulatory problems** — **unapproved tools** can breach industry standards and
   regulations, with possible **legal consequences**
3. **Unclear intellectual property** — tools with **vague licensing** can cause **IP disputes**,
   especially if **copyrighted material gets processed without permission**

**Three words: Security, Compliance, IP.**

### The fix

> A **strategy and a plan for adopting GenAI** stops shadow AI.

⚠️ The answer is **not** "ban AI tools." People use them because they help. Banning just pushes it
further underground. **Give people an approved way to do it.**

---

## Topic 2 — What a GenAI strategy needs

Six things to think about:

**1. Measurable objectives, first.** What are you actually trying to achieve? The syllabus examples:
**more test productivity, shorter test cycles, better test quality.** Measurable — so you can tell
whether it worked.

**2. The right model.** Matched to those objectives, **compatible with your existing test
infrastructure**, and able to **scale**.

**3. Good input data.** The syllabus is firm here: results depend on **accurate, relevant input data,
protected by solid security**. **Good input is what makes the output trustworthy.**

**4. Training programmes.** Teams need **technical *and* ethical skills** — both words matter.

**5. Metrics.** To measure whether the AI is actually delivering (the seven from Chapter 2).

**6. Process guidelines** covering three specific things:
   - **Rules for handling sensitive data**
   - **Transparency obligations — being clear about what was AI-generated**
   - **Quality gates, where generated testware gets reviewed**

That last group of three is very quotable. Learn it.

> **Likely question:** what comes first? **Defining measurable test objectives.**

---

## Topic 3 — Choosing a model

Models differ in:
- **What they can do** — multimodal input, reasoning ability
- **Technical specs** — context window size
- **Licensing** — commercial or open source

### An important warning

> There are **plenty of benchmarks** for things like general language tasks, code generation and
> image analysis — but **very few aimed specifically at software testing tasks**.

So a model topping a general leaderboard tells you little about how it handles *your* test work. You
have to **test it against your own benchmarks**.

### The four selection criteria

1. **Model performance** — on **your** targeted test tasks, against **your** benchmarks, using the
   Chapter 2 metrics
2. **Fine-tuning potential** — could you usefully train it on your domain data?
3. **Recurring cost** — **licence fees plus running costs**, within your budget
4. **Community and support** — **active community and good documentation**, so you can get unstuck

**Four words: Performance, Fine-tuning, Cost, Community.**

*(Cost depends on: number of **input and output tokens**, the **prompts** used, and **how often** you
run the task.)*

---

## Topic 4 — The three adoption phases (recall — learn this list)

| Phase | Name | What happens |
|---|---|---|
| **1** | **Discovery** | **Awareness and capability building** — **train the team on GenAI concepts**, **give them access to models**, **let them experiment** and build confidence |
| **2** | **Initiation and usage definition** | **Identify and prioritise practical use cases** — evaluate infrastructure, develop expertise, make sure it fits what the organisation needs |
| **3** | **Utilization and iteration** | **Full integration** — **continuous monitoring**, measuring and managing the change so benefits last and scale |

**Discovery → Initiation → Utilization.** Roughly: *try it → decide where it helps → embed it.*

### Two closing points that get examined

**They can run in parallel.** The syllabus gives the example: **test report analysis might be fully
embedded while test automation is still at the experiment stage.** You don't finish phase 1
everywhere before starting phase 2.

⚠️ An option saying each phase must complete before the next begins is **wrong**.

**Address the fear.** The syllabus explicitly says to **recognise and deal with worries like fear of
job displacement**, because they **affect adoption and team morale**. It's in the syllabus, so it can
be examined.

---

## Topic 5 — What skills testers need

**Skills:**
- **Prompt engineering**
- **Understanding context windows**
- **Test review methods**
- **Combining domain and testing expertise with AI skills**

**Competencies:**
- **Judging what an LLM can and can't do**
- **Knowing how to refine prompts**
- **Evaluating AI-generated testware**

**Knowledge:**
- **The risks of GenAI** and the **common mitigations**
- **What happens to your data** when you share testware with an LLM
- **Data sanitization** — **removing or masking sensitive, personal or confidential information**
- **Privacy-preserving prompt practices**

**Environmental awareness:**
- **Choosing models and usage patterns that cut computing overhead**
- **Picking right-sized models** — don't use a huge model for a small job
- **Balancing the benefits against cost and energy**

> **The key framing:** testers **combine domain and test expertise with AI skills.**
> AI skills are **added to** testing knowledge, not a replacement for it. Any option saying testers
> no longer need traditional testing skills is wrong.

---

## Topic 6 — Building skills in the team (recall)

> **A hands-on approach is essential.** Reading about it isn't enough.

**What that looks like:**
- **Practising with several different models**, not just one
- **Structured learning paths**
- **Building know-how gradually and sharing it** across the organisation
- **Guided exercises, peer learning, and gradually working AI into daily tasks**
- **Internal communities of practice** — **regular meetings** to **share what worked, discuss
  problems, and refine good practice**

**The progression:** people move **from basic prompt writing to more focused, test-specific
techniques.**

### One definition to memorise

> **Prompt pattern:** a **reusable template for writing effective prompts**, so the AI gives
> **consistent, reliable output**.

Communities of practice **share prompt pattern libraries** and **write down lessons learned** across
projects.

---

## Topic 7 — How roles change (recall)

### The tester

**From:** test design and test execution specialist
**To:** **AI-assisted test specialist**

Still needs all the test technique expertise — plus the ability to **guide and check AI-generated
testware**.

**Three new tasks:**
1. **Reviewing the AI's output overall**
2. **Refining prompts**
3. **Maintaining test-specific prompt libraries**

### The test manager

**Three new responsibilities:**
1. **Developing an AI-based test strategy**
2. **AI-based risk management**
3. **Monitoring and controlling AI-based test processes**

**And three focus areas:**
- **Balancing human and AI capabilities**
- **Setting up AI governance frameworks**
- **Making sure the team keeps both traditional testing skills and AI literacy**

### The headline sentence

> Test managers will **not only lead human testers but also coordinate GenAI-powered test agents** —
> needing **new skills for managing hybrid teams of people and AI tools**.

That phrase — **hybrid teams of people and AI** — is very quotable and likely to appear.

**Short version: the tester guides and verifies. The manager does strategy, risk and governance.**

---

## Traps to watch for

1. **Shadow AI = no formal approval or oversight.** Risks: **security, compliance, IP**.
2. **The cure is a strategy, not a ban.**
3. **Adoption phases can overlap** across different use cases.
4. **Strategy starts with measurable objectives.**
5. **Few benchmarks target testing** — use your own.
6. **Testers keep their testing skills** and add AI literacy.
7. **Fear of job displacement must be addressed** — it's in the syllabus.
8. **Prompt pattern = reusable template.** Know the definition.
9. **Managers coordinate hybrid teams** of humans and AI agents.
10. **Training covers technical *and ethical* skills.**
11. **Transparency means disclosing what was AI-generated.**

---

## Quick self-check

1. Define shadow AI and name its three risks.
2. What prevents shadow AI?
3. Name three measurable objectives a strategy might set.
4. What three things must process guidelines cover?
5. Name the four model selection criteria.
6. Why can't you just trust published benchmarks?
7. Name the three adoption phases and what each involves.
8. Can they overlap?
9. What human worry does the syllabus tell you to address?
10. What is data sanitization?
11. Define prompt pattern.
12. What supports ongoing knowledge sharing?
13. Name the tester's three new tasks.
14. Name the test manager's three new responsibilities.

<details><summary>Answers</summary>

1. **Using GenAI tools without formal approval or oversight.** Risks: **security and privacy
   weaknesses**, **compliance and regulatory issues**, **unclear intellectual property**.
2. **A strategy and plan for adopting GenAI** — an approved route, not a ban.
3. **More test productivity, shorter test cycles, better test quality.**
4. **Rules for sensitive data**, **transparency about what was AI-generated**, and
   **quality gates with review of generated testware**.
5. **Model performance, fine-tuning potential, recurring cost, community and support.**
6. Because **very few benchmarks target software testing tasks** — evaluate against **your own
   benchmarks** for your actual tasks.
7. **Discovery** (awareness and capability building) → **Initiation and usage definition**
   (identify and prioritise use cases) → **Utilization and iteration** (full integration and
   continuous monitoring).
8. **Yes** — they run in parallel for different use cases.
9. **Fear of job displacement**, which affects adoption and morale.
10. **Removing or masking sensitive, personal or confidential information.**
11. **A reusable template for writing effective prompts**, producing **consistent and reliable
    output**.
12. **Internal communities of practice**, sharing **prompt pattern libraries** and lessons learned.
13. **Reviewing overall AI output, refining prompts, maintaining test-specific prompt libraries.**
14. **AI-based test strategy, AI-based risk management, monitoring and control of AI-based test
    processes.**
</details>

---

# Practice questions — Chapter 5

*Twelve questions. The real exam asks **7** from this chapter — **4 recall** and 3 understanding,
all worth 1 point. The recall ones are the cheapest marks in the exam, so get these right.*

**1.** Shadow AI is best defined as:
- a) Using AI tools that run locally rather than in the cloud
- b) Using GenAI tools or systems within an organization without formal approval or oversight
- c) Using an LLM whose training data is undisclosed
- d) Using AI agents that operate without logging

**2.** Which is **not** one of the three risks of shadow AI?
- a) Information security and data privacy weaknesses
- b) Compliance and regulatory issues
- c) Vague intellectual property
- d) Reduced model accuracy

**3.** How does the syllabus say an organisation should address shadow AI?
- a) By prohibiting all GenAI tools
- b) Through a strategy and steps for integrating and deploying GenAI
- c) By restricting GenAI use to the test management team
- d) By fine-tuning an approved in-house model

**4.** What should a GenAI test strategy define first?
- a) The vector database technology
- b) Measurable test objectives, such as increased productivity or shorter test cycles
- c) The fine-tuning dataset
- d) The number of agents to deploy

**5.** Which three areas must GenAI process guidelines cover?
- a) Model size, licensing and hosting region
- b) Rules for sensitive data, transparency obligations, and quality gates with review of generated testware
- c) Temperature, seed value and context window
- d) Recruitment, training budget and tooling spend

**6.** Which is one of the four criteria for selecting an LLM/SLM for test tasks?
- a) The number of parameters
- b) Community and support, including documentation
- c) The country where the model was trained
- d) The size of the vendor's customer base

**7.** Why does the syllabus caution against relying on published LLM benchmarks?
- a) Benchmarks are usually out of date
- b) Only a few benchmarks focus specifically on software test tasks
- c) Benchmarks are proprietary and cannot be cited
- d) Benchmarks only measure energy consumption

**8.** Which sequence gives the three phases of adopting GenAI in a test organization?
- a) Pilot, rollout, optimization
- b) Discovery; initiation and usage definition; utilization and iteration
- c) Awareness, adoption, automation
- d) Planning, monitoring, completion

**9.** During which phase would a team be trained on GenAI concepts, given access to models, and
allowed to experiment with initial use cases?
- a) Discovery
- b) Initiation and usage definition
- c) Utilization and iteration
- d) Test completion

**10.** Which statement about the adoption phases is correct?
- a) Each phase must be completed organization-wide before the next begins
- b) They can run in parallel for different use cases
- c) They apply only to test automation
- d) They must be repeated for every release

**11.** A prompt pattern is:
- a) A recurring error observed in LLM responses
- b) A reusable template for crafting effective prompts to guide GenAI toward consistent and reliable outputs
- c) The prescribed order of the six prompt components
- d) A vendor-specific prompt syntax

**12.** How does the syllabus describe the evolving role of the test manager?
- a) They stop managing people and manage only AI tools
- b) They lead human testers and also coordinate GenAI-powered test agents, requiring new skills for hybrid teams
- c) They become responsible for fine-tuning the organisation's models
- d) They approve every individual LLM response before use

<details><summary>Answers and explanations</summary>

| Q | Ans | Why |
|---|---|---|
| 1 | **b** | The glossary definition — without formal approval or oversight. |
| 2 | **d** | The three risks are security/privacy weaknesses, compliance and regulatory issues, and vague intellectual property. Model accuracy is not among them. |
| 3 | **b** | A strategy and steps for integrating and deploying GenAI helps avoid shadow AI. Prohibition is not the syllabus's answer. |
| 4 | **b** | The strategy begins by defining measurable test objectives — increasing productivity, shortening cycles, improving quality. |
| 5 | **b** | These are the three named items: sensitive data rules, transparency about what was AI-generated, and quality gates with review. |
| 6 | **b** | The four are model performance, fine-tuning potential, recurring cost, and community and support. Parameter count is not one. |
| 7 | **b** | Many benchmarks exist for NLP, code generation and image analysis, but only a few target software test tasks — so evaluate against the organisation's own benchmarks. |
| 8 | **b** | Discovery; Initiation and usage definition; Utilization and iteration. |
| 9 | **a** | Discovery focuses on awareness and capability building — training, access, and experimentation to build confidence. |
| 10 | **b** | The phases can run in parallel for different use cases; the syllabus gives test report analysis being ahead of test automation as its example. |
| 11 | **b** | A reusable template for crafting effective prompts, producing consistent and reliable outputs. |
| 12 | **b** | Test managers will not only lead human testers but also coordinate GenAI-powered test agents, needing new skills for overseeing hybrid teams of people and GenAI tools. |

</details>
