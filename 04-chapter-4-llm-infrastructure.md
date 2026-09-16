# Chapter 4 — Building AI Into Your Test Setup

**Worth 5 points out of 46 — the smallest chapter.**
**Five questions, all "understand" level, one per topic. No recall questions, no 2-point scenarios.**

---

## Before you start

This chapter has the most technical-sounding words in the syllabus — RAG, LLMOps, vector databases,
agents — and beginners often panic and over-study it.

Don't. **It's worth 5 points and every question is straightforward understanding.** There are exactly
five topics and exactly one question on each. Read it twice, get the core idea of each, and move on
to Chapter 2.

Here's the whole chapter in five sentences:

1. An AI test tool has a front end, a back end, and an LLM
2. **RAG** = let the AI look things up before answering
3. **Agents** = AI that does things, not just talks
4. **Fine-tuning** = permanently retraining a model for your work
5. **LLMOps** = the practices for running all this in production

---

## Topic 1 — How an AI-powered test tool is put together

An **LLM-powered test infrastructure** is a system with an LLM built into your test process, to help
with automation, reasoning and decision-making.

It's different from a chatbot: a chatbot is built for **conversation**, while this is built to
**support testing** — handling test queries, analysing requirements, generating test cases,
evaluating output.

### The three pieces

**Front end** — the screen you interact with. You type queries and commands here.

**Back end** — the engine room. It handles **authentication, fetching data, preparing the prompt,
and talking to the LLM**.

**The LLM itself** — either a **third-party service accessed through an API**, or a **custom model
you run in-house**.

Plus **external data sources** feeding into it.

### Why it's more than a normal client-server app

The syllabus makes four points here:

1. **The LLM isn't just a server — it's a smart component** that interprets and reasons about your
   testware
2. **Unlike a scripted chatbot**, it generates insights **dynamically from context** — your
   requirements, code, test results
3. **The back end pulls from two kinds of database:**
   - **Relational databases** — for **structured data like test cases**
   - **Vector databases** — for **semantic retrieval using embeddings** (finding things by meaning
     rather than exact words)
4. **The back end cleans up the LLM's raw output** before you see it — **post-processing** it so the
   answer fits your test process

> ⚠️ Point 4 is the one people miss. **The back end is not a passive pipe.** It processes what comes
> out of the model.

**Remember:** relational = structured test data. Vector = meaning-based search.

---

## Topic 2 — RAG: letting the AI look things up

**RAG** stands for **Retrieval-Augmented Generation**. Long name, simple idea:

> **Before the AI answers, it goes and looks up relevant information from your own documents, then
> answers using what it found.**

It's the difference between a closed-book exam and an open-book one. Without RAG, the model can only
use what it learned during training. With RAG, it can consult your actual current requirements.

### How it works — two stages

**Stage A: preparing the library (done in advance)**

1. Your big documents get **chopped into small chunks** — the syllabus says **256–512 tokens** each.
   Two reasons: **focused retrieval**, and **fitting inside the context window**
2. Each chunk gets **cleaned and converted into an embedding** (that list of numbers from Chapter 1)
3. Those embeddings get **stored in a vector database**, ready for fast searching

**Stage B: answering a question (happens live) — two steps**

| Step | What happens |
|---|---|
| **1. Retrieval** | Your question is converted to an embedding, then the system finds the **chunks closest in meaning** — this is **semantic similarity**, not keyword matching |
| **2. Generation** | Those chunks get handed to the LLM, which writes an answer **combining what it already knew with what it just looked up** |

**Retrieval, then Generation. That's the exam answer.** Chunking and embedding happen earlier, in
preparation — not at runtime.

### Why testers care

RAG lets the AI reach **your company's actual data** — databases, documentation, repositories —
**in real time**. So test analysis and test design get based on the **latest specifications and
requirements**, not on whatever the model absorbed during training.

---

## Topic 3 — Agents: AI that does things

An **LLM-powered agent** is an application that handles defined tasks **semi-autonomously or
autonomously**.

### The one difference that matters

> A chatbot **answers**. An agent **acts** — by calling a set of predefined functions called **tools**.

Having tools lets it **interact with and change external systems**. It doesn't just tell you to run
the regression suite; it runs it.

That's the distinction the exam tests. The official glossary says an agent integrates
**LLM reasoning, decision-making and memory, using tools to perform tasks**.

### Two levels of independence

**Autonomous agents** — work **independently with minimal human involvement**, using predefined
rules, reinforcement learning and adaptive feedback loops.

**Semi-autonomous agents** — work with **periodic human oversight** to make sure the output matches
what you wanted.

### Multiple agents working together

A **multi-agent architecture** has several agents, each with a specialised role, **communicating and
coordinating** to solve bigger problems.

That coordination has a name: **orchestration**.

### What they do in testing

They usually appear as **AI assistants built into your testing workflow**. They can take user stories
or requirements and carry them through **test analysis, design, implementation, execution and
reporting** — semi-autonomously.

The syllabus describes this as a shift **from script-based execution to goal-driven, agent-based test
automation**. You tell it the goal; it works out the steps.

### The warning

> Agents have **exactly the same hallucination, reasoning-error and bias problems** as any LLM.

Two ways to manage that:
1. **Automated verification of the agent's results**
2. **Use semi-autonomous agents for critical tasks** — keep a human in the loop

> ⚠️ Likely question: *which agent type for a critical test task?* → **semi-autonomous**.

---

## Topic 4 — Fine-tuning: retraining a model for your work

**Fine-tuning** means taking a pre-trained model and **training it further on your own targeted
dataset**, so it learns your domain.

Technically: **supervised learning on labelled examples that updates the model's weights.**

The "updates the weights" bit is what separates it from RAG.

### What it's good for

- Giving a general model **specialist reasoning** for your domain
- Teaching it **vocabulary specific to your field**

**Testing example from the syllabus:** train a model on **your organisation's own user stories and
the test cases written from them**. Now it generates test cases **in your house format, using your
terminology**.

### The small-model advantage

You can fine-tune an **SLM** (small language model) too. They're **less resource-hungry**, and a
fine-tuned SLM can hit **high performance on a specific task without the computing overhead of a
large model**.

So small + specialised can beat big + general for a narrow job.

### Four problems with fine-tuning

| Problem | What it means |
|---|---|
| **Bias or inaccuracy** | Fixed by using **high-quality, task-specific training data** |
| **Overfitting** | The model gets **too specialised to its training data** and **performs badly on anything new** |
| **Opacity** | You **can't see how it reaches its decisions**, which **makes debugging and validation hard** |
| **Computational cost** | Fine-tuning a large model takes **significant computing resources** |

### RAG vs fine-tuning — the comparison the exam loves

| | **RAG** | **Fine-tuning** |
|---|---|---|
| **Does it change the model?** | **No** | **Yes — updates the weights** |
| **How it gets knowledge** | **Looks it up when asked** | **Learned it during training** |
| **Best for** | **Information that changes** — current specs, requirements, test data | **Your house style, vocabulary, specialist reasoning** |
| **How current is it?** | **Live** | **Frozen at training time** |

Simple version: **RAG gives it a library card. Fine-tuning sends it to school.**

---

## Topic 5 — LLMOps: running this stuff properly

**LLMOps** = **Large Language Model Operations**. It's the **practices, tools and processes for
developing, deploying and maintaining LLMs in production**.

Think DevOps, but for language models.

### Three ways an organisation can adopt GenAI

| Approach | Main things to think about | The distinctive bit |
|---|---|---|
| **1. Use an AI chatbot** | **Privacy, security, cost** | Either a **cloud LLM-as-a-Service**, or **run open-source models in-house for more control**. Either way you must **rigorously assess the vendor's assurances or your own capability** |
| **2. Use a test tool with GenAI built in** | Same, **plus** the **tool vendor's security and performance guarantees** | These **complement your existing process**, so you need a **cost-benefit analysis and risk assessment** |
| **3. Build your own** | **Full control** of privacy and security | Requires planning for **computing resources, data storage and staff training**, **structured validation processes**, and **real expertise** to build it |

### The point the exam will test

> These approaches are **not mutually exclusive**. An organisation might **use a chatbot for some
> tasks while building custom tools for others** — **at the same time**.

And you can layer **RAG and fine-tuning** on top of any of them.

⚠️ Any option saying you must pick one approach is **wrong**.

---

## Traps to watch for

1. **Agent vs chatbot: the agent acts, using tools.** That's the entire distinction.
2. **Critical tasks → semi-autonomous agents** (human oversight).
3. **Agents don't fix Chapter 3's problems** — they inherit all of them.
4. **RAG doesn't change the model. Fine-tuning does.**
5. **RAG at runtime = Retrieval then Generation.** Chunks are **256–512 tokens**.
6. **Vector DB = meaning-based search. Relational DB = structured test data.**
7. **The back end post-processes the output** before you see it.
8. **Overfitting = too specialised to training data, fails on new data.**
9. **Opacity = can't see how it decides, so debugging is hard.**
10. **The three LLMOps approaches can be combined.**
11. **A fine-tuned SLM can outperform a large model** on a specific task, more cheaply.

---

## Quick self-check

1. Name the three architectural pieces.
2. What two database types does the back end use, and what for?
3. What does the back end do to the raw output?
4. What are RAG's two runtime steps?
5. What chunk size, and why chunk at all?
6. What single ability separates an agent from a chatbot?
7. What is orchestration?
8. Which agent type for critical tasks, and why?
9. What does fine-tuning actually change?
10. Name the four fine-tuning problems.
11. What is overfitting? What is opacity?
12. Name the three LLMOps approaches.
13. Must you pick just one?

<details><summary>Answers</summary>

1. **Front end, back end, and the LLM** (plus external data sources).
2. **Relational** for **structured test data like test cases**; **vector** for **semantic retrieval
   using embeddings**.
