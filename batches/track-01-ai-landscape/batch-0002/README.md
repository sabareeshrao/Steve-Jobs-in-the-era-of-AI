# Batch 0002 - How Does a Machine Actually Learn From Data?

> Type: Core  
> Track: 01 - AI Landscape & First Principles  
> Status: COMPLETE  
> Depends on: Batch 0001  
> Core Progress After Completion: 2 / 3,600  

## Objective

Open the training black box one level beyond Batch 0001.

By the end of this batch, the learner should understand the conceptual learning loop:

```text
EXAMPLES
   ↓
MODEL MAKES A GUESS
   ↓
COMPARE GUESS WITH DESIRED RESULT
   ↓
MEASURE ERROR
   ↓
ADJUST MODEL
   ↓
TRY AGAIN
```

No equations are required yet.

## Why This Batch Exists

Batch 0001 established:

```text
DATA -> TRAINING -> MODEL
```

But TRAINING was still a black box. Before studying AI history, neural networks, gradients, or model architectures, the learner should understand what "learning from data" means at a beginner level.

---

<!-- BATCH 0002 | MINI TASK 01 -->
## Mini Task 01 - Human Rules vs Learned Patterns

Imagine we want software to detect spam.

### Approach A

A programmer writes:

```text
IF email contains "FREE MONEY"
    mark as SPAM

IF email contains "YOU WON"
    mark as SPAM

IF email contains "CLICK HERE NOW"
    mark as SPAM
```

This is primarily:

```text
PROGRAMMER WRITES RULES
```

### Approach B

We provide thousands of examples:

```text
Email 1 -> SPAM
Email 2 -> NOT SPAM
Email 3 -> SPAM
Email 4 -> NOT SPAM
...
```

A machine-learning process searches for patterns that help predict the correct category.

This is:

```text
DATA
 ↓
LEARNING PROCESS
 ↓
LEARNED MODEL
```

### Task

Classify each:

A. Programmer writes 500 fraud-detection rules manually.  
B. Model studies examples of fraudulent and legitimate transactions.  
C. Developer writes `if age < 18: deny_access()`.  
D. Model studies thousands of X-rays labeled with diagnoses.

### Answer

| Case | Type | Why |
|---|---|---|
| A | Rule-based software | Humans explicitly define the decision rules. |
| B | Machine learning | The system learns predictive patterns from historical examples. |
| C | Rule-based software | The decision logic is directly programmed. |
| D | Machine learning | The model learns useful patterns from labeled medical images. |

### Important

Machine learning does not mean nobody programmed anything.

Engineers still program:

- How data is loaded.
- How the model is built.
- How training runs.
- How errors are measured.
- How parameters are updated.
- How predictions are served.

What changes is that developers do not manually write every final decision rule.

---

<!-- BATCH 0002 | MINI TASK 02 -->
## Mini Task 02 - Understand an Example

Suppose we want a model to predict:

```text
HOUSE SIZE -> HOUSE PRICE
```

Training examples:

```text
1000 sq ft -> $200,000
1500 sq ft -> $300,000
2000 sq ft -> $400,000
2500 sq ft -> $500,000
```

The system sees relationships in the examples.

Eventually it may learn something approximately like:

```text
larger house -> usually higher price
```

Now provide:

```text
1800 sq ft
```

The model might predict:

```text
$360,000
```

It did not necessarily memorize:

```text
1800 sq ft = $360,000
```

because that exact example may never have existed.

Instead, it learned a useful relationship from examples.

### Task

Suppose training data contains:

```text
1 hour study -> score 52
2 hours study -> score 61
3 hours study -> score 69
4 hours study -> score 79
5 hours study -> score 87
```

What might the model predict for 3.5 hours?

### Answer

A reasonable prediction might be approximately:

```text
74
```

The exact answer depends on the model and training process.

The important idea is:

```text
Known examples
      ↓
Learn relationship
      ↓
Estimate unseen example
```

This ability is called **generalization**.

---

<!-- BATCH 0002 | MINI TASK 03 -->
## Mini Task 03 - Meet Training Examples

An AI model cannot learn from the phrase:

> Become intelligent.

It needs information.

Suppose we train a cat-vs-dog classifier.

Training data might look like:

```text
cat001.jpg -> CAT
dog001.jpg -> DOG
cat002.jpg -> CAT
dog002.jpg -> DOG
...
```

Each example contains:

