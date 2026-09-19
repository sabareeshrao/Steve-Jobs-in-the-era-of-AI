# Batch 0004 - Dataset vs Algorithm vs Architecture vs Model vs AI Product

> Type: Core  
> Track: 01 - AI Landscape & First Principles  
> Status: COMPLETE  
> Depends on: Batches 0001-0003  
> Core Progress After Completion: 4 / 3,600  

## Objective

Separate the major layers of an AI system so the learner no longer treats every AI-related component as "the AI."

By the end of this batch, the learner should understand:

- Dataset vs model.
- Algorithm vs trained model.
- Architecture vs parameters.
- Trained model vs inference infrastructure.
- Model vs AI system.
- AI system vs AI product.

## Why This Batch Exists

Batches 0001-0003 introduced data, training, models, parameters, and different learning paradigms.

A terminology gap remained. Without clarifying these layers, later topics such as neural networks, LLMs, Transformers, inference engines, and AI products could become confusing.

The core mental model is:

```text
DATA
  ↓
TRAINING METHOD
  ↓
MODEL ARCHITECTURE
  ↓
TRAINING PROCESS
  ↓
TRAINED MODEL
  ↓
INFERENCE SYSTEM
  ↓
AI PRODUCT
```

---

<!-- BATCH 0004 | MINI TASK 01 -->
## Mini Task 01 - Dataset Is Not the Model

A dataset is a collection of information used for training or evaluation.

Example:

```text
dataset/
├── cat_001.jpg
├── cat_002.jpg
├── dog_001.jpg
├── dog_002.jpg
└── ...
```

Mental model:

```text
Textbook != Student
Dataset  != Model
```

### Task

Classify each:

A. 5 million labeled photographs  
B. Numerical values learned after training  
C. A collection of customer transactions  
D. A trained fraud detector

### Answer

```text
A -> DATASET
B -> MODEL PARAMETERS / PART OF TRAINED MODEL
C -> DATASET
D -> TRAINED MODEL
```

---

<!-- BATCH 0004 | MINI TASK 02 -->
## Mini Task 02 - Algorithm Is Not the Trained Model

An algorithm is a procedure or method for performing a computation.

In machine learning, a simplified training procedure can look like:

```text
Take data
Make prediction
Measure error
Adjust model
Repeat
```

The procedure is not the same thing as the trained model.

```text
TRAINING ALGORITHM
        +
       DATA
        ↓
     TRAINING
        ↓
 TRAINED MODEL
```

### Analogy

```text
Recipe         -> algorithm
Ingredients    -> data
Cooking        -> training
Finished cake  -> trained model
```

### Task

Which statement is more correct?

A. The training algorithm and trained model are exactly the same thing.  
B. An algorithm describes a procedure, while a trained model contains learned parameter values produced through training.

### Answer

**B**

---

<!-- BATCH 0004 | MINI TASK 03 -->
## Mini Task 03 - What Is a Model Architecture?

Architecture describes the structural design of a model.

Later examples include:

- Linear model.
- Decision tree.
- Neural network.
- CNN.
- RNN.
- Transformer.
- Mixture of Experts.

Mental model:

```text
Model design
    ↓
Architecture

Architecture + learned parameters
    ↓
Trained Model
```

### Task

Two models both use a similar Transformer architecture. One is trained mainly on English text. Another is trained mainly on computer code.

Can they have the same general architecture?

### Answer

**YES**

They can share a similar architecture while having different:

- Training data.
- Parameter values.
- Training objectives.
- Capabilities.
- Behavior.

Architecture does not uniquely determine the final trained model.

---

<!-- BATCH 0004 | MINI TASK 04 -->
## Mini Task 04 - Architecture vs Parameters

Very simplified:

```text
Architecture
    =
Where computation happens
and how components connect

Parameters
    =
Numbers learned inside that structure
```

Example parameters:

```text
weight_1 = 0.82
weight_2 = -0.41
bias_1   = 1.17
```

### Task and Answers

| Statement | Category |
|---|---|
| "This model has 12 layers." | Architecture |
| weight_54321 = 0.027 | Parameter |
| "This model uses Transformer blocks." | Architecture |
| bias_82 = -0.19 | Parameter |

---

<!-- BATCH 0004 | MINI TASK 05 -->
## Mini Task 05 - Model vs Inference Engine

A trained model may be stored on disk, but users still need software and infrastructure to run it.

```text
USER INPUT
    ↓
APPLICATION
    ↓
INFERENCE ENGINE
    ↓
TRAINED MODEL
    ↓
OUTPUT
```

An inference system may handle:

- Loading the model.
- Receiving requests.
- Running computation.
- Managing memory.
- Producing outputs.
- GPU usage.
- Scaling and reliability.

### Task

A company has a trained language model stored on disk.

Does that automatically mean millions of users can chat with it simultaneously?

### Answer

**NO**

The trained model is only one component. Production use also requires model-serving software, compute resources, request handling, networking, memory management, scaling, and reliability.

---

<!-- BATCH 0004 | MINI TASK 06 -->
## Mini Task 06 - Model vs AI System vs AI Product

A model is not necessarily the whole product.

A simplified AI product may contain:

```text
                 AI PRODUCT
                     |
     +---------------+---------------+
     |               |               |
     v               v               v
   User UI        Backend          Safety
                     |
                     v
                 AI SYSTEM
                     |
       +-------------+-------------+
       |             |             |
       v             v             v
     Model         Tools         Retrieval
       |             |             |
       +-------------+-------------+
                     |
                     v
                   Output
```

A product may also include:

- Authentication.
- Billing.
- File handling.
- Search.
- Databases.
- Memory.
- Voice.
- Image processing.
- Moderation.
- Caching.
- Monitoring.
- APIs.

### Task

An AI travel assistant contains:

- Language model.
- Maps connection.
- Flight search API.
- User account system.
- Payment system.
- Conversation memory.
- Mobile app.

Which one is the entire product?

### Answer

All of those components together can form the product.

The language model may be a central intelligence component, but it is not necessarily the entire product.

---

<!-- BATCH 0004 | MINI TASK 07 -->
## Mini Task 07 - Build the Full AI Stack

Suppose Steve wants to build an AI Plant Disease Assistant.

Available pieces:

- 100,000 leaf photographs.
- Disease labels.
- Training procedure.
- Neural-network design.
- Learned parameter values.
- GPU server.
- Mobile app.

### Answer

#### Dataset

```text
100,000 leaf photographs
Disease labels
```

#### Training Method

```text
Procedure used to:
predict
measure loss
adjust parameters
repeat
```

#### Model Architecture

```text
Chosen neural-network structure
```

#### Trained Model

```text
Architecture
+
learned parameter values
```

#### Inference Infrastructure

```text
GPU server
model-serving software
request handling
```

#### Product

```text
Mobile application
+
backend
+
model
+
inference system
+
user experience
```

---

## Full Mental Model

```text
               RAW DATA
                  ↓
               DATASET
                  ↓
        TRAINING ALGORITHM
                  ↓
        MODEL ARCHITECTURE
                  ↓
               TRAINING
                  ↓
       LEARNED PARAMETERS
                  ↓
          TRAINED MODEL
                  ↓
         INFERENCE ENGINE
                  ↓
             AI SYSTEM
                  ↓
             AI PRODUCT
                  ↓
                USER
```

## Important Nuance

Real systems are not always perfectly linear.

For example:

- Data collection can continue after launch.
- User feedback can create new training data.
- One product may call multiple models.
- One model may serve many products.
- One product may route between different models.

AI development can become a cycle:

```text
PRODUCT
   ↓
USER FEEDBACK
   ↓
NEW DATA
   ↓
TRAINING
   ↓
NEW MODEL
   ↓
PRODUCT
```

---

## Steve Jobs Product Test 4

When a founder says "We built an AI," ask:

```text
What exactly did you build?

Did you create the dataset?

Did you design the architecture?

Did you train your own model?

Did you fine-tune someone else's model?

Are you calling another company's model API?

What inference infrastructure do you own?

What parts are ordinary software?

What parts actually contain learned behavior?

What part creates the user experience?
```

