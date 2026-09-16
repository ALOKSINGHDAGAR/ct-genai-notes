# Chapter 1 — Introduction to Generative AI for Software Testing

> **Exam weight: 7 questions, 7 points (15%) — 1×K1, 6×K2, 0×K3**
> Teaching time in syllabus: 100 minutes.
> No K3 here, so nothing to *apply* — this chapter is definitions and understanding.

## Learning objectives (memorise the verbs)

| LO | K | Objective |
|---|---|---|
| GenAI-1.1.1 | K1 | **Recall** different types of AI: symbolic AI, classical ML, deep learning, generative AI |
| GenAI-1.1.2 | K2 | **Explain** the basics of generative AI and large language models |
| GenAI-1.1.3 | K2 | **Distinguish** between foundation, instruction-tuned and reasoning LLMs |
| GenAI-1.1.4 | K2 | **Write and execute** a given prompt addressing a test task using a multimodal LLM |
| GenAI-1.2.1 | K2 | **Give examples** of key LLM capabilities for test tasks |
| GenAI-1.2.2 | K2 | **Compare** interaction models when using GenAI for software testing |

## Keywords you must be able to define (K1 territory)

AI chatbot · context window · deep learning · embedding · feature · foundation LLM ·
generative AI · generative pre-trained transformer (GPT) · instruction-tuned LLM ·
large language model · machine learning · multimodal model · reasoning LLM · symbolic AI ·
tokenization · transformer

---

# STEP 1 — The AI spectrum (GenAI-1.1.1, K1)

This is the classic "which type of AI is this?" question. Learn the **one-line discriminator**
for each.

| Type | One-line discriminator | Testing example |
|---|---|---|
| **Symbolic AI** | **Rules and symbols.** A rule-based system that mimics human decision-making by representing knowledge as symbols and logical rules. | An expert system with hand-written IF-THEN rules |
| **Classical machine learning** | **Data-driven, but you choose the features.** Requires data preparation, **feature selection**, and model training. | Defect categorization; predicting software problems |
| **Deep learning** | **Neural networks that learn the features themselves.** Multiple layers; finds patterns in large complex data (images, video, audio, text) without manually defined features. | Image/pattern recognition |
| **Generative AI** | **Deep learning that creates NEW content** (text, images, code) by learning and mimicking patterns from training data. | LLMs generating test cases |

### The discriminator that wins you the mark
- **Classical ML = humans define the features.**
- **Deep learning = the model learns the features automatically.**
  (Though humans may still be involved in data annotation, model tuning, result validation —
  the syllabus explicitly adds this caveat, so "no human involvement at all" is a wrong option.)
- **GenAI = generates new content**, and is *built on* deep learning.

### Why GenAI is attractive for testing — the key sentence
> "The key advantage of using GenAI for software testing is that it uses **pre-trained models
> that can be applied directly to test tasks without the need for an additional training phase**."

⚠️ …*"although this does come with some risks"* (forward reference to Chapter 3). Exam options
that present GenAI as risk-free are wrong.

**Memory hook — nesting dolls:** AI ⊃ ML ⊃ Deep Learning ⊃ Generative AI. Symbolic AI sits
*outside* the ML branch (it is rules, not learning from data).

---

# STEP 2 — How LLMs actually work (GenAI-1.1.2, K2)

An **LLM** is a GenAI model pre-trained on very large text datasets (books, articles, websites),
based on the **generative pre-trained transformer** architecture.

An **SLM (Small Language Model)** is a compact model with **fewer parameters**, designed for
lightweight and focused GenAI solutions.

## The four concepts you must be able to explain

### 1. Tokenization
Breaking text down into smaller units called **tokens**.
- A token can be **as small as a character or as large as a sub-word or word**.
- The LLM tokenizes input first, so each token is understood individually **while maintaining
  the overall context**.

### 2. Embeddings
**Numerical representations of tokens.** Each token becomes a **vector in a high-dimensional space**.
- They encode **semantic, syntactic and contextual** relationships.
- **Tokens with similar meanings sit close together** in that space.
- This is what lets the LLM understand word relationships and retain context.

> 💡 Tokenization and embeddings together **convert language into a numerical form the model
> can process.** That framing is often the correct answer.

