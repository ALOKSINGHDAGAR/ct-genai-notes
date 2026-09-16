# Practice Questions

> **Part A** is a **full 40-question mock exam** that mirrors the official blueprint exactly:
>
> | Chapter | Questions | K1 | K2 | K3 | Points |
> |---|---|---|---|---|---|
> | 1 | 7 | 1 | 6 | 0 | 7 |
> | 2 | 11 | 0 | 6 | 5 | 16 |
> | 3 | 10 | 3 | 6 | 1 | 11 |
> | 4 | 5 | 0 | 5 | 0 | 5 |
> | 5 | 7 | 4 | 3 | 0 | 7 |
> | **Total** | **40** | **8** | **26** | **6** | **46** |
>
> K3 questions are marked **[K3 — 2 pts]**. Everything else is worth 1 point.
> **Pass = 30 / 46.** Give yourself **60 minutes** for Part A to simulate the real thing.
>
> **Part B** adds 23 extra drill questions on the most confusable points.

---

# PART A — Full mock exam (40 questions, 46 points)

## Chapter 1 (7 questions, 7 points)

**Q1.** Which type of AI requires data preparation, feature selection and model training?
- a) Symbolic AI
- b) Classical machine learning
- c) Deep learning
- d) Generative AI

**Q2.** What does an LLM predict during inference?
- a) The most factually correct answer from its knowledge base
- b) The next token in a sequence
- c) The user's intent, before selecting a stored response
- d) The probability that the prompt is valid

**Q3.** Which statement about the context window is correct?
- a) A larger context window always improves output quality at no cost
- b) The context window is measured in words
- c) Increasing the tokens in the context window increases computational complexity and processing time
- d) The context window determines how many examples a few-shot prompt may contain

**Q4.** Which is the correct relationship between LLM types?
- a) Reasoning LLMs are pre-trained first, then reduced to instruction-tuned LLMs
- b) Instruction-tuned LLMs are derived from foundation LLMs; reasoning LLMs extend instruction-tuned LLMs
- c) Foundation LLMs are derived from instruction-tuned LLMs by removing task alignment
- d) Instruction-tuned and reasoning LLMs are two independent types of foundation LLM

**Q5.** A tester supplies a GUI screenshot together with the related user story and asks the model
to report differences between them. Which capability is being used?
- a) A symbolic AI rule engine
- b) A multimodal LLM augmented with a vision-language model
- c) Retrieval-augmented generation
- d) A fine-tuned small language model

**Q6.** Which of the following is a key LLM capability for test tasks as listed in the syllabus?
- a) Guaranteeing full requirements coverage without review
- b) Test oracle generation, i.e. generating expected results
- c) Automatically approving test completion criteria
- d) Replacing the test manager's monitoring responsibilities

**Q7.** A test team wants to embed GenAI into their existing automation framework to generate test
data at scale, with customization and scalability. Which interaction model fits best?
- a) An AI chatbot, because it gives immediate conversational responses
- b) An LLM-powered testing application integrated via APIs
- c) A foundation LLM used without adaptation
- d) A symbolic AI expert system

---

## Chapter 2 (11 questions, 16 points)

**Q8.** Which of the following is **not** one of the six components of a structured prompt?
- a) Constraints
- b) Output format
- c) Examples
- d) Input data

**Q9.** A prompt contains two worked examples showing the exact format required. This is:
- a) Zero-shot prompting
- b) One-shot prompting
- c) Few-shot prompting
- d) Meta prompting

**Q10.** Which statement about system prompts is correct?
- a) It is written by the chatbot user and changes with each interaction
- b) It sets the temperature and random seed for the session
- c) It stays constant throughout the session and is typically not visible or editable by the user
- d) It must contain the input data for the test task

**Q11. [K3 — 2 pts]** A tester must analyse a user story and refine its acceptance criteria. They
want to first find ambiguities, then assess testability, then assess completeness, checking and
correcting the model's output at each stage. Which approach is most appropriate?
- a) A single zero-shot prompt containing all three questions
- b) Prompt chaining with human verification at each step
- c) Few-shot prompting with three example user stories
- d) Lowering the temperature and re-running the same prompt three times

**Q12. [K3 — 2 pts]** A team must generate test cases from user stories in strict Gherkin
given-when-then format, consistently, for many stories. Which technique is most appropriate?
- a) Meta prompting
- b) Prompt chaining
- c) Few-shot prompting
- d) Zero-shot prompting