```text
INPUT
+
EXPECTED ANSWER
```

For example:

```text
Input:
cat001.jpg

Expected answer:
CAT
```

The expected answer is often called a **label**.

```text
IMAGE -> INPUT
CAT   -> LABEL
```

### Task and Answers

| Example | Input | Label |
|---|---|---|
| Customer review: "This phone is fantastic." | Review text | POSITIVE |
| Transaction: $8,900 transferred at 3:14 AM from unusual location | Transaction information | FRAUD |
| X-ray image | X-ray image | PNEUMONIA |

Mental model:

```text
INPUT + CORRECT ANSWER
        ↓
 TRAINING EXAMPLE
```

---

<!-- BATCH 0002 | MINI TASK 04 -->
## Mini Task 04 - Prediction -> Error -> Adjustment

Suppose the correct house price is:

```text
$300,000
```

The model initially predicts:

```text
$220,000
```

Clearly:

```text
Prediction != Correct Answer
```

There is an error.

Very roughly:

```text
Correct answer: $300,000
Prediction:     $220,000

Difference:      $80,000
```

Training needs a way to measure how bad the prediction was.

That measurement is connected to **loss**.

For now:

```text
LOSS = a number telling us how wrong the model currently is
```

Very rough conceptual loop:

```text
INPUT
 ↓
MODEL
 ↓
PREDICTION
 ↓
COMPARE WITH CORRECT ANSWER
 ↓
LOSS
 ↓
ADJUST MODEL
```

Then try again.

### Task

A model predicts DOG for an image whose correct answer is CAT.

What should happen during training?

A. Nothing  
B. The training system measures the error and changes the model in a direction intended to improve future predictions.  
C. Delete the picture.  
D. Programmer manually adds an exact image rule.

### Answer

**B**

Conceptually:

```text
Wrong prediction
      ↓
Measure error
      ↓
Adjust model
      ↓
Try to perform better
```

---

<!-- BATCH 0002 | MINI TASK 05 -->
## Mini Task 05 - Meet Parameters

What exactly gets adjusted?

A model can contain many adjustable numerical values called **parameters**.

During training, those values change.

Very simplified:

```text
Before training:

parameter_1 = random-ish value
parameter_2 = random-ish value
parameter_3 = random-ish value
...
```

Training:

```text
Prediction
   ↓
Error
   ↓
Adjust parameters
```

Eventually:

```text
parameter_1 = learned value
parameter_2 = learned value
parameter_3 = learned value
...
```

Those parameters collectively encode useful learned behavior.

Do not think:

```text
parameter = English rule
```

Usually it is not something readable like:

```text
IF sentence contains "lottery"
THEN spam
```

It is numerical information distributed throughout the model.

### Task

Which thing primarily changes during normal model training?

A. Monitor brightness  
B. Model parameters  
C. File extension  
D. User's keyboard

### Answer

**B. Model parameters**

Mental model:

```text
DATA
 ↓
TRAINING
 ↓
PARAMETERS CHANGE
 ↓
MODEL LEARNS USEFUL BEHAVIOR
```

---

<!-- BATCH 0002 | MINI TASK 06 -->
## Mini Task 06 - Memorization vs Learning a Pattern

Imagine training data contains:

```text
2 + 2 = 4
3 + 3 = 6
4 + 4 = 8
5 + 5 = 10
```

Now we ask:

```text
6 + 6 = ?
```

If a system has learned a useful pattern, it might answer:

```text
12
```

even though that exact example was not one of its training examples.

This introduces **generalization**:

> Performing usefully on new examples that were not simply memorized from the training set.

### Task

Two models take an exam.

Model A sees Q1-Q4 during training and is tested on the same Q1-Q4. It gets 100%.

Model B sees Q1-Q4 during training and is tested on different questions Q5-Q8. It gets 92%.

Which result gives stronger evidence of useful generalization?

### Answer

**Model B**

Model A may simply have memorized the exact questions.

Model B successfully handled previously unseen examples.

This distinction later connects to:

- Training set.
- Validation set.
- Test set.
- Overfitting.
- Benchmark contamination.
- LLM evaluation.

---

<!-- BATCH 0002 | MINI TASK 07 -->
## Mini Task 07 - Build the First Complete Learning Loop

Suppose we are building an Apple Fruit Classifier.

Training data:

```text
image_001.jpg -> APPLE
image_002.jpg -> ORANGE
image_003.jpg -> APPLE
image_004.jpg -> BANANA
...
```

