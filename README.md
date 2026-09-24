# Loop Engineering for Agentic AI — Databricks Wanderbricks Lab

This lab demonstrates how to build a simple **loop-engineered Agentic AI workflow** on **Databricks Free Edition** using the built-in `samples.wanderbricks` dataset.

The objective is to show that a reliable agent is more than a single LLM call. The system repeatedly **plans, acts, observes, evaluates, and decides whether to continue**, while maintaining state and enforcing explicit stop conditions.

---

## Lab Scenario

The notebook implements a **Travel Support Investigation Agent**.

A customer has a booking where the **booking status and payment status require investigation**. The agent gathers evidence from multiple Wanderbricks tables, evaluates whether enough evidence has been collected, generates an answer, and then checks the quality of that answer.

The agent can:

- Inspect the booking
- Inspect the related payment
- Inspect booking-update history
- Inspect customer-support messages
- Maintain state across iterations
- Decide whether more evidence is required
- Retry an answer when quality is insufficient
- Stop when quality is acceptable
- Escalate to human review when the loop reaches its limits

---

## What Is Loop Engineering?

**Loop Engineering** is the practice of designing AI systems that operate in controlled cycles rather than relying on a single model response.

A typical loop is:

```text
Goal
  ↓
Plan
  ↓
Act
  ↓
Observe
  ↓
Evaluate
  ↓
Replan / Retry
  ↓
Repeat or Stop