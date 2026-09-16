# Chapter 1 — Getting Started with Generative AI

**Worth 7 points out of 46. Seven questions, none of them hard "apply" questions.**

---

## What this chapter is really about

Before you can learn how to *use* AI for testing, you need to know what AI actually is and how it
works. That is all this chapter does. There is no scenario-solving here — just understanding.

Think of it as the vocabulary lesson before the conversation.

---

## Part 1 — There are four kinds of AI, and GenAI is only one

People say "AI" as if it is one thing. It is not. The syllabus wants you to tell four types apart.

### 1. Symbolic AI — the rule follower

Someone sits down and writes rules by hand:

> IF the customer is over 60 AND the order is over ₹5000, THEN apply a discount.

The computer just follows them. It never learns anything. It only knows what a human typed in.

**Remember it as:** rules and logic, written by people.

### 2. Classical machine learning — learns, but you point at what matters

Here the computer learns from data instead of rules. But **a human has to decide which pieces of
information are worth looking at.** Those pieces are called **features**.

Say you want to predict which bug reports are critical. A human decides: "look at the module name,
the customer type, and how many users reported it." The machine then learns patterns from those
three things.

Picking those three things is called **feature selection**, and a human does it.

**Remember it as:** the machine learns, but *you* choose what it looks at.

### 3. Deep learning — figures out what matters by itself

Same idea, but now the computer uses **neural networks** with many layers, and it **works out the
important features on its own**. Nobody tells it to look at module name or customer type — it finds
useful patterns itself.

This is what makes it good at messy things like images, audio and video, where a human could never
list all the features.

> ⚠️ Small but examinable detail: humans are still involved — labelling data, tuning the model,
> checking results. So an answer saying "no human involvement at all" is wrong.

**Remember it as:** the machine figures out what to look at.

### 4. Generative AI — creates something new

Deep learning that doesn't just classify or predict, but **makes new content**: text, images, code.
It learned patterns from huge amounts of training data, and now it produces new material that
follows those patterns.

**Remember it as:** it creates things.

### How they fit together

```
AI
 ├── Symbolic AI          (rules — off on its own branch)
 └── Machine Learning
      └── Deep Learning
           └── Generative AI
```

Generative AI is a *type of* deep learning, which is a *type of* machine learning. Symbolic AI
sits outside all of that, because it does not learn from data at all.

### Why testers like GenAI

Here is the sentence the exam cares about:

> GenAI uses **pre-trained models you can use straight away, with no extra training phase**.

With classical ML you would have to gather data and train a model before you got any value. With
GenAI you just open it and start asking. That is the big advantage.

But — and the syllabus says this immediately after — **this comes with risks**. Chapter 3 is
entirely about those risks. If an exam option makes GenAI sound risk-free, it is wrong.

---

## Part 2 — How a large language model actually works

A **large language model (LLM)** is a program trained on an enormous amount of text — books,
articles, websites — until it got very good at producing human-like writing.

There is also a **small language model (SLM)**: same idea, just a smaller model with **fewer
parameters**. Lighter, cheaper, more focused.

Four ideas make an LLM work. Take them one at a time.

### Idea 1: Tokenization — chopping text into pieces

The model cannot read a sentence the way you do. First it chops the text into small pieces called
**tokens**.

A token might be a whole word, part of a word, or even a single character:

```
"unbelievable"   →   "un"  +  "believ"  +  "able"
```

**So a token is not the same as a word.** That trips people up in the exam.

### Idea 2: Embeddings — turning pieces into numbers

Computers only do maths, not meaning. So each token gets turned into a long list of numbers called
an **embedding**.

Picture a gigantic map. Every token is a dot on it. Tokens that mean similar things end up **close
together** — "cat" sits near "kitten", far from "invoice".

That closeness is how the model senses that two words are related.

> **Put tokenization and embeddings together and you get the point:** they convert language into
> numbers the model can work with.

### Idea 3: The transformer — guessing the next piece, over and over

The **transformer** is the design of the neural network underneath. Its job is simple to describe:

**Look at everything so far, then guess the next token. Then do it again. And again.**

It is predictive text on your phone, except vastly better at it.

Now here is the single most important sentence in the whole syllabus:

> ### It produces text that is **statistically plausible**. Plausible is not the same as correct.

The model writes what *sounds* right based on patterns it has seen. It has no idea whether what it
just wrote is true. It is like a very confident colleague who never admits they don't know
something — fluent, convincing, and sometimes completely wrong.

Everything in Chapter 3 grows out of this one fact.

### Idea 4: Non-determinism — the same question, different answers

Ask an LLM the same thing twice and you can get two different answers.

Why? Because when it picks the next token, it **picks probabilistically** rather than always taking
the single most likely one. There is deliberate randomness in there, controlled by settings called
**hyperparameters**.

**Exam answer:** non-determinism comes from *the probabilistic nature of inference, plus
hyperparameter settings*. Not from bugs. Not from bad prompts.

### And one more: the context window

The **context window** is how much text the model can hold in mind at once, **measured in tokens**.

Think of it as the size of its desk. A bigger desk means it can keep a longer document in view and
stay coherent — handy when you feed it a huge test log.

**But bigger is not free.** More tokens means more computing and more processing time.

> ⚠️ Common trap: "a bigger context window is always better." No. There is a cost. Nothing in this
> syllabus is free.

---

## Part 3 — Three types of LLM, in the order they are built

These are built one on top of the next. The order matters.

### 1. Foundation LLM — the raw graduate

Trained on a huge, broad pile of data. Knows a bit about everything. Very capable, but not shaped
for any particular job — the syllabus says it **typically requires further adaptation**.

*Also called a **Base LLM**. Learn that synonym.*

### 2. Instruction-tuned LLM — the trained employee

Take a foundation model and train it further on **examples of prompts paired with good responses**.
Now it actually follows instructions instead of rambling.

The syllabus says it is optimised for **task adherence, instruction following, and response
coherence**.

*Confusingly, these are also called **"non-reasoning"** models. Know that too.*

### 3. Reasoning LLM — the senior analyst who shows their working

Take an instruction-tuned model and train it further on problems that need **step-by-step thinking**
— logical inference, multi-step problems, **chain-of-thought**.

Best for **high-cognitive-load tasks**.

**The order: Foundation → Instruction-tuned → Reasoning.**

### Which ones do testers actually use?

**Instruction-tuned and reasoning models.** Not raw foundation models.

And which of the two? The syllabus says it **depends on how complex the task is and how much
reasoning it needs**. Simple, repetitive job → instruction-tuned. Hard multi-step problem →
reasoning model.

---

## Part 4 — Models that can see, not just read

A **multimodal LLM** handles more than text. It can take in **text, images, sound and video**.

How? Each type of data gets converted into embeddings in its own way. For images, that conversion is
done by a **vision-language model** before the transformer sees it.

A **vision-language model** is a *subset* of multimodal models that specifically combines pictures
and words. It can caption an image, answer questions about an image, or check whether a picture
matches a description.

### Why this matters for a tester

You can hand the model **a screenshot and the user story at the same time** and ask what doesn't
match.

The syllabus gives two benefits:

1. **Spot differences between what was expected and what the screenshot actually shows.**
2. **Write richer test cases** that use both the words and the visuals, which **increases coverage**.

---

## Part 5 — What an LLM can do across the test process

The syllabus lists **seven** things. Expect a question like "which of these is *not* a key LLM
capability?"

| # | What it does | In practice |
|---|---|---|
| 1 | **Analyse and improve requirements** | Finds **ambiguities, inconsistencies, missing information**, and writes questions to ask stakeholders |
| 2 | **Help create test cases** | Drafts test cases and suggests test objectives from requirements or user stories |
| 3 | **Generate test oracles** | Works out the **expected results** |
| 4 | **Generate test data** | Builds datasets, **sets boundary values**, makes combinations |
| 5 | **Support test automation** | Writes scripts from test case descriptions, improves existing ones, suggests test techniques |
| 6 | **Analyse test results** | Summarises them, **sorts anomalies by severity and priority** |
| 7 | **Create testware** | Test plans, test reports, defect reports — and **keeps them updated as the project changes** |