### 3. The transformer model
The neural network architecture behind LLMs. It uses **self-attention** to capture long-range
dependencies, processes the context of extensive text sequences, and learns how tokens relate.

**During inference, the LLM predicts the next token in a sequence.**

> ⚠️ **Learn this sentence verbatim — it is the philosophical core of the whole syllabus:**
> "The transformer model can be used to generate new text that is **statistically plausible**,
> based on training data and the prompt. **But plausible is not necessarily correct.**"

### 4. Non-determinism
> "LLMs exhibit **non-deterministic behavior** primarily due to the **probabilistic nature of
> their inference mechanisms and hyperparameter settings**. This inherent randomness can lead to
> variations in outputs **even when the same input is provided multiple times**."

Remember the *cause*: probabilistic inference + hyperparameters. (Mitigations are Chapter 3.1.4.)

### 5. Context window
> "The amount of **preceding text, measured in tokens**, that the model can consider when
> generating responses."

- **Larger context window** → maintains coherence over longer passages (e.g. analysing large test logs).
- **But**: increasing tokens in the context window **increases computational complexity and
  processing time**.

⚠️ Classic trap: "a larger context window is always better." **No** — there is a
cost/performance trade-off. Nothing in this syllabus is free.

---

# STEP 3 — Three types of LLM (GenAI-1.1.3, K2)

These build on each other in order. Learn the **progression**.

| Type | How it is made | What it is good at | Key phrase |
|---|---|---|---|
| **Foundation LLM** (a.k.a. **Base LLM**) | Pre-trained on vast, diverse data (text, code, images, other modalities) | General-purpose across many domains | "**Typically requires further adaptation** to meet specific task requirements" |
| **Instruction-tuned LLM** | **Derived from foundation models**, fine-tuned on datasets **pairing prompts with expected responses** | Following human instructions; real-world usability | Optimised for "**task adherence, instruction following, and response coherence**" |
| **Reasoning LLM** | **Extends instruction-tuned models**, trained on tasks demanding intermediate reasoning steps | Logical inference, **multi-step problem-solving**, **chain-of-thought** | Best for "**high-cognitive-load tasks**" |

**Memory hook — F → I → R:** **F**oundation is raw, **I**nstruction-tuned obeys,
**R**easoning thinks.

### The exam-relevant conclusion
> "In the context of GenAI applications for software testing, **both instruction-tuned
> (sometimes referred to as non-reasoning) and reasoning LLMs are utilized.**
> **The selection depends on the complexity and reasoning demands of the specific testing task.**"

⚠️ Note the alias: **instruction-tuned = "non-reasoning"**. And note that foundation LLMs are
*not* the ones normally used directly for test tasks.

---

# STEP 4 — Multimodal and vision-language models (GenAI-1.1.4, K2)

**Multimodal LLMs** extend the transformer to process **multiple data modalities: text, images,
sound, and video.**
- Tokenization is **adapted for each data type** — e.g. images are converted into embeddings
  using **vision-language models** before being processed in the transformer.

**Vision-language models** are a **subset of multimodal LLMs** that integrate visual + textual
information. Tasks: **image captioning, visual question answering, analysing consistency between
textual and visual input.**

## Why testers care (likely K2 question)
Multimodal LLMs can analyse:
- **Visual elements**: screenshots, GUI wireframes
- **Associated text**: defect reports, user stories

This allows testers to:
1. **Identify discrepancies between expected results and actual visual elements on a screenshot**
2. **Generate rich, realistic test cases combining textual data and visual cues → increasing coverage**

---

# STEP 5 — What LLMs can do across the test process (GenAI-1.2.1, K2)

The syllabus lists **seven** capabilities. Expect "which of the following is / is not a key LLM
capability for test tasks?"

| # | Capability | What it means |
|---|---|---|
| 1 | **Requirements analysis and improvement** | Identify **ambiguities, inconsistencies, or missing information** in the test basis; **generate meaningful questions** to clarify requirements with stakeholders |
| 2 | **Test case creation support** | Generate test cases; suggest test objectives from requirements/user stories |
| 3 | **Test oracle generation** | Generate **expected results** |
| 4 | **Test data generation** | Generate datasets, **set boundary values**, create combinations of test data |
| 5 | **Test automation support** | Generate test scripts from test case descriptions; improve existing scripts; **identify appropriate test techniques** |
| 6 | **Test result analysis** | Create summaries; **classify anomalies by severity and priority** |
| 7 | **Testware creation** | Create test plans, test reports, defect reports — and **keep them updated as the project evolves** |

