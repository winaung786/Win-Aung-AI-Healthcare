# 🤖 Assignment 9: Reinforcement Learning — Automated Insulin Dosing

## 📋 Overview

In this assignment, I designed a **Reinforcement Learning (RL) scenario** for automated insulin dosing in Type 1 diabetic patients. RL is a branch of machine learning where an agent learns optimal actions through trial and error, receiving rewards for good outcomes and penalties for bad ones.

---

## 🧪 Methods

I defined the RL framework by specifying the three core components:

1. **State**: What the agent observes about the patient's current condition.
2. **Action**: What the agent can do (adjust the insulin dose).
3. **Reward**: The feedback signal based on whether blood glucose stayed in the target range.

---

## 📊 Results

### RL Framework Definition

| Component | Definition | Details |
|-----------|-----------|----------|
| **State (S)** | Patient's current physiological status | Blood glucose level (mg/dL), time since last meal, carbohydrate intake, physical activity level, insulin on board (IOB), time of day |
| **Action (A)** | Insulin dose adjustment | Increase, decrease, or maintain current dose; 0.5-unit increments (range: 0–15 units) |
| **Reward (R)** | Feedback based on resulting blood glucose | Positive reward for target range; escalating penalties for hypo/hyperglycemia |

### Reward Structure

| Blood Glucose Level | Classification | Reward Signal |
|-------------------|----------------|---------------|
| < 54 mg/dL | Severe Hypoglycemia | **-100** (critical penalty) |
| 54–69 mg/dL | Hypoglycemia | **-50** (strong penalty) |
| **70–180 mg/dL** | **Target Range** | **+10** (positive reward) |
| 181–250 mg/dL | Hyperglycemia | **-20** (moderate penalty) |
| > 250 mg/dL | Severe Hyperglycemia | **-60** (strong penalty) |

### Episode Structure

| Element | Description |
|---------|-------------|
| **Episode Length** | 24 hours (one full day cycle) |
| **Time Steps** | Every 5 minutes (288 steps per episode) |
| **Terminal Condition** | Episode ends if blood glucose drops below 40 mg/dL |
| **Training Environment** | FDA-approved Type 1 diabetes simulator (UVA/Padova) |

---

## 💬 Discussion

RL for insulin dosing offers several advantages over traditional approaches:

- **Personalization**: The RL agent learns each patient's unique glucose dynamics.
- **Continuous Adaptation**: Unlike fixed dosing regimens, the RL agent adjusts in real time.
- **Asymmetric Risk Handling**: The reward structure heavily penalizes hypoglycemia (acutely dangerous) more than hyperglycemia.

**Safety considerations**: The agent must be trained in simulation before clinical deployment, with a safety override layer and human oversight at all times.

---

## 💡 What I Learned

- **The RL framework (State, Action, Reward)** provides a powerful structure for modeling sequential medical decisions.
- **Reward shaping is critical** — the relative magnitude of rewards and penalties directly determines the agent's behavior.
- **Simulation-first development** is essential for safety.
- **RL's potential extends beyond insulin dosing** to chemotherapy dosing, ventilator management, and sepsis treatment.

---

## 📚 References

1. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
2. Bastani, M. (2021). *Model-free intelligent diabetes management.* Control Engineering Practice, 56, 87–95.
3. Kovatchev, B. P., et al. (2009). *In silico preclinical trials for closed-loop control of type 1 diabetes.* JDST, 3(1), 44–55.
4. Zhu, T., et al. (2020). *Basal glucose control using deep reinforcement learning.* IEEE JBHI, 24(10), 2930–2940.

---

[⬅️ Back to Portfolio](../../README.md)
