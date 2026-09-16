# Glossary — Every Term, With a Plain-English Version

**This file targets the 8 recall questions (8 points).**

The syllabus says every keyword listed under a chapter heading **must be remembered, even if it
isn't mentioned in the learning objectives**. That's where most recall questions come from.

Each entry has two parts: the **official definition** (what the exam expects), and
**"In plain English"** (so you actually understand it).

---

## How to use this file

**Pass 1:** read straight through. Don't try to memorise — just get familiar.

**Pass 2:** cover the right-hand side. Read the term, say the definition out loud.

**Pass 3:** cover the *left*-hand side. Read the definition, name the term. **This is how ISTQB
actually asks it** — "Which of the following best describes...?"

---

# Chapter 1 terms — AI and how models work

### Symbolic AI
**Official:** An AI approach that uses symbols, rules, and structured knowledge to model reasoning.
**In plain English:** Hand-written rules. IF this, THEN that. It never learns anything.

### Machine learning (ML)
**Official:** The process using computational techniques to enable systems to learn from data or
experience. *(ISO/IEC TR 29119-11)*
**In plain English:** The computer learns patterns from data instead of being given rules.

### Feature
**Official:** An individual measurable attribute of the input data used for training by an ML
algorithm and for prediction by an ML model.
**In plain English:** One piece of information the model looks at. In classical ML, a **human picks**
which ones matter.

### Deep learning
**Official:** ML using neural networks with multiple layers.
**In plain English:** Machine learning where the model **works out for itself** what's worth looking
at.

### Generative AI (GenAI)
**Official:** A type of AI system that uses ML models to generate (new) intellectual content that
resembles human-created content.
**In plain English:** AI that **creates new things** — text, images, code — rather than just
classifying or predicting.

### Large language model (LLM)
**Official:** A computer program that uses very large collections of language data to understand and
produce text in a way similar to humans.
**In plain English:** A program trained on an enormous amount of text until it got very good at
writing.

### Small language model (SLM)
**Official:** Language models intentionally designed and trained to be small, offering a balance
between efficiency and task-specific language understanding.
**In plain English:** A smaller, cheaper model with **fewer parameters**. Lighter — and often good
enough, or better, for one narrow job.

### Tokenization
**Official:** The process of breaking down text into smaller units for processing by language models.
**In plain English:** Chopping text into small pieces called **tokens**. A token can be a whole word,
part of a word, or a single character. **A token is not the same as a word.**

### Embedding
**Official:** A technique used to represent tokens as dense vectors in a continuous space, learned
during training to capture semantic, syntactic, and contextual relationships.
**In plain English:** Turning each token into a list of numbers, so things that **mean similar things
end up close together** on a giant map of meaning.

### Transformer
**Official:** A deep learning model architecture that utilizes self-attention mechanisms to capture
long-range dependencies in input sequences.
**In plain English:** The design under the bonnet. Its job: look at everything so far and **guess the
next token**. Then repeat.

### Generative pre-trained transformer (GPT)
**Official:** A type of transformer-based deep learning model pre-trained on vast amounts of text
data to understand and generate human-like text.
**In plain English:** The specific family of transformer models that LLMs are built on.

### Context window
**Official:** The span of text, measured in tokens, that a language model considers when generating
responses, influencing the relevance and coherence of its outputs.
**In plain English:** How much the model can hold in mind at once. Its desk space. **Bigger means
more coherent, but slower and more expensive.**

### Foundation LLM *(synonym: **Base LLM**)*
**Official:** General-purpose models pre-trained on a wide range of text data, capable of predicting
the next word based on learned linguistic patterns.
**In plain English:** The raw model. Knows a lot, but hasn't been shaped for any particular job —
**it needs further adaptation**.

### Instruction-tuned LLM *(also called "non-reasoning")*
**Official:** A foundation LLM trained to follow instructions, often reinforced by feedback to
encourage correct answers.
**In plain English:** A foundation model trained further on examples of good prompt-and-answer pairs,
so it actually does what you ask.

### Reasoning LLM
**Official:** An LLM building upon instruction-tuned models by refining their ability to emulate
human-like reasoning processes.
**In plain English:** Trained further still, to work through problems step by step. Best for hard,
multi-step tasks.

