# Batch 0001 - What Exactly Is Artificial Intelligence?

> Type: Core  
> Track: 01 - AI Landscape & First Principles  
> Status: COMPLETE  
> Depends on: None  
> Core Progress After Completion: 1 / 3,600  

## Objective

Build the first mental model of artificial intelligence without requiring programming, mathematics, neural networks, or Transformer knowledge.

By the end of this batch, the learner should understand:

```text
DATA -> TRAINING -> MODEL
                    |
NEW INPUT -> INFERENCE -> OUTPUT
```

## Why This Batch Exists

Before learning machine learning algorithms or building models, the learner must distinguish AI systems from ordinary rule-based software and understand the words input, model, output, training, and inference.

---

<!-- BATCH 0001 | MINI TASK 01 -->
## Mini Task 01 - Separate Normal Software From AI

### Task

Classify the following systems as ordinary rule-based software or AI/ML systems.

| System | Normal Software / AI | Why? |
|---|---|---|
| Calculator | Normal Software | Arithmetic operations follow explicitly programmed mathematical rules. |
| Alarm clock | Normal Software | A basic alarm follows a fixed rule such as triggering at a configured time. |
| Spam email detector | AI / ML | A modern spam detector can learn patterns from examples of spam and legitimate email. |
| Face recognition system | AI / ML | It learns visual representations and patterns that help associate faces with identities. |
| ChatGPT | AI | It uses a trained language model to generate responses from input prompts. |
| Basic tax calculator | Normal Software | A basic tax calculator applies explicitly defined tax rules and formulas. |

### Answer

The important distinction is not that ordinary software has no data or that AI has no programmed code. Both contain software.

The beginner-level distinction is:

```text
Traditional rule-based software:
Rules written by programmers + Input -> Output

Machine-learning system:
Training data + Learning process -> Model
Model + New input -> Output
```

### Check

**Why is a calculator normally not called AI while a spam classifier can be?**

A calculator applies predefined arithmetic rules. A machine-learning spam classifier can learn patterns from labeled email examples and then apply those learned patterns to new messages.

---

<!-- BATCH 0001 | MINI TASK 02 -->
## Mini Task 02 - Identify Input, Model, and Output

### Example 1: Spam Detection

```text
Input:
"This email says I won $5,000,000."

Model:
Spam detection model

Output:
SPAM
```

### Example 2: Face Recognition

```text
Input:
A face photograph

Model:
Face recognition model

Output:
Predicted identity
```

### Example 3: AI Assistant

```text
Input:
A user's question

Model:
Language model used by the assistant

Output:
Generated response
```

### Answer

```text
Input  = information supplied to the system
Model  = the learned computational system that processes the input
Output = the result produced by the system
```

### Original Example

```text
Input:
A photograph of a road

Model:
Traffic-sign recognition model

Output:
"STOP SIGN"
```

---

<!-- BATCH 0001 | MINI TASK 03 -->
## Mini Task 03 - Meet the Word Model

For this batch, use the following beginner mental model:

```text
Input -> MODEL -> Output
```

A model is a learned computational system that transforms input into a useful output.

### Task Answers

#### Handwritten Digit

```text
Photo of handwritten number
        |
        v
      Model
        |
        v
Predicted digit, for example "7"
```

#### Audio

```text
Audio recording
      |
      v
Speech recognition model
      |
      v
Transcribed text
```

#### Language Model

```text
"What is gravity?"
        |
        v
 Language Model
        |
        v
Generated explanation of gravity
```

### One-Sentence Answer

**What is an AI model?**

An AI model is a learned computer system that takes information in, applies patterns learned during training, and produces a useful result.

---

<!-- BATCH 0001 | MINI TASK 04 -->
## Mini Task 04 - Training vs Inference

### Mental Model

```text
TRAINING

Training Data
     |
     v
Learning Process
     |
     v
Trained Model
```

```text
INFERENCE

New Input
    |
    v
Trained Model
    |
    v
Prediction / Generated Output
```

### Classification Answers

| Scenario | Answer | Reason |
|---|---|---|
| A company feeds millions of text documents into a model-building process. | TRAINING | The model is being created or improved from data. |
| You type "Explain Java" into ChatGPT. | INFERENCE | An already-trained model processes a new prompt and produces a response. |
| A vision model processes a new road image and identifies a pedestrian. | INFERENCE | The trained vision model is being used on new input. |
| A model's parameters are repeatedly adjusted while learning from examples. | TRAINING | Parameter updates are part of the learning process. |

