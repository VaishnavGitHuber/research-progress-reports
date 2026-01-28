# Text-to-SQL Research Repository

This repository contains all the files and resources required for conducting research on **Text-to-SQL** generation.

---

## Stage 1: Experiments on the BIRD California_School Database using GPT-5-Mini

### Results

| Strategy | Accuracy |
|--------|----------|
| No Chain-of-Thought (NoCoT) | **54%** |
| Chain-of-Thought (CoT) | 52% |
| Divide & Conquer | 52% |

### Observations

- The results are **highly correlated with the original paper**.
- **NoCoT outperforms more advanced reasoning strategies** such as CoT and Divide & Conquer.
- A possible explanation is that modern Large Language Models (LLMs), such as ChatGPT, have **strong internal reasoning capabilities**, making explicit reasoning prompts less effective.
- The **Divide & Conquer strategy** performs better for certain queries where both NoCoT and CoT fail, indicating its usefulness in specific scenarios.

---

## Stage 2: Selecting Correct-Answer Queries Using ChatGPT-5

This stage is motivated by the assumption that **small-scale models** may not consistently perform well across all queries. Therefore, selecting queries that the **base model can answer correctly** may lead to more reliable experimental analysis.

### Query Selection Strategy

- Queries for which **GPT produced correct answers using the NoCoT approach** were selected.
- Total selected queries: **27**

### Accuracy on Selected Queries

| Strategy | Accuracy |
|--------|----------|
| NoCoT | **100% (27/27)** |
| CoT | 92.59% (25/27) |
| Divide & Conquer | 77.78% (21/27) |

---

### Key Insights

- **NoCoT achieves perfect accuracy** on the selected subset of queries.
- Advanced reasoning strategies may introduce **unnecessary complexity**, sometimes degrading performance.
- These findings suggest that **explicit reasoning prompts are not always optimal**, especially when the base model already performs strong implicit reasoning.

---
