# Optimizing Bank Marketing Decisions Using Contextual Bandits

## Project Overview
This project frames a real-world bank marketing problem as a **contextual bandit** task, a practical form of reinforcement learning commonly used in business decision-making systems such as marketing optimization, recommendation, and online experimentation.

Instead of focusing on pure outcome prediction, the goal of this project is to **optimize marketing actions under uncertainty**, balancing exploration and exploitation to maximize customer conversion rates over time.

---

## Business Problem
Banks frequently run marketing campaigns to promote financial products (e.g., term deposits). For each customer, the bank must decide **whether and how to contact them**, without knowing in advance which strategy will be most effective.

This project addresses the following question:

> *How can a bank dynamically choose marketing strategies for different customers in order to maximize long-term conversion rates while minimizing ineffective outreach?*

---

## Reinforcement Learning Formulation
The problem is modeled as a **contextual bandit**, where each decision is independent but informed by customer context.

- **Context (State):** Customer demographic and behavioral features (e.g., age, job, balance, past campaign outcomes)
- **Actions:** Abstract marketing strategies (e.g., no contact, standard offer, promotional offer)
- **Reward:** Binary conversion outcome (1 if the customer accepts the offer, 0 otherwise)

This formulation captures a realistic decision-making setting commonly found in marketing and product optimization systems.

---

## Methods
The project implements and compares multiple decision policies:

- Random policy (baseline)
- Greedy policy
- Contextual bandit with exploration strategies (e.g., Thompson Sampling)

All policies are evaluated using **offline replay simulation** to estimate cumulative rewards and conversion uplift.

---

## Dataset
This project uses the **Bank Marketing Dataset**, originally from the UCI Machine Learning Repository and widely available on Kaggle.

- **Source:** Kaggle – Bank Marketing Campaign Dataset  
- **Description:** Historical records of direct marketing campaigns, including customer attributes and campaign outcomes  
- **Target Variable:** Customer subscription to a term deposit (yes / no)

The dataset is reinterpreted from a supervised learning setting into a sequential decision-making framework.

---

## Project Summary

This project explores the use of **offline reinforcement learning**, formulated as a **contextual bandit problem**, to support marketing contact decisions using historical bank campaign data.

We frame the problem as a decision-making task: given a customer’s context, the system chooses a contact intensity level and observes a binary conversion outcome. We evaluate three types of policies under a conservative **replay-based offline evaluation framework**:
- Random policy
- Greedy heuristic policy
- Offline Thompson Sampling (batch formulation)

While greedy and learning-based policies demonstrate improved decision quality over random selection when evaluated on matched historical actions, overall performance gains remain limited. This result highlights a key challenge of offline reinforcement learning in real-world business data: **historical selection bias**. Because past actions were not assigned randomly, different actions correspond to systematically different customer populations, making it difficult to isolate true action effects from historical data alone.

Rather than optimizing for marginal performance gains, this project emphasizes **decision framing, evaluation rigor, and methodological honesty**. The findings illustrate when offline RL is appropriate, where its limitations lie, and why additional mechanisms—such as online experimentation, randomized exploration, or causal modeling—are often required for reliable decision optimization.

Overall, the project demonstrates a realistic and production-aware approach to applying reinforcement learning concepts in a fully offline business setting.
 accuracy

---

## Future Work

This project highlights both the potential and limitations of offline reinforcement learning under real-world data constraints. Several extensions could meaningfully improve decision optimization beyond the fully offline setting explored here:

- **Online Experimentation**  
  Deploying randomized exploration or A/B testing would enable direct observation of counterfactual outcomes and substantially reduce historical selection bias, allowing reinforcement learning methods to realize their full potential.

- **Causal and Uplift Modeling**  
  Incorporating causal inference techniques, such as uplift modeling or treatment effect estimation, could better isolate the impact of different contact strategies using historical data.

- **Simulation-Based Evaluation**  
  Building a domain-informed simulator would allow controlled experimentation and iterative policy learning without risking real-world business impact.

- **Richer Reward Design**  
  Extending the reward function to include contact costs, customer lifetime value, or delayed outcomes could provide a more realistic objective for decision optimization.

These directions emphasize that effective reinforcement learning systems require alignment between modeling techniques, data generation processes, and evaluation frameworks.