### Task

Complete the flow.

```text
Step 1:
__________

Step 2:
Model makes __________

Step 3:
Prediction is compared with __________

Step 4:
Calculate __________

Step 5:
Adjust model __________

Step 6:
Repeat many times

Step 7:
Use trained model on __________ data
```

### Answer

```text
Step 1:
Provide training examples.

Step 2:
Model makes a prediction.

Step 3:
Prediction is compared with the expected answer / label.

Step 4:
Calculate loss.

Step 5:
Adjust model parameters.

Step 6:
Repeat many times.

Step 7:
Use trained model on new/unseen data.
```

Full picture:

```text
              TRAINING DATA
                   ↓
                 MODEL
                   ↓
              PREDICTION
                   ↓
           COMPARE WITH LABEL
                   ↓
                 LOSS
                   ↓
          ADJUST PARAMETERS
                   ↓
             TRY AGAIN
                   ↓
             TRAINED MODEL
                   ↓
              NEW INPUT
                   ↓
               INFERENCE
                   ↓
                OUTPUT
```

---

## Steve Jobs Product Test 2

Steve now sees a photo-classification AI.

Instead of simply saying "AI", he should ask:

```text
What training examples did it see?
What was the input?
What was the desired output?
Where did the labels come from?
What exactly was optimized?
How do we know it learned instead of memorized?
What happens when it sees something completely new?
Where does it fail?
```

### Worked Example - Plant Disease Recognition

**Training data:**  
Leaf photographs plus disease labels.

**Input:**  
Leaf photograph.

**Desired output:**  
Disease category.

**Learning process:**

```text
Model predicts a disease
        ↓
Compare prediction with known label
        ↓
Measure error/loss
        ↓
Adjust parameters
        ↓
Repeat
```

**Inference:**

```text
new_leaf.jpg
      ↓
trained model
      ↓
"Possible Early Blight"
```

**Product questions:**

Does it work on leaves from different cameras, countries, lighting conditions, and plant varieties?

These questions push toward generalization.

---

## Batch 0002 Vocabulary

| Word | Beginner Meaning |
|---|---|
| Data | Information used by or provided to a system |
| Training example | One example used during learning |
| Input | Information given to the model |
| Label | Expected/correct answer attached to certain training examples |
| Prediction | Model's current output |
| Loss | Numerical measure of how wrong the prediction is |
| Parameter | Adjustable numerical value inside the model |
| Training | Process that adjusts model parameters using data |
| Inference | Using a trained model on an input |
| Generalization | Performing well on useful unseen examples |

## What Is Intentionally Not Covered Yet

- How parameters mathematically change.
- Gradients.
- Gradient descent.
- Neurons.
- Neural networks.
- Backpropagation.
- Tensors.
- Embeddings.
- Tokens.
- Attention.
- Transformers.

These black boxes will be opened progressively.

## Connection to Batch 0001

Batch 0001:

```text
DATA
 ↓
TRAINING
 ↓
MODEL
 ↓
INFERENCE
 ↓
OUTPUT
```

Batch 0002 expands TRAINING:

```text
Training Examples
       ↓
     Model
       ↓
   Prediction
       ↓
Compare With Target
       ↓
      Loss
       ↓
Adjust Parameters
       ↓
      Repeat
```

## Learning-Order Review

The repository state was reviewed before generating this batch.

No dynamic ⭐ prerequisite was required.

The sequence was intentionally adjusted to explain "learning from data" before moving into AI history, model families, neural-network internals, or mathematical optimization.

## Validation

- [x] Understands manually written rules vs learned patterns.
- [x] Understands training examples.
- [x] Understands input and label.
- [x] Understands prediction at beginner level.
- [x] Understands loss conceptually.
- [x] Understands that training changes model parameters.
- [x] Understands generalization vs simple memorization.
- [x] Can reconstruct the basic training loop.
- [x] All mini-tasks include worked answers.

## Discoveries

No prerequisite gap currently requires a dynamic ⭐ batch.

Before Batch 0003, the repository and learning order must be reviewed again. Batch 0003 should build on Batches 0001 and 0002 without unnecessarily reteaching them.

## Completion Checklist

- [x] All mini-tasks completed with answers.
- [x] Evidence recorded.
- [x] Batch 0002 marked complete.
- [x] STATUS.md scheduled for update.
- [x] Next core batch identified as 0003, subject to learning-order review.