### Worked Example - AI Coding Assistant

A coding assistant might contain:

```text
Developer
   ↓
IDE Extension
   ↓
Backend
   ↓
Language Model
   ↓
Generated Code
```

But the complete product may also contain:

- Repository indexing.
- Search.
- Context selection.
- Security rules.
- Tool execution.
- Model routing.
- Logging.
- Caching.
- Evaluation.

Therefore:

```text
MODEL != ENTIRE CODING ASSISTANT
```

---

## Batch 0004 Vocabulary

| Term | Beginner Meaning |
|---|---|
| Dataset | Collection of data used for training/evaluation |
| Algorithm | Procedure for performing a computation or learning process |
| Architecture | Structural design of a model |
| Parameter | Adjustable numerical value learned during training |
| Trained Model | Architecture plus learned parameter state |
| Training | Process used to learn parameter values |
| Inference | Using the trained model |
| Inference Engine | Software/system that executes the model efficiently |
| AI System | Model plus surrounding technical components |
| AI Product | Complete user-facing experience built around one or more AI systems |

## Quick Classification Test

### Question 1

```text
50 TB of text
```

**Answer:** DATASET / DATA

### Question 2

```text
Transformer
```

**Answer:** MODEL ARCHITECTURE FAMILY

### Question 3

```text
Billions of learned numerical values
```

**Answer:** PARAMETERS

### Question 4

```text
A trained checkpoint containing learned parameters
```

**Answer:** TRAINED MODEL

### Question 5

```text
Servers that load the model and answer requests
```

**Answer:** INFERENCE INFRASTRUCTURE

### Question 6

```text
Mobile app + backend + model + search + account + memory
```

**Answer:** AI PRODUCT / SYSTEM, depending on the boundary being discussed.

---

## Connection Across All Four Batches

```text
Batch 0001
What is AI?
      ↓
Batch 0002
How can a model learn?
      ↓
Batch 0003
What kinds of learning signals exist?
      ↓
Batch 0004
What are the pieces that make up
training, a model, a system, and a product?
```

## Learning-Order Review

Potential next concepts included:

- AI history.
- Neural networks.
- Deep learning.
- Generative AI.
- Foundation models.
- LLMs.

The repository showed that the learner already understood training, parameters, and learning signals, but had not clearly separated dataset, algorithm, architecture, trained model, inference system, and product.

Teaching LLMs or Transformers before this distinction would risk terminology confusion.

Therefore Batch 0004 is a justified core-order refinement.

### Dynamic Prerequisite Decision

```text
DYN-0001 required?
NO
```

Reason:

There is no failed concept or missing prerequisite requiring remediation. The needed clarification fits naturally inside Core Batch 0004.

## What Is Intentionally Not Covered Yet

- Weights in detail.
- Biases.
- Neurons.
- Activation functions.
- Layers.
- Neural networks.
- Gradient descent.
- Backpropagation.
- Vectors.
- Matrices.
- Tensors.
- Tokenization.
- Embeddings.
- Attention.
- Transformers.

## Validation

- [x] Understands dataset vs model.
- [x] Understands algorithm vs trained model.
- [x] Understands model architecture conceptually.
- [x] Understands architecture vs parameters.
- [x] Understands trained model vs inference infrastructure.
- [x] Understands model vs AI system.
- [x] Understands AI system vs user-facing AI product.
- [x] Can decompose a simple AI product into its layers.
- [x] Understands that one product can use multiple models.
- [x] Understands that one model can power multiple products.
- [x] All mini-tasks contain worked answers.

## Discoveries

No dynamic prerequisite is currently justified.

Before Batch 0005, inspect repository state and learner maturity again. Batch 0005 should be selected only after another learning-order review.

## Completion Checklist

- [x] All mini-tasks completed with answers.
- [x] Evidence recorded.
- [x] Batch 0004 marked complete.
- [x] STATUS.md scheduled for update.
- [x] Next core batch identified as 0005, subject to learning-order review.