**Q13. [K3 — 2 pts]** A test automation engineer wants GenAI to help keep a large GUI regression
suite stable as the UI changes frequently. Which GenAI application addresses this directly?
- a) Test data synthesis
- b) Self-healing and adaptive tests that adjust scripts for dynamic locators and modified interactions
- c) Test completion reporting
- d) Coverage analysis of the test basis

**Q14. [K3 — 2 pts]** A test manager wants GenAI to analyse test progress data from the test
management tool, spot deviations from plan, and recommend reprioritizing tests and reallocating
resources. Which test activities are being supported?
- a) Test analysis and test design
- b) Test implementation and test execution
- c) Test monitoring and test control
- d) Test planning and risk analysis only

**Q15. [K3 — 2 pts]** A tester faces a brand-new task — analysing regression test reports to
cluster anomalies — and is unsure how to phrase an effective prompt. Which technique should they
select first?
- a) Few-shot prompting, because examples always improve output
- b) Meta prompting, to co-create and refine the prompt with the LLM
- c) Zero-shot prompting, to avoid biasing the model
- d) Fine-tuning a small language model on past test reports

**Q16.** Which metric measures the proportion of generated test scripts that can be executed
without syntax errors or output format issues?
- a) Accuracy
- b) Precision
- c) Execution Success Rate
- d) Time Efficiency

**Q17.** Why must metrics for evaluating GenAI results be based on statistically relevant data?
- a) Because ISTQB requires a minimum sample size of 30
- b) Because LLMs are non-deterministic, so a single output is not representative
- c) Because token costs vary between vendors
- d) Because accuracy cannot be measured on small datasets

**Q18.** Which statement about refining prompts is correct?
- a) Adding more context always improves the quality of the response
- b) A/B testing of prompts compares versions against predefined metrics
- c) User feedback should be excluded to avoid subjective bias
- d) Output analysis should only be performed by the model itself

---

## Chapter 3 (10 questions, 11 points)

**Q19.** An LLM generates a test case verifying an acceptance criterion that does not exist in the
user story. This is an example of:
- a) A reasoning error
- b) A hallucination
- c) Bias
- d) Data poisoning

**Q20.** Why are LLMs prone to reasoning errors?
- a) Their training data is always incomplete
- b) They lack true logical reasoning and rely on pattern matching
- c) Their temperature is set too high by default
- d) They cannot process conditional logic in any form

**Q21.** Where does LLM bias originate?
- a) From the prompt structure used by the tester
- b) From the data on which the model was trained
- c) From the non-deterministic sampling at inference time
- d) From the size of the context window

**Q22. [K3 — 2 pts]** A tester reviews LLM-generated testware and finds that non-functional tests
are consistently underrepresented compared with the documented test strategy. Which problem has
been identified, and how?
- a) A hallucination, identified by cross-verification
- b) A reasoning error, identified by output testing
- c) Bias, identified by reviewing whether generated testware represents the defined test strategy and coverage requirements
- d) Non-determinism, identified by repeated execution

**Q23.** Which pair are the mitigation techniques for the non-deterministic behaviour of LLMs?
- a) Retrieval-augmented generation and fine-tuning
- b) Lowering the temperature and setting random seeds
- c) Prompt chaining and few-shot prompting
- d) Data minimization and pseudonymization

**Q24.** What is the trade-off of lowering the temperature?
- a) It increases token cost
- b) It limits creativity and diversity, making outputs more repetitive
- c) It reduces the size of the context window
- d) It prevents the use of multimodal input

**Q25.** An attacker sends extremely long prompts to overload the model's memory, hoping it will
reveal snippets of its training data. This attack vector is:
- a) Request manipulation
- b) Data poisoning
- c) Context manipulation
- d) Malicious code generation

**Q26.** Which statement about GDPR and GenAI in testing is correct?
- a) GDPR explicitly prohibits using GenAI tools for software testing
- b) GDPR does not restrict GenAI applications explicitly but provides safeguards limiting lawfulness and purposes of collection, processing and storage
- c) GDPR applies only to training data, not to prompts
- d) GDPR compliance is achieved automatically by using a commercial LLM provider

**Q27.** Which consumes the most energy?
- a) Generating a short block of text
- b) Generating a single image with a powerful AI model
- c) Tokenizing an input prompt
- d) Storing embeddings in a vector database