A phrase worth remembering: the LLM can read **requirements, specifications, screenshots, code, test
cases and defect reports** — so it helps across the **whole** test process, not just one part.

---

## Part 6 — Two ways you will actually use it

There are two ways GenAI shows up in a tester's working life.

### The chatbot

You type, it replies. Like messaging a knowledgeable colleague.

- Good for **quick answers**, **exploratory testing**, and **helping new testers get up to speed**
- Anyone can use it, including **non-technical stakeholders** — no coding needed
- You refine answers by going back and forth (that's **prompt chaining**, coming in Chapter 2)

### The LLM built into a tool

Here the AI is wired **into your test tools through APIs**. You don't chat with it; it works in the
background.

- Offers **customisation and scalability**
- Good for **automating repetitive or complex work** — generating test cases, analysing defects,
  creating test data
- The advanced version of this is **AI agents** (Chapter 4)

### The link to Chapter 2

Whichever one you use, the syllabus says the same thing:

> Success depends on **strong prompt engineering** — clear, specific, well-built prompts.

Which is exactly what Chapter 2 teaches, and Chapter 2 is worth more than double this chapter.

---

## Traps to watch for

1. **Plausible is not correct.** Any option that treats LLM output as trustworthy by default is wrong.
2. **A bigger context window costs more** computing and time.
3. **Classical ML: humans pick the features. Deep learning: the model finds them.**
4. **Foundation → Instruction-tuned → Reasoning**, in that order.
5. **A token is not a word.** It can be a character, part of a word, or a word.
6. **Similar meanings sit close together** in embedding space.
7. **An SLM is smaller, not automatically worse** — Chapter 4 shows small models can beat big ones
   on specific jobs.
8. **Non-determinism comes from probabilistic inference and hyperparameters**, not from mistakes.

---

## Quick self-check

1. Which type of AI needs a human to choose the features?
2. What does the model predict each step?
3. Why do you get different answers to the same question?
4. What is the downside of a bigger context window?
5. Name the three LLM types in build order.
6. What else is a foundation LLM called?
7. Which LLM types do testers actually use, and what decides which?
8. Name four of the seven LLM capabilities for testing.
9. Give two testing benefits of a model that can see images.
10. Which is better for onboarding a new tester — chatbot or built-in tool? Why?

<details><summary>Answers</summary>

1. **Classical machine learning** — it needs data preparation, feature selection, and training.
2. **The next token**, producing text that is statistically plausible but not necessarily correct.
3. **Probabilistic inference plus hyperparameter settings** — there is deliberate randomness.
4. It **costs more computing power and processing time**.
5. **Foundation → Instruction-tuned → Reasoning.**
6. A **Base LLM**.
7. **Instruction-tuned and reasoning LLMs**, chosen by **how complex the task is and how much
   reasoning it demands**.
8. Any four of: analyse/improve requirements, help create test cases, generate test oracles,
   generate test data, support automation, analyse results, create testware.
9. **(a)** Spot differences between expected results and what a screenshot actually shows.
   **(b)** Write richer test cases using text and visuals together, increasing coverage.
10. **The chatbot** — it gives quick, conversational access to testing knowledge and is easy enough
    for anyone to use.
</details>

---

# Practice questions — Chapter 1

*Twelve multiple-choice questions in exam style. The real exam asks **7** from this chapter,
all worth 1 point each.*

**1.** Which type of AI represents knowledge using symbols and logical rules?
- a) Classical machine learning
- b) Symbolic AI
- c) Deep learning
- d) Generative AI

**2.** What is the main advantage of GenAI for software testing?
- a) It produces output that never needs checking
- b) It uses pre-trained models that can be applied directly, with no additional training phase
- c) It removes the need for test techniques
- d) It guarantees complete requirements coverage