### Multimodal model
**Official:** GenAI models that are capable of processing and generating content across multiple data
types, such as text, images, and audio.
**In plain English:** It can handle more than text — pictures, sound, video.

### Vision-language model
**Official:** A GenAI system that jointly processes visual and textual data to perform tasks by
linking and generating content across both modalities.
**In plain English:** The part that lets a model understand pictures alongside words — so you can
show it a screenshot and ask what's wrong.

### AI chatbot
**Official:** A conversational agent that uses LLMs to process queries and generate human-like text
responses, enabling interactive communication with users.
**In plain English:** You type, it replies. It **answers** — it doesn't do anything.

---

# Chapter 2 terms — prompting

### Prompt
**Official:** A natural language input provided to elicit a specific response in Generative AI and
large language models.
**In plain English:** What you type in.

### Prompt engineering
**Official:** The process of designing and refining input prompts to guide LLMs toward producing
desired outputs.
**In plain English:** The craft of writing and improving prompts so you get what you actually wanted.

### Natural language processing (NLP)
**Official:** The processing of data encoded in natural language by computers to retrieve information
and for knowledge representation.
**In plain English:** Computers working with ordinary human language.

### Zero-shot prompting
**Official:** A prompt writing technique where the prompt contains no examples, relying on the
model's pre-existing knowledge.
**In plain English:** **No examples.** Just ask.

### One-shot prompting
**Official:** A prompt writing technique where the prompt contains one example to guide the LLM's
response.
**In plain English:** **Exactly one example.**

### Few-shot prompting
**Official:** A technique where a model is given a few examples within the prompt to guide it in
generating appropriate responses.
**In plain English:** **More than one example.** Use it when the output must follow a specific format.

### Prompt chaining
**Official:** A prompting technique that involves using the output of one prompt as the input for
another, creating a sequence of prompts.
**In plain English:** Break the job into steps, **and check each answer before moving on**. That
checking is what defines it.

### Meta prompting
**Official:** The crafting of higher-level instructions that generate specific prompts for exploring
or automating capabilities.
**In plain English:** **Ask the AI to write the prompt for you**, then improve it together.

### System prompt
**Official:** A predefined instruction set, typically hidden from the chatbot's users, that
consistently establishes the context, tone, and boundaries for an LLM's responses and guides its
behavior throughout interactions.
**In plain English:** The standing instruction set once at the start. **Hidden, and it doesn't
change.** Usually holds role, context and constraints.

### User prompt
**Official:** An instruction or query entered by a user into a Large Language Model (LLM) that
directs the model's response to fulfil specific tasks or provide desired information.
**In plain English:** What you type each time. **Visible, and it changes every message.**

---

# Chapter 3 terms — things going wrong

### Hallucination
**Official:** Wrong information created by an LLM.
**In plain English:** It **made something up.** In testing: test cases for features that don't exist,
or criteria that were never in the user story.

### Reasoning error
**Official:** Misinterpretation of logical structures (cause-and-effect, conditional logic,
step-by-step problem-solving) leading to incorrect conclusions.
**In plain English:** **The logic doesn't hold up.** It happens because LLMs **pattern-match instead
of genuinely reasoning**.

### Bias
**Official:** Output that favours certain types of information, approaches or assumptions,
originating from the data the model was trained on.
**In plain English:** It **leans one way**, consistently — because of **what it was trained on**.

### Temperature
**Official:** A parameter that controls the randomness or creativity of an LLM's outputs.
**In plain English:** The creativity dial. Turn it **down** for consistent answers — but you lose
variety, and it **doesn't make answers more correct**.

### Context manipulation
**Official:** An attack vector: sending requests designed to extract confidential training data.
**In plain English:** **Overload the context window with huge prompts** until the model starts
leaking bits of its training data.

---

# Chapter 4 terms — infrastructure

### Retrieval-augmented generation (RAG)
**Official:** A technique combining LLM capabilities with a retriever to fetch relevant data for
generating accurate, contextually relevant responses.
**In plain English:** **Let the AI look things up before answering.** Open-book instead of
closed-book. **Two runtime steps: Retrieval, then Generation.**

