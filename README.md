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

## Key Takeaways
- Demonstrates how traditional supervised datasets can be reframed as reinforcement learning problems
- Highlights the practical value of contextual bandits in business decision optimization
- Emphasizes decision quality and long-term reward over one-shot prediction accuracy

---

## Future Work
- Incorporate contact cost and customer lifetime value into the reward function
- Extend to off-policy evaluation methods (e.g., IPS, doubly robust estimators)
- Simulate delayed rewards and multi-step customer interactions