3. **Post-processes it**, so responses fit the test conditions of the test process.
4. **1. Retrieval** (finding chunks by semantic similarity); **2. Generation** (the LLM combines them
   with what it knows).
5. **256–512 tokens**, for **focused retrieval** and to **fit the context window**.
6. It can **act by invoking predefined functions called tools**, letting it interact with external
   systems.
7. **Several specialised agents communicating and coordinating** in a multi-agent architecture.
8. **Semi-autonomous** — it has **periodic human oversight**.
9. **The model's weights**, through supervised learning on labelled examples.
10. **Bias/inaccuracy**, **overfitting**, **opacity**, **computational cost**.
11. **Overfitting** — too specialised to the training data, so it does badly on new data.
    **Opacity** — you can't see how it makes decisions, which complicates debugging and validation.
12. **(1)** An AI chatbot; **(2)** a test tool with GenAI built in; **(3)** building your own.
13. **No** — they're **not mutually exclusive** and can run at the same time.
</details>

---

# Practice questions — Chapter 4

*Ten questions. The real exam asks **5** from this chapter — one per learning objective,
all worth 1 point, all understanding level. No recall, no scenarios.*

**1.** Which component of an LLM-powered test infrastructure handles authentication, data retrieval
and prompt preparation?
- a) The front end
- b) The back end
- c) The LLM
- d) The vector database

**2.** Why does the syllabus say this architecture goes beyond a traditional client-server model?
- a) Because it uses HTTPS rather than HTTP
- b) Because the LLM is a smart processing component that interprets and reasons based on testware
- c) Because the front end is written as a single-page application
- d) Because it requires an on-premises deployment

**3.** In RAG preprocessing, why are documents split into chunks of roughly 256–512 tokens?
- a) To reduce the cost of the vector database licence
- b) To ensure focused retrieval and compatibility with the model's context window
- c) Because embeddings cannot exceed 512 dimensions
- d) To prevent hallucinations entirely

**4.** How does a RAG system select which stored chunks to use?
- a) By exact keyword match against the prompt
- b) By semantic similarity between the embeddings of the prompt and those of the chunks
- c) By the most recently added chunks
- d) By the chunk with the highest token count

**5.** What primarily separates fine-tuning from RAG?
- a) Fine-tuning updates the model's weights; RAG does not
- b) RAG requires labelled training data; fine-tuning does not
- c) Fine-tuning works only with small language models
- d) RAG can only be used with multimodal models

**6.** An agent operating with periodic human oversight to ensure output meets user-defined goals is:
- a) Autonomous
- b) Semi-autonomous
- c) A rule-based chatbot
- d) A vision-language model

**7.** What is the recommended approach for using LLM-powered agents on critical test tasks?
- a) Use fully autonomous agents to remove human error
- b) Use semi-autonomous agents, and implement automated verification of results
- c) Avoid agents and use a foundation LLM directly
- d) Raise the temperature to encourage more thorough answers

**8.** A model performs excellently on its fine-tuning dataset but poorly on new, unseen test cases.
This is:
- a) Opacity
- b) Overfitting
- c) Data poisoning
- d) Non-determinism

**9.** Which fine-tuning challenge makes debugging and validation harder?
- a) Overfitting
- b) Opacity — lack of transparency in how the model produces its outputs
- c) Computational cost
- d) Biased training data

**10.** An organisation uses a commercial AI chatbot for exploratory work while also building its own
GenAI test tool for regression analysis. This is:
- a) Not permitted — one LLMOps approach must be selected
- b) Acceptable — the three approaches are not mutually exclusive and may run simultaneously
- c) Only possible if both use the same underlying model
- d) Only possible after fine-tuning the commercial model

<details><summary>Answers and explanations</summary>

| Q | Ans | Why |
|---|---|---|
| 1 | **b** | The back end processes user input and manages authentication, data retrieval, prompt preparation and interaction with the LLM. |
| 2 | **b** | The syllabus gives four reasons; this is the first. The others: dynamic generation from context rather than scripted responses, multiple integrated data sources, and post-processing of the LLM's raw output. |
| 3 | **b** | Both reasons matter — focused retrieval **and** compatibility with the context window. |
| 4 | **b** | Retrieval is based on semantic similarity between embeddings, not keyword matching. |
| 5 | **a** | Fine-tuning is supervised learning on labelled examples that updates LLM weights. RAG retrieves external data at runtime and leaves the model unchanged. |
| 6 | **b** | Semi-autonomous agents perform tasks with periodic human oversight. |
| 7 | **b** | The syllabus names both mitigations: automated verification procedures for agent results, and semi-autonomous agents for critical tasks. |
| 8 | **b** | Overfitting — the model becomes too specialized to the training data, harming performance on new, unseen data. |
| 9 | **b** | Opacity is defined as lack of transparency in how an LLM makes decisions or produces outputs, which complicates debugging and validation. |
| 10 | **b** | The approaches are not mutually exclusive and may be implemented simultaneously depending on the test activities involved. |

</details>