**Memory hook — "R-C-O-D-A-R-T":** Requirements, Cases, Oracles, Data, Automation, Results, Testware.

> Framing sentence: LLMs can interpret **requirements, specifications, screenshots, code, test
> cases, and defect reports** — so they help **throughout the whole test process**.

---

# STEP 6 — Two ways to interact with GenAI (GenAI-1.2.2, K2)

This LO says **"Compare"** — so expect a side-by-side comparison question. Learn the contrasts.

| | **AI Chatbot** | **LLM-Powered Testing Application** |
|---|---|---|
| **Interface** | Conversational, natural language | **Integrated via APIs** into test tools/frameworks |
| **Who uses it** | Any tester; **accessible to non-technical stakeholders** | Organizations and tool vendors |
| **Strength** | **Fast feedback**, clarification, dynamic exploration | **Customization and scalability** |
| **Best for** | Routine tasks, **exploratory testing**, **onboarding new testers** | **Automation of repetitive or complex tasks** — test case generation, defect analysis, test data synthesis |
| **Technique used** | **Prompt chaining** to iteratively refine outputs | Embedded GenAI; advanced form = **AI agents** (Chapter 4) |

### The sentence that ties Chapter 1 to Chapter 2
> "**Regardless** of how the tester interacts with LLMs — whether through chatbots or integrated
> LLM-powered applications — successful implementation of generative AI in testing requires
> **strong prompt engineering**."

---

# ⚠️ Chapter 1 exam traps

1. **"Plausible ≠ correct."** Any option claiming LLM output is reliable by nature is wrong.
2. **Bigger context window is not automatically better** — it costs complexity and time.
3. **Classical ML needs feature selection; deep learning learns features automatically.**
4. **Instruction-tuned is derived FROM foundation; reasoning EXTENDS instruction-tuned.** The
   order matters, and foundation models "require further adaptation."
5. **Tokens are not words.** A token can be a character, sub-word, or word.
6. **Embeddings represent tokens**, and similar meanings are *close together* in vector space.
7. **SLM = fewer parameters**, not "less accurate at everything." (Ch.4 shows fine-tuned SLMs
   can be highly effective on specific tasks at lower cost.)
8. **Non-determinism is caused by probabilistic inference + hyperparameters**, not by bugs or
   by bad prompts.

---

# ✅ Chapter 1 self-check

1. Which AI type requires manual feature selection?
2. What does the transformer predict during inference?
3. Give the two-part reason for LLM non-determinism.
4. What is the trade-off of a larger context window?
5. Name the three LLM types in the order they are built.
6. What is another name for a foundation LLM?
7. Which LLM types are actually used for software test tasks?
8. Name four of the seven key LLM capabilities for test tasks.
9. Give two benefits of multimodal LLMs specifically for testing.
10. Which interaction model is best for onboarding a new tester, and why?

<details><summary>Answers</summary>

1. **Classical machine learning** (data preparation, feature selection, model training).
2. **The next token in a sequence** — producing text that is statistically plausible, not
   necessarily correct.
3. **The probabilistic nature of its inference mechanisms** and **hyperparameter settings**.
4. It maintains coherence over longer passages, **but increases computational complexity and
   processing time**.
5. **Foundation → Instruction-tuned → Reasoning.**
6. **Base LLM.**
7. **Instruction-tuned (non-reasoning) and reasoning LLMs** — chosen by the complexity and
   reasoning demands of the task.
8. Any four of: requirements analysis/improvement, test case creation support, test oracle
   generation, test data generation, test automation support, test result analysis, testware creation.
9. (a) Identify **discrepancies between expected results and actual visual elements on a
   screenshot**; (b) generate **richer test cases combining text and visual cues, increasing
   coverage**.
10. **AI chatbot** — its conversational interface gives quick access to testing knowledge and
    practices, and is accessible even to non-technical users.
</details>