**Q28.** Which of the following is a **Regulation** rather than a standard or framework?
- a) ISO/IEC 42001:2023
- b) ISO/IEC 23053:2022
- c) NIST AI Risk Management Framework
- d) EU AI Act

---

## Chapter 4 (5 questions, 5 points)

**Q29.** In an LLM-powered test infrastructure, what does the back end do with the LLM's raw output?
- a) Passes it unchanged to the front-end
- b) Post-processes it so responses align with the test conditions of the test process
- c) Stores it in the vector database as new training data
- d) Uses it to update the model's weights

**Q30.** What are the two runtime steps of Retrieval-Augmented Generation?
- a) Chunking and embedding
- b) Retrieval and generation
- c) Fine-tuning and inference
- d) Tokenization and post-processing

**Q31.** What primarily distinguishes an LLM-powered agent from a traditional AI chatbot?
- a) The agent uses a larger context window
- b) The agent can act by invoking a predefined set of functions, referred to as tools
- c) The agent is always fully autonomous
- d) The agent does not suffer from hallucinations

**Q32.** Which is a challenge of fine-tuning described in the syllabus?
- a) Overfitting, where the model becomes too specialized to the training data
- b) Reduced context window size
- c) Inability to use the model for multimodal input
- d) Loss of the vector database index

**Q33.** Which statement about the three LLMOps deployment approaches is correct?
- a) An organization must select exactly one approach
- b) They are not mutually exclusive and may be implemented simultaneously
- c) In-house development removes the need for data privacy controls
- d) Using a test tool with GenAI capabilities avoids all cost considerations

---

## Chapter 5 (7 questions, 7 points)

**Q34.** Which is **not** one of the three risks of shadow AI?
- a) Information security and data privacy weaknesses
- b) Compliance and regulatory issues
- c) Vague intellectual property
- d) Increased energy consumption

**Q35.** Which are the three phases of adopting GenAI in a test organization?
- a) Planning, execution, completion
- b) Discovery; initiation and usage definition; utilization and iteration
- c) Pilot, rollout, optimization
- d) Awareness, automation, autonomy

**Q36.** Which statement about the adoption phases is correct?
- a) Each phase must be fully completed organization-wide before the next begins
- b) They can run in parallel for different use cases
- c) They apply only to test automation use cases
- d) They replace the test process defined in CTFL

**Q37.** Which is **not** one of the four criteria for selecting an LLM/SLM for test tasks?
- a) Model performance
- b) Fine-tuning potential
- c) Number of parameters in the model
- d) Community and support

**Q38.** What is a prompt pattern?
- a) The order in which the six prompt components appear
- b) A reusable template for crafting effective prompts to guide GenAI toward consistent and reliable outputs
- c) A recurring hallucination observed across prompts
- d) A vendor-specific prompt syntax

**Q39.** How does the tester's role evolve when GenAI is adopted?
- a) Testers stop designing tests and only operate tools
- b) Testers become AI-assisted test specialists, combining test expertise with guiding and verifying AI-generated testware
- c) Testers focus exclusively on prompt engineering
- d) Testers are replaced by semi-autonomous agents for all routine tasks

**Q40.** Which is an updated responsibility of the test manager in an AI-enabled test organization?
- a) Writing all prompts for the test team
- b) Development of an AI-based test strategy and AI-based risk management
- c) Fine-tuning the organization's LLM
- d) Approving every individual LLM response

---

# PART A — ANSWER KEY

<details><summary>Click to reveal answers and explanations</summary>