**3.** Which statement about tokens is correct?
- a) One token always equals one word
- b) A token can be a character, a sub-word or a word
- c) Tokens are only used for image data
- d) Tokens are the numerical vectors the model processes

**4.** What do embeddings capture?
- a) The file size of the input document
- b) The semantic, syntactic and contextual relationships of tokens
- c) The number of tokens in the context window
- d) The temperature setting used at inference

**5.** Two tokens with similar meanings will have embeddings that are:
- a) Identical
- b) Positioned close together in a high-dimensional space
- c) Stored in the same relational database row
- d) Assigned the same token ID

**6.** Which statement best reflects how the transformer generates text?
- a) It retrieves the closest matching answer from a stored knowledge base
- b) It predicts the next token, producing text that is statistically plausible but not necessarily correct
- c) It applies logical rules to derive a provably correct answer
- d) It searches the internet and summarises the results

**7.** An SLM differs from an LLM primarily because it:
- a) Cannot process natural language
- b) Has fewer parameters and is designed to be lightweight and focused
- c) Is always more accurate than an LLM
- d) Does not use the transformer architecture

**8.** Which LLM type is described as emphasising chain-of-thought and multi-step problem solving?
- a) Foundation LLM
- b) Instruction-tuned LLM
- c) Reasoning LLM
- d) Base LLM

**9.** An instruction-tuned LLM is created by:
- a) Training a foundation model further on datasets pairing prompts with expected responses
- b) Reducing the parameter count of a reasoning model
- c) Training from scratch on instruction data only
- d) Applying retrieval-augmented generation to a base model

**10.** Which is a correct application of a multimodal LLM in software testing?
- a) Reducing the energy consumption of test execution
- b) Identifying discrepancies between expected results and the actual visual elements on a screenshot
- c) Guaranteeing that generated test scripts compile
- d) Eliminating the need for a test oracle

**11.** Which of these is one of the seven key LLM capabilities for test tasks?
- a) Automatically signing off the test completion report
- b) Test data generation, including setting boundary values
- c) Replacing the risk analysis performed by the test manager
- d) Certifying compliance with the EU AI Act

**12.** A non-technical business analyst wants to explore possible test scenarios for a new feature
by asking questions in plain language. Which is most appropriate?
- a) An LLM-powered testing application integrated via API
- b) An AI chatbot
- c) A fine-tuned small language model
- d) A multi-agent orchestration framework

<details><summary>Answers and explanations</summary>

| Q | Ans | Why |
|---|---|---|
| 1 | **b** | Symbolic AI is the rule-based approach that represents knowledge using symbols and logical rules. |
| 2 | **b** | The syllabus names this as the key advantage — pre-trained models usable directly without an additional training phase. It adds immediately that this comes with risks, so (a) and (d) are wrong. |
| 3 | **b** | A token can be as small as a character or as large as a sub-word or word. Option (d) describes embeddings, not tokens. |
| 4 | **b** | Embeddings encode semantic, syntactic and contextual relationships in numerical form. |
| 5 | **b** | Tokens with similar meanings or contextual roles sit close together in the high-dimensional space. Close, not identical. |
| 6 | **b** | It predicts the next token. "Plausible is not necessarily correct" is the defining caution of the whole syllabus. |
| 7 | **b** | An SLM is a compact model with fewer parameters, designed for lightweight and focused solutions. It is not automatically less accurate — Chapter 4 shows fine-tuned SLMs performing strongly. |
| 8 | **c** | Reasoning LLMs emphasise logical inference, multi-step problem-solving and chain-of-thought. |
| 9 | **a** | Instruction-tuned models are derived from foundation models and fine-tuned on prompt/expected-response pairs. |
| 10 | **b** | This is one of the two benefits the syllabus names, along with generating richer test cases from text plus visual cues. |
| 11 | **b** | Test data generation — datasets, boundary values, combinations — is one of the seven. The others all breach the human-responsibility principle. |
| 12 | **b** | Chatbots have an intuitive conversational interface accessible even to non-technical stakeholders, and suit dynamic exploration of requirements and potential test cases. |

</details>
