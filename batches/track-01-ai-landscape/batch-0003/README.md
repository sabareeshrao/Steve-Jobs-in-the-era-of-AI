# Batch 0003 - Not Every AI Model Learns the Same Way

> Type: Core  
> Track: 01 - AI Landscape & First Principles  
> Status: COMPLETE  
> Depends on: Batches 0001-0002  
> Core Progress After Completion: 3 / 3,600  

## Objective

Expand the learner's mental model beyond labeled examples by introducing the major ways models can receive learning signals.

By the end of this batch, the learner should understand at a beginner level:

- Supervised learning.
- Classification vs regression.
- Unsupervised learning.
- Self-supervised learning.
- Reinforcement learning.
- Why modern AI systems often use multiple training stages.

## Why This Batch Exists

Batch 0002 intentionally used labeled examples to explain the basic training loop:

```text
INPUT + LABEL
     ↓
   MODEL
     ↓
 PREDICTION
     ↓
   LOSS
     ↓
ADJUST PARAMETERS
```

That mental model is useful but incomplete. If left uncorrected, it can create the false idea that every AI system requires humans to label every training example.

Before moving deeper into AI history, neural networks, or model architectures, the learner should understand that models can learn from different kinds of signals.

---

<!-- BATCH 0003 | MINI TASK 01 -->
## Mini Task 01 - Supervised Learning

Supervised learning uses examples where the desired target is known.

Examples:

```text
Image -> CAT / DOG
Transaction -> FRAUD / NOT FRAUD
House information -> PRICE
Customer review -> POSITIVE / NEGATIVE
```

### Task

Classify each:

A. Photos already labeled CAT or DOG  
B. One million unlabeled customer records grouped automatically  
C. Historical houses with their actual selling prices  
D. Emails already labeled SPAM or NOT SPAM

### Answer

```text
A -> Supervised
B -> Not supervised in this example
C -> Supervised
D -> Supervised
```

Why?

A, C, and D contain known targets.

---

<!-- BATCH 0003 | MINI TASK 02 -->
## Mini Task 02 - Classification vs Regression

Two common supervised-learning problem types are classification and regression.

### Classification

Predict a category.

Examples:

```text
SPAM / NOT SPAM
FRAUD / NOT FRAUD
CAT / DOG
DISEASE A / DISEASE B / HEALTHY
```

### Regression

Predict a numerical quantity.

Examples:

```text
House price -> $425,000
Delivery duration -> 37 minutes
Electricity demand -> 4,820 MW
Temperature -> 81.2
```

### Task and Answers

| Problem | Type |
|---|---|
| Predict whether a transaction is fraud | Classification |
| Predict apartment rent | Regression |
| Predict whether an image contains a pedestrian | Classification |
| Predict tomorrow's temperature | Regression |
| Predict which species of flower appears in a photo | Classification |

Mental model:

```text
CATEGORY -> Classification
NUMBER   -> Regression
```

---

<!-- BATCH 0003 | MINI TASK 03 -->
## Mini Task 03 - Unsupervised Learning

Suppose we have customer data but no labels such as:

```text
Premium customer
Budget customer
Occasional customer
```

A system may try to discover useful structure on its own.

```text
RAW CUSTOMER DATA
        ↓
     ALGORITHM
        ↓
Possible Groups
```

This connects to unsupervised learning.

Common goals include:

- Finding groups.
- Finding structure.
- Finding unusual examples.
- Learning useful representations.

### Task

One million songs have no genre labels. A system examines song features and discovers groups of similar music.

Supervised or unsupervised?

### Answer

**Unsupervised learning**

Why?

The system was not given explicit targets such as:

```text
song001 -> ROCK
song002 -> JAZZ
song003 -> POP
```

It attempted to discover structure from the data itself.

---

<!-- BATCH 0003 | MINI TASK 04 -->
## Mini Task 04 - Self-Supervised Learning

Self-supervised learning creates a learning target from the raw data itself.

Example:

Original text:

```text
Steve built a new computer.
```

Create a learning example:

```text
Input:
Steve built a new

Target:
computer
```

No human had to manually label every sentence. The data already contained the target.

Very simplified:

```text
RAW DATA
   ↓
Automatically create learning task
   ↓
INPUT -> TARGET
   ↓
Train model
```

### Task

Original sentence:

```text
The satellite captured an image of Earth.
```

Create one next-word-style self-supervised example.

### Answer

One possible answer:

```text
Input:
The satellite captured an image of

Target:
Earth
```

The important discovery:

```text
Raw data supplied its own target.
```

---

<!-- BATCH 0003 | MINI TASK 05 -->
## Mini Task 05 - Why Self-Supervision Changed AI

Manually labeling enormous collections of books, web pages, code, articles, and documents is expensive.

Self-supervised learning allows raw data to generate vast numbers of training examples automatically.

```text
HUGE RAW DATASET
       ↓
SELF-SUPERVISED OBJECTIVE
       ↓
TRAIN LARGE MODEL
```

For a decoder-style language model, an oversimplified objective is:

```text
Given previous text
        ↓
Predict next token
```

Example:

```text
Input:
"The capital of France is"

Target:
"Paris"
```

### Task

Why is self-supervised learning useful at enormous scale?

A. Humans must manually label every word.  
B. Raw data itself can provide training targets at enormous scale.  
C. Models no longer need data.  
D. Training no longer requires computation.

### Answer

**B**

The raw data can generate vast numbers of training examples automatically.

---

<!-- BATCH 0003 | MINI TASK 06 -->
## Mini Task 06 - Reinforcement Learning