| Q | Ans | Why |
|---|---|---|
| 1 | **b** | Classical ML is the data-driven approach requiring **data preparation, feature selection and model training**. Deep learning learns features automatically. |
| 2 | **b** | During inference LLMs **predict the next token**, producing text that is statistically plausible — *not necessarily correct*. |
| 3 | **c** | A larger window helps coherence **but increases computational complexity and processing time**. It is measured in **tokens**, not words. |
| 4 | **b** | Foundation → Instruction-tuned (derived from) → Reasoning (extends instruction-tuned). |
| 5 | **b** | Multimodal LLMs augmented with vision-language models let testers **identify discrepancies between expected results and actual visual elements on a screenshot**. |
| 6 | **b** | **Test oracle generation = generating expected results** is one of the seven listed capabilities. (a), (c), (d) all violate the human-verification principle. |
| 7 | **b** | LLM-powered testing applications are **integrated via APIs** and offer **greater customization and scalability**. |
| 8 | **c** | The six are Role, Context, Instruction, Input data, Constraints, Output format. **Examples belong to few-shot prompting — a technique, not a component.** |
| 9 | **c** | More than one example = **few-shot**. One example = one-shot. |
| 10 | **c** | System prompts are **constant across the session** and **not visible or editable by the user** in most interfaces. Temperature/seed are model parameters, not prompt content. |
| 11 | **b** | This is the syllabus's own prompt-chaining exercise: **ambiguities → testability → completeness**, with manual verification at each step. |
| 12 | **c** | Few-shot is recommended for **"repetitive or specific/constrained output format tasks"**, and Gherkin-style test cases are the syllabus's named example. |
| 13 | **b** | **Self-healing and adaptive tests** automatically adjust scripts for **minor UI or API changes**, e.g. **dynamic locators**. |
| 14 | **c** | Spotting deviations from plan = **test monitoring**; reprioritizing and reallocating resources = **test control**. |
| 15 | **b** | Meta prompting is for **flexible, dynamic tasks and crafting prompts for new tasks**; the syllabus names **test report analysis and anomaly detection** explicitly. |
| 16 | **c** | **Execution Success Rate** — artefacts executable **as is**, without syntax errors or format issues. |
| 17 | **b** | "Given the **non-deterministic nature** of GenAI, the metrics **must be based on statistically relevant data**." |
| 18 | **b** | A/B testing evaluates prompt versions **against predefined metrics**. (a) is wrong — sometimes **shorter prompts yield better generalization**. |
| 19 | **b** | Test cases verifying **non-existent acceptance criteria** is the syllabus's own example of a **hallucination**. |
| 20 | **b** | "LLMs **lack true logical reasoning and rely on pattern matching**." |
| 21 | **b** | Bias "**originates from the data on which the model was trained**." |
| 22 | **c** | Bias detection includes **assessing biases related to test types, such as underrepresented non-functional tests**, by reviewing representation of the **test strategy and coverage requirements**. |
| 23 | **b** | Section 3.1.4 gives exactly two: **adjusting temperature** and **setting random seeds**. (a) are Chapter 4 techniques for improving results generally. |
| 24 | **b** | Lower temperature "**will also limit creativity and diversity in responses, making outputs more repetitive or overly deterministic**." |
| 25 | **c** | **Context manipulation** — exceeding the context window to overload memory and extract training data. |
| 26 | **b** | GDPR "does **not restrict the applications of GenAI explicitly** but **does provide safeguards**…". |
| 27 | **b** | A single image can consume **as much energy as fully charging a smartphone**; text uses only a small percentage of a charge. |
| 28 | **d** | The **EU AI Act** is the Regulation. ISO/IEC items are Standards; NIST AI RMF is a Framework. |
| 29 | **b** | "The back end **enhances the LLM's raw output through post-processing**, ensuring its responses **align with the test conditions of the test process**." |
| 30 | **b** | **Retrieval → Generation.** Chunking and embedding happen in **preprocessing**, not at runtime. |
| 31 | **b** | Agents can **"act" by invoking a predefined set of functions, commonly referred to as "tools"**. (c) is wrong — agents may be semi-autonomous. (d) is wrong — they inherit the same problems. |
| 32 | **a** | The four challenges are bias/inaccuracy, **overfitting**, **opacity**, and computational resources. |
| 33 | **b** | "These approaches are **not mutually exclusive** … they **may be implemented simultaneously**." |
| 34 | **d** | The three shadow AI risks are **security/privacy, compliance/regulatory, and vague IP**. Energy is a Chapter 3 topic, not a shadow AI risk. |
| 35 | **b** | **Discovery; Initiation and usage definition; Utilization and iteration.** |
| 36 | **b** | "These phases **can run in parallel for different use cases**." |
| 37 | **c** | The four are **model performance, fine-tuning potential, recurring cost, community and support**. Parameter count is not one of them. |
| 38 | **b** | "A **reusable template for crafting effective prompts** to guide GenAI toward **consistent and reliable outputs**." |
| 39 | **b** | Testers evolve **from test design and execution specialists to AI-assisted test specialists**, combining test technique expertise with **guiding and verifying** AI-generated testware. |
| 40 | **b** | Test manager responsibilities are updated to include **AI-based test strategy, AI-based risk management, and monitoring and control of AI-based test processes**. |

