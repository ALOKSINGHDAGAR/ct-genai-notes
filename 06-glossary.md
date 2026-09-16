# Glossary — Every Examinable Term

> **Why this file matters:** the syllabus states that *"All terms listed as keywords just below
> chapter headings **shall be remembered, even if not explicitly mentioned in the learning
> objectives**."* This is where most of the **8 K1 questions (8 points)** come from.
>
> Definitions below are the official ISTQB CT-GenAI v1.1 Appendix D wordings, condensed.

---

## How to use this file

1. **First pass:** read the whole table.
2. **Second pass:** cover the right column and recall the definition from the term.
3. **Third pass:** cover the *left* column and name the term from the definition — this is how
   ISTQB actually asks it ("Which of the following best describes…?").

---

# A–F

| Term | Definition | Chapter |
|---|---|---|
| **AI chatbot** | A **conversational agent** that uses LLMs to process queries and generate human-like text responses, enabling **interactive communication** with users. | 1 |
| **Bias** | Output that **favours certain types of information, approaches or assumptions**, originating from **the data the model was trained on**. | 3 |
| **Context manipulation** | An attack vector: sending requests designed to **extract confidential training data** (e.g. **exceeding the context window with long prompts** to overload the model's memory). | 3 |
| **Context window** | The **span of text, measured in tokens**, that a language model **considers when generating responses**, influencing the **relevance and coherence** of its outputs. | 1 |
| **Deep learning** | **ML using neural networks with multiple layers.** | 1 |
| **Embedding** | A technique to represent **tokens as dense vectors in a continuous space**, learned during training to capture **semantic, syntactic and contextual relationships**. | 1 |
| **Feature** | An **individual measurable attribute of the input data** used for training by an ML algorithm and for prediction by an ML model. | 1 |
| **Few-shot prompting** | A technique where the model is given **a few examples within the prompt** to guide it in generating appropriate responses. *(More than one example.)* | 2 |
| **Fine-tuning** | A **supervised learning process** using a **dataset of labeled examples** to **update LLM weights** and adapt them for specific tasks or domains. | 4 |
| **Foundation LLM** *(syn. **Base LLM**)* | **General-purpose models pre-trained on a wide range of text data**, capable of **predicting the next word** based on learned linguistic patterns. | 1 |

# G–L

| Term | Definition | Chapter |
|---|---|---|
| **Generative AI (GenAI)** | A type of AI system that uses ML models to **generate (new) intellectual content that resembles human-created content**. | 1 |
| **Generative pre-trained transformer (GPT)** | A type of **transformer-based deep learning model pre-trained on vast amounts of text data** to understand and generate human-like text. | 1 |
| **Hallucination** | **Wrong information created by an LLM.** *(In testing: fictitious/irrelevant test cases, non-functioning scripts, criteria that do not exist.)* | 3 |
| **Instruction-tuned LLM** | **A foundation LLM trained to follow instructions**, often reinforced by feedback to encourage correct answers. *(Also called "non-reasoning".)* | 1 |
| **Large language model (LLM)** | A computer program that uses **very large collections of language data** to understand and produce text **in a way similar to humans**. | 1 |
| **LLM-powered agent** | An application that integrates **LLM reasoning, decision-making, and memory, using tools to perform tasks**. | 4 |
| **LLMOps** (Large Language Model Operations) | **Practices and tools focused on deploying, monitoring, and maintaining LLMs in production environments.** | 4 |

# M–P

| Term | Definition | Chapter |
|---|---|---|
| **Machine learning (ML)** | The process using **computational techniques to enable systems to learn from data or experience**. *(ISO/IEC TR 29119-11)* | 1 |
| **Meta prompting** | The crafting of **higher-level instructions that generate specific prompts** for exploring or automating capabilities. *(The LLM writes the prompt.)* | 2 |
| **Multimodal model** | GenAI models capable of **processing and generating content across multiple data types** — text, images, audio. | 1 |
| **Natural language processing (NLP)** | The **processing of data encoded in natural language** by computers, to retrieve information and for knowledge representation. | 2 |
| **One-shot prompting** | A prompt writing technique where the prompt contains **one example** to guide the LLM's response. | 2 |
| **Prompt** | A **natural language input** provided to elicit a specific response in GenAI and LLMs. | 2 |
| **Prompt chaining** | A technique that involves **using the output of one prompt as the input for another**, creating a **sequence of prompts**. | 2 |
| **Prompt engineering** | The process of **designing and refining input prompts** to guide LLMs toward producing desired outputs. | 2 |
| **Prompt pattern** | A **reusable template for crafting effective prompts** to guide GenAI toward **consistent and reliable outputs**. | 5 |

# R–Z

| Term | Definition | Chapter |
|---|---|---|
| **Reasoning error** | **Misinterpretation of logical structures** (cause-and-effect, conditional logic, step-by-step problem-solving) leading to incorrect conclusions, because LLMs **rely on pattern matching rather than true logical reasoning**. | 3 |
| **Reasoning LLM** | An LLM **building upon instruction-tuned models** by refining their ability to **emulate human-like reasoning processes**. | 1 |
| **Retrieval-augmented generation (RAG)** | A technique **combining LLM capabilities with a retriever** to **fetch relevant data** for generating accurate, contextually relevant responses. | 4 |
| **Shadow AI** | The use of GenAI tools or systems within an organization **without formal approval or oversight**. | 5 |
| **Small language model (SLM)** | Language models **intentionally designed and trained to be small**, offering a **balance between efficiency and task-specific language understanding**. | 1 |
| **Symbolic AI** | An AI approach that uses **symbols, rules, and structured knowledge to model reasoning**. | 1 |
| **System prompt** | A **predefined instruction set, typically hidden from the chatbot's users**, that consistently establishes the **context, tone, and boundaries** for an LLM's responses and **guides its behavior throughout interactions**. | 2 |
| **Temperature** | A parameter that **controls the randomness or creativity** of an LLM's outputs. | 3 |
| **Tokenization** | The process of **breaking down text into smaller units** for processing by language models. | 1 |
| **Transformer** | A deep learning model architecture that utilizes **self-attention mechanisms** to capture **long-range dependencies** in input sequences. | 1 |
| **User prompt** | An **instruction or query entered by a user** into an LLM that **directs the model's response** to fulfil specific tasks or provide desired information. | 2 |
| **Vector database** | A database **optimized for storing and querying high-dimensional vector representations** of data. | 4 |
| **Vision-language model** | A GenAI system that **jointly processes visual and textual data** to perform tasks by **linking and generating content across both modalities**. | 1 |
| **Zero-shot prompting** | A prompt writing technique where the prompt contains **no examples**, relying on the **model's pre-existing knowledge**. | 2 |

---

# Testing terms carried over from CTFL (also listed as chapter keywords)

You are expected to already know these from Foundation Level. They appear as chapter keywords, so
refresh them.

| Term | Reminder | Chapter |
|---|---|---|
| **acceptance criteria** | The criteria a component/system must satisfy to be accepted by a user, customer or other stakeholder. | 2 |
| **test case** | A set of preconditions, inputs, actions, expected results and postconditions. | 2 |
| **test condition** | A testable aspect of a component or system identified as a basis for testing. | 2 |
| **test data** | Data needed for test execution. | 2 |
| **test design** | Elaborating and refining **test conditions into test cases** and other testware. | 2 |
| **test report** | Documentation summarizing test activities and results. | 2 |
| **test script** | A sequence of instructions for the execution of a test. | 2 |
| **data privacy** | Protection of personal/sensitive data from unauthorized access or disclosure. | 3 |
| **security** | Protection against unauthorized access to, or modification of, a component or system. | 3 |
| **vulnerability** | A weakness that can be exploited to cause a security breach. | 3 |
| **test infrastructure** | The organizational artifacts needed to perform testing (environments, tools, facilities). | 4 |

---

# ⚡ The 12 most confusable pairs — drill these

| A | B | The discriminator |
|---|---|---|
| **Zero-shot** | **One-shot** vs **Few-shot** | **0** examples / **1** example / **more than one** |
| **Prompt chaining** | **Meta prompting** | Chaining = **multi-step with verification**. Meta = **LLM writes the prompt** |
| **System prompt** | **User prompt** | System = **hidden, constant, set by developer/tester**. User = **visible, changes each turn** |
| **Hallucination** | **Reasoning error** | Invented content vs **faulty logic** |
| **Reasoning error** | **Bias** | Faulty logic vs **systematic skew from training data** |
| **RAG** | **Fine-tuning** | RAG **retrieves at runtime, no weight change**. Fine-tuning **updates weights** |
| **Relational DB** | **Vector DB** | Structured test data vs **semantic retrieval via embeddings** |
| **AI chatbot** | **LLM-powered agent** | Chatbot **answers**. Agent **acts, using tools** |
| **Autonomous agent** | **Semi-autonomous agent** | Minimal human intervention vs **periodic human oversight** (use for critical tasks) |
| **Classical ML** | **Deep learning** | **Humans select features** vs **model learns features** |
| **Foundation LLM** | **Instruction-tuned LLM** | Raw, **needs further adaptation** vs **trained to follow instructions** |
| **Accuracy** | **Precision** vs **Recall** | Overall correctness vs correctness **for a specific objective** vs **finding all relevant instances** |

---

# ⚡ Numbers to memorise

| Number | What it is |
|---|---|
| **6** | Components of a structured prompt (Role, Context, Instruction, Input data, Constraints, Output format) |
| **3** | Core prompting techniques (chaining, few-shot, meta) |
| **7** | Metrics for evaluating GenAI results |
| **5** | Techniques for evaluating/refining prompts |
| **3** | Defect types (hallucination, reasoning error, bias) |
| **4** | Attack vectors (context manipulation, request manipulation, data poisoning, malicious code generation) |
| **4** | Regulations/standards/frameworks (ISO 42001, ISO 23053, EU AI Act, NIST AI RMF) |
| **4** | Fine-tuning challenges (bias, overfitting, opacity, computational resources) |
| **3** | LLMOps deployment approaches |
| **3** | Shadow AI risks (security/privacy, compliance, IP) |
| **4** | LLM/SLM selection criteria (performance, fine-tuning potential, cost, community) |
| **3** | Adoption phases (Discovery, Initiation and usage definition, Utilization and iteration) |
| **2** | RAG runtime steps (Retrieval, Generation) |
| **256–512** | Tokens per RAG chunk |
| **7** | Key LLM capabilities for test tasks |
| **40 / 46 / 30 / 60** | Exam questions / points / pass mark / minutes |
