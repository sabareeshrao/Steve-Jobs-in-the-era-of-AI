# Operating Rules

## 1. Repository Is the Source of Truth

Never generate a new batch from memory alone. Read the current repository state first.

## 2. Core Numbering

- Core batches are fixed at 0001 through 3600.
- The 60 master tracks each own exactly 60 core numbers.
- A later core batch may be redesigned before it begins if repository evidence shows a better learning or build order.
- Completed core batch numbers are never reused.

## 3. Dynamic ⭐ Batches

Use a dynamic batch only when it solves a real discovered need.

Valid triggers include:

- Missing prerequisite.
- Failed or confusing previous implementation.
- Regression.
- Important concept that must be learned before continuing.
- Research finding that changes the architecture or build order.
- Security, evaluation or data-quality gap.
- New technique that is materially relevant to the end goal.

Dynamic identifiers use DYN-0001, DYN-0002, and so on. They do not consume core batch numbers.

## 4. Before Generating Any Batch

Check, in order:

1. MASTER_ROADMAP.md
2. STATUS.md
3. Recent batch records
4. Relevant code
5. Tests
6. Experiment outputs
7. Known failures
8. Prerequisites
9. Duplicate-topic risk
10. Current build order
11. Learner maturity reached so far
12. Whether the planned sequence should be readjusted

Then decide whether the next item should be the next core batch or a dynamic ⭐ batch.

## 5. Adaptive Learning-Order Rule

The 3,600-batch roadmap defines the long-range destination, not an immutable sequence of future lessons.

Before every batch:

- Re-evaluate the order of learning.
- Preserve already-completed batches.
- Move future concepts earlier or later when dependencies justify it.
- Avoid teaching advanced abstractions before required mental models exist.
- Avoid unnecessary repetition of concepts already demonstrated.
- Prefer build order over textbook chapter order when the project benefits from it.
- Insert a ⭐ dynamic batch when the next core batch would otherwise depend on missing knowledge.
- Record meaningful sequencing decisions inside the batch.

## 6. Answers Are Mandatory

Every future batch must include worked answers for its mini-tasks.

Answers should:

- Show the expected reasoning or result.
- Remain appropriate to the learner's current maturity.
- Not hide required intermediate understanding.
- Clearly distinguish a sample answer from facts when multiple valid answers are possible.
- Grow in technical depth as the journey matures.

## 7. Batch Design

Each batch should normally contain small, executable mini-tasks rather than one large assignment.

A batch should:

- Have a concrete learning/build objective.
- Explain only what is needed to execute the tasks.
- Reuse earlier knowledge.
- Produce observable evidence.
- Include code when the stage requires code.
- Include tests or checks when applicable.
- Include worked answers.
- End with a clear completion checklist.
- Record discoveries that should affect future batches.

## 8. Build-First Principle

Theory must connect to implementation, experiments, debugging, evaluation or product behavior. The journey should progressively build real artifacts rather than become a collection of notes.

## 9. Language Guardrail

All repository content must be written in English.

## 10. Commit Rule

Do not mark a batch complete until its intended repository changes are committed. A completion commit should update STATUS.md and the batch record.

Recommended commit pattern:

- batch 0001: <short objective>
- dyn 0001: <reason>
- docs: <documentation change>
- fix: <correction>

## 11. Evidence Rule

Where applicable, keep evidence such as:

- Source code.
- Tests.
- Training logs.
- Evaluation results.
- Benchmark outputs.
- Experiment configuration.
- Failure analysis.
- Research notes.
- Architecture decisions.

## 12. No Blind Sequence Rule

The roadmap gives direction. Repository evidence and current learner maturity determine the exact next work. Never continue merely because the next number exists.

## 13. End Goal

The journey is designed to move through broad AI mastery and progressively serious systems toward:

1. Independent AI research capability.
2. Foundation-model design and pretraining.
3. Post-training and reasoning systems.
4. Multimodal and agentic capabilities.
5. Evaluation, safety and security.
6. Large-scale inference infrastructure.
7. A production AI assistant product.
8. Continuous Model V2 and later research cycles.