### Score yourself
- **30+ / 46** → you would pass. Review your wrong answers and sit the exam confidently.
- **24–29 / 46** → close. Re-read Chapters 2 and 3 — that is where the points are.
- **< 24 / 46** → work through Chapter 2 (16 pts) and Chapter 5 (4 easy K1 marks) again first.

</details>

---

# PART B — 23 extra drill questions

**B1.** Which prompt component specifies restrictions or special considerations that determine how
instructions are applied to input data?
**B2.** What most distinguishes prompt chaining from simply issuing several prompts in a row?
**B3.** Which evaluation metric is described as "the degree to which generated test cases cover
valid and invalid equivalence partitions of a data class"?
**B4.** Which technique changes the model's weights: RAG or fine-tuning?
**B5.** What chunk size does the syllabus give for RAG preprocessing?
**B6.** Which agent type is recommended for critical test tasks?
**B7.** What is "orchestration"?
**B8.** Name the three hallucination detection methods.
**B9.** What distinguishes Precision from Accuracy in the evaluation metrics?
**B10.** A system prompt typically contains which three of the six prompt components?
**B11.** Which attack vector manipulates the *training* data?
**B12.** What is the synonym for "foundation LLM"?
**B13.** What alternative name does the syllabus give for instruction-tuned LLMs?
**B14.** Which two databases does an LLM-powered test infrastructure back end integrate, and why?
**B15.** Name the three secure operational environment options for running an LLM.
**B16.** Which roles should be involved in GenAI data privacy and security decisions?
**B17.** What is "opacity" in the context of fine-tuning?
**B18.** Which prompting technique is recommended for keyword-driven test automation, and why?
**B19.** What is the first thing a GenAI test strategy must define?
**B20.** What three things must GenAI process guidelines cover?
**B21.** What does "data sanitization" mean?
**B22.** True or false: prompting techniques may be combined for a single use case.
**B23.** Why can't published LLM benchmarks alone guide model selection for testing?

<details><summary>Part B answers</summary>

**B1.** **Constraints** — they "help to specify how instructions should be applied to input data."
**B2.** **The result of each step is checked (manually or automatically) and refined before
proceeding to the next step.**
**B3.** **Recall.**
**B4.** **Fine-tuning** updates weights (supervised learning on labeled examples). **RAG does not** —
it retrieves external data at runtime.
**B5.** **256–512 tokens** — for focused retrieval and compatibility with the context window.
**B6.** **Semi-autonomous** agents — they operate with **periodic human oversight**.
**B7.** The **coordinated effort among multiple AI agents** in a multi-agent architecture, where
several specialized agents communicate and coordinate to solve complex problems.
**B8.** **Cross-verification**, **domain expertise consultation**, **consistency checks**.
**B9.** **Accuracy** = overall correctness against expert-written test cases, requirements or other
standards. **Precision** = correctness **with respect to a specific objective**.
**B10.** **Role, context and constraints** (plus general instructions, e.g. on expected output).
**B11.** **Data poisoning.**
**B12.** **Base LLM.**
**B13.** **Non-reasoning** LLMs.
**B14.** **Relational databases** for **structured data used in testing, such as test cases**;
**vector databases** for **semantic retrieval of related content using embeddings**.
**B15.** **(1)** A commercial, secure offering from an LLM provider; **(2)** operating the LLM in a
secure cloud; **(3)** installing the LLM in the organization's own infrastructure.
**B16.** **Senior Security Engineers, Legal counsel, the CTO, or the CISO.**
**B17.** **Lack of transparency in how an LLM makes its decisions or produces its outputs**, which
**complicates debugging and validation**.
**B18.** **Few-shot prompting** — keyword-driven testing is one of its named applications, because
the task is repetitive with a specific pattern/output format.
**B19.** **Measurable test objectives for GenAI** — e.g. increasing test productivity, shortening
test cycles, improving test quality.
**B20.** **Rules for the use of sensitive data**, **transparency obligations** (what was generated
using GenAI), and **quality gates with review of generated testware**.
**B21.** **Removing or masking sensitive, personal, or confidential information.**
**B22.** **True.** The syllabus explicitly endorses meta prompting → few-shot → prompt chaining.
**B23.** Because **only a few benchmarks are specifically focused on software test tasks** — models
must be evaluated against **the organization's own benchmarks** for the targeted test tasks.

</details>

---

> ⚠️ **Note:** these are practice questions written from the v1.1 syllabus content to drill the
> examinable points. They are not official ISTQB exam questions. If you want official sample
> questions, ISTQB publishes a sample exam set on its website for each syllabus.