### Vector database
**Official:** A database optimized for storing and querying high-dimensional vector representations
of data.
**In plain English:** Where embeddings live. It finds things **by meaning**, not by exact keyword.

### Fine-tuning
**Official:** A supervised learning process using a dataset of labeled examples to update LLM weights
and adapt them for specific tasks or domains.
**In plain English:** **Retraining the model on your own data so it permanently learns your domain.**
Unlike RAG, this **changes the model itself**.

### LLM-powered agent
**Official:** An application that integrates LLM reasoning, decision-making, and memory, using tools
to perform tasks.
**In plain English:** AI that **does things**, not just talks — by calling functions called
**"tools"**. That's the whole difference from a chatbot.

### LLMOps (Large Language Model Operations)
**Official:** Practices and tools focused on deploying, monitoring, and maintaining LLMs in
production environments.
**In plain English:** DevOps, but for language models. How you run this properly in the real world.

---

# Chapter 5 terms — organisation

### Shadow AI
**Official:** The use of GenAI tools or systems within an organization without formal approval or
oversight.
**In plain English:** People quietly using AI tools nobody approved. Risks: **security, compliance,
intellectual property.**

### Prompt pattern
**Official:** A reusable template for crafting effective prompts to guide GenAI toward consistent and
reliable outputs.
**In plain English:** A prompt template your team reuses so everyone gets consistent results.

---

# Testing terms you should already know from Foundation Level

These appear as chapter keywords, so refresh them.

| Term | Reminder |
|---|---|
| **acceptance criteria** | What a system must satisfy to be accepted by a stakeholder |
| **test condition** | A testable aspect of a system, used as a basis for testing |
| **test case** | Preconditions, inputs, actions, expected results, postconditions |
| **test data** | The data you need to run a test |
| **test design** | Turning **test conditions into test cases** and other testware |
| **test script** | A sequence of instructions for running a test |
| **test report** | A summary of test activities and results |
| **data privacy** | Protecting personal and sensitive data from unauthorised access |
| **security** | Protection against unauthorised access or modification |
| **vulnerability** | A weakness that can be exploited to cause a security breach |
| **test infrastructure** | The environments, tools and facilities needed to test |

---

# The 12 pairs people mix up

| These two | Tell them apart by |
|---|---|
| **Zero-shot / one-shot / few-shot** | **0 examples / 1 example / more than one** |
| **Prompt chaining vs meta prompting** | Chaining = **steps with checking**. Meta = **the AI writes the prompt** |
| **System vs user prompt** | System = **hidden and constant**. User = **visible and changes** |
| **Hallucination vs reasoning error** | **Made it up** vs **faulty logic** |
| **Reasoning error vs bias** | **Faulty logic** vs **systematic lean from training data** |
| **RAG vs fine-tuning** | **Looks it up, model unchanged** vs **retrains, model changed** |
| **Relational vs vector database** | **Structured test data** vs **meaning-based search** |
| **Chatbot vs agent** | **Answers** vs **acts, using tools** |
| **Autonomous vs semi-autonomous agent** | **Minimal oversight** vs **periodic human oversight** (use for critical tasks) |
| **Classical ML vs deep learning** | **Humans pick features** vs **model finds features** |
| **Foundation vs instruction-tuned LLM** | **Raw, needs adaptation** vs **trained to follow instructions** |
| **Accuracy / precision / recall** | **Right overall** / **right for one objective** / **found them all** |

---

# Numbers worth memorising

| Number | What it counts |
|---|---|
| **6** | Parts of a structured prompt |
| **3** | Core prompting techniques |
| **7** | Metrics for evaluating AI output |
| **5** | Techniques for refining prompts |
| **3** | Ways output goes wrong (hallucination, reasoning error, bias) |
| **4** | Attack vectors |
| **4** | Regulations, standards and frameworks |
| **4** | Fine-tuning problems |
| **3** | LLMOps deployment approaches |
| **3** | Shadow AI risks |
| **4** | Model selection criteria |
| **3** | Adoption phases |
| **2** | RAG runtime steps |
| **256–512** | Tokens per RAG chunk |
| **7** | Key LLM capabilities for testing |
| **40 / 46 / 30 / 60** | Questions / points / pass mark / minutes |