### Core Rule

```text
Training creates or improves the model.
Inference uses the trained model.
```

---

<!-- BATCH 0001 | MINI TASK 05 -->
## Mini Task 05 - Build the First AI Family Map

### Beginner-Level Map

```text
Artificial Intelligence
|
+-- Rule/search/reasoning approaches
|
+-- Machine Learning
    |
    +-- Deep Learning
        |
        +-- Modern Generative AI
```

### Required Hierarchy Answer

```text
AI
└── Machine Learning
    └── Deep Learning
        └── Generative AI
```

This is a useful beginner hierarchy, but the real AI field contains overlapping techniques and categories that later batches will refine.

### Generative AI Can Produce

- Text
- Images
- Audio
- Video
- Code

### Foundation Models

A foundation model is broadly trained so that it can support or be adapted to many downstream tasks rather than being created for only one narrow task.

### Why These Statements Are Wrong

**"AI = ChatGPT"**

Wrong because AI is a broad field. ChatGPT is one AI product built using AI models and supporting systems.

**"Machine Learning = ChatGPT"**

Wrong because machine learning contains many approaches and applications beyond conversational language models.

**"All AI = Generative AI"**

Wrong because AI also includes non-generative systems such as classification, search, planning, recommendation, detection, optimization, and control systems.

---

<!-- BATCH 0001 | MINI TASK 06 -->
## Mini Task 06 - Steve Jobs Product Test

### Selected AI System

**ChatGPT**

### Answer

**Input:**  
A user's prompt, which may include text and, depending on the product capabilities, other supported input types.

**Model's job:**  
Process the supplied context and produce an appropriate continuation or response based on patterns learned during training and later model improvements.

**Output:**  
A generated response such as an explanation, answer, draft, code sample, analysis, or structured result.

**What probably required training:**  
Large amounts of data, computational resources, optimization, model architecture, and later stages of post-training that shape useful assistant behavior.

**What happens during inference:**  
The trained model receives the user's current input and generates output without repeating the original full pretraining process.

**Why this is useful:**  
A single conversational interface can help users work with information, language, coding, reasoning tasks, and many other workflows without requiring a separate manually programmed rule for every possible request.

### Product Questions Steve Should Ask

```text
What goes in?
What comes out?
What did the system have to learn?
Where did that learning come from?
What can this product do that ordinary software cannot do easily?
Where does it fail?
Why would a human actually want this?
```

---

## Batch 0001 Mental Model

```text
                ARTIFICIAL INTELLIGENCE
                         |
                         v
                MACHINE LEARNING
                         |
                         v
                  DEEP LEARNING
                         |
                         v
                GENERATIVE AI
```

And:

```text
DATA
 |
 v
TRAINING
 |
 v
MODEL
 |
 +----------------+
 |                |
New Input         |
 |                |
 v                |
INFERENCE         |
 |                |
 v                |
OUTPUT            |
```

## What Is Intentionally Not Covered Yet

- How neural networks learn
- Python
- Linear algebra
- Calculus
- Gradient descent
- Tokens
- Embeddings
- Attention
- Transformers
- LLM architecture
- GPU training

These belong to later batches.

## Validation

- [x] Can distinguish basic rule-based software from machine-learning systems.
- [x] Understands Input -> Model -> Output.
- [x] Can explain "model" at beginner level.
- [x] Understands training vs inference.
- [x] Can distinguish AI, ML, deep learning, and generative AI at a high level.
- [x] Analyzed one modern AI product using the Steve Jobs product test.
- [x] Worked answers are recorded in the repository.

## Discoveries

No prerequisite gap was discovered before Batch 0001. No dynamic ⭐ batch is required before continuing.

Batch 0002 should continue Track 01 from this mental model and must not unnecessarily reteach the same definitions.

## Completion Checklist

- [x] All mini-tasks completed with worked answers.
- [x] Evidence recorded in this batch file.
- [x] Batch 0001 marked complete.
- [x] STATUS.md scheduled for update.
- [x] Next core batch identified as 0002.