Reinforcement learning introduces agents, actions, environments, and rewards.

Very simplified:

```text
AGENT
  ↓
ACTION
  ↓
ENVIRONMENT
  ↓
REWARD / FEEDBACK
  ↓
AGENT LEARNS
```

Examples include:

- Game-playing agents.
- Robotics.
- Control systems.
- Some forms of post-training for modern AI systems.

### Task

Which scenario most resembles reinforcement learning?

A. 50,000 images already labeled CAT or DOG  
B. Customer records automatically grouped into clusters  
C. Game agent tries actions and receives rewards depending on performance  
D. House records contain house price labels

### Answer

**C**

Learning is guided by outcomes or rewards from actions.

---

<!-- BATCH 0003 | MINI TASK 07 -->
## Mini Task 07 - One Modern AI System Can Use Multiple Learning Stages

Do not assume:

```text
One model = one learning method forever
```

A simplified language-model journey might include:

```text
STAGE 1
Large raw text/code dataset
       ↓
Self-supervised pretraining
       ↓
Base language model


STAGE 2
Instruction examples
       ↓
Supervised fine-tuning
       ↓
More useful assistant behavior


STAGE 3
Preference / reward-related training
       ↓
Further post-training
       ↓
Improved behavior
```

### Task

Match each stage.

A. Model predicts missing/next information using enormous raw text datasets.  
B. Model is shown examples of user instructions and good assistant responses.  
C. Different responses receive preference or reward-related signals.

### Answer

```text
A -> Self-supervised learning
B -> Supervised learning
C -> Preference / reinforcement-related learning
```

This is the first rough picture of why building a modern AI assistant involves more than simply "training one neural network."

---

## Steve Jobs Product Test 3

Steve now asks:

```text
HOW did the system receive its learning signal?

Were humans labeling examples?

Was structure discovered automatically?

Was behavior learned from user actions?

Were rewards or preferences involved?

Was there more than one training stage?
```

### Worked Example - AI Chess System

Potential learning sources may include:

```text
Historical games
       +
Board positions
       +
Self-play
       +
Game outcomes
```

Possible signals include:

```text
Moves made by strong players
Win / loss
Self-generated experience
```

A sophisticated system can combine multiple techniques rather than fitting neatly into one beginner category.

---

## Batch 0003 Comparison Table

| Learning Style | What Provides the Learning Signal? | Simple Example |
|---|---|---|
| Supervised | Known targets/labels | CAT vs DOG |
| Unsupervised | Structure in unlabeled data | Customer clustering |
| Self-supervised | Targets generated from the data itself | Predict next token |
| Reinforcement learning | Rewards/outcomes from actions | Game-playing agent |

## Critical Correction to Batch 0002

Batch 0002 used:

```text
INPUT + LABEL
```

That was intentionally simplified.

Training does not always require a human-created label.

A broader mental model is:

```text
                TRAINING SIGNAL
                       |
       +---------------+---------------+
       |               |               |
     LABEL         RAW DATA          REWARD
       |               |               |
       v               v               v
 Supervised      Self-supervised   Reinforcement
```

Unsupervised learning introduces another important idea:

```text
UNLABELED DATA
      ↓
DISCOVER STRUCTURE
```

## What Is Intentionally Not Covered Yet

- Weights.
- Biases.
- Neurons.
- Layers.
- Neural networks.
- Gradient descent.
- Backpropagation.
- Vectors.
- Matrices.
- Tensors.
- Tokens.
- Embeddings.
- Attention.
- Transformers.

These are not required yet to understand the AI landscape.

## Learning-Order Review

Repository inspection showed:

```text
Batch 0001
What AI/model/training/inference mean
        ↓
Batch 0002
How a basic labeled training loop works
        ↓
Batch 0003
Different sources of learning signals
```

This is a stronger sequence than jumping directly into AI history, neural networks, ChatGPT architecture, or Transformers.

### Dynamic Prerequisite Decision

```text
DYN-0001 required?
NO
```

Reason:

Batches 0001 and 0002 provide enough prerequisite knowledge for Batch 0003. No demonstrated gap requires remediation.

## Batch 0003 Mental Model

```text
                     DATA / EXPERIENCE
                            |
          +-----------------+----------------+
          |                 |                |
       LABELS          DATA ITSELF        REWARDS
          |                 |                |
          v                 v                v
     SUPERVISED      SELF-SUPERVISED   REINFORCEMENT
          \                 |                /
           \                |               /
            +---------------+--------------+
                            |
                            v
                     LEARNED MODEL
```

And:

```text
UNLABELED DATA
      ↓
DISCOVER STRUCTURE
```

## Validation

- [x] Understands supervised learning at beginner level.
- [x] Understands classification vs regression.
- [x] Understands unsupervised learning at beginner level.
- [x] Understands self-supervised learning conceptually.
- [x] Understands why self-supervision matters for large language models.
- [x] Understands reinforcement learning conceptually.
- [x] Understands that one modern model can use multiple training stages.
- [x] No longer assumes all AI requires human-created labels.
- [x] All seven mini-tasks include worked answers.

## Discoveries

No dynamic prerequisite is currently justified.

Before Batch 0004, inspect repository state and learner maturity again. Batch 0004 should be generated only after another learning-order review.

## Completion Checklist

- [x] All mini-tasks completed with answers.
- [x] Evidence recorded.
- [x] Batch 0003 marked complete.
- [x] STATUS.md scheduled for update.
- [x] Next core batch identified as 0004, subject to learning-order review.
