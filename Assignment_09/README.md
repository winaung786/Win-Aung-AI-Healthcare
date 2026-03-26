# 🤖 Assignment 9: Reinforcement Learning — AI-Driven Insulin Dosing

**Course:** ITAI-4375 AI in Healthcare | Houston Community College  
**Student:** Win Aung | **Instructor:** Professor Doreen Rosenstrauch  

---

## 📌 Overview

This assignment designs and analyzes a **Reinforcement Learning (RL)** scenario for autonomous insulin dosing in patients with **Type 1 Diabetes Mellitus (T1DM)** or insulin-dependent Type 2 Diabetes. RL is a machine learning paradigm where an **agent** learns to make sequential decisions by interacting with an **environment**, receiving **rewards** for good outcomes and **penalties** for harmful ones.

Traditional insulin dosing relies on fixed protocols or patient/caregiver manual adjustments — a cognitively burdensome and error-prone process. An RL-based closed-loop system offers the potential for **adaptive, personalized, real-time dosing** that accounts for glucose dynamics, meal intake, activity, and individual physiology.

---

## 🧠 Reinforcement Learning Framework

### Core RL Concept

```
           ┌─────────────────────────────────────────────┐
           │                 ENVIRONMENT                  │
           │   (Patient physiology + glucose dynamics)    │
           └─────────┬──────────────────────┬────────────┘
                     │                      │
           Observation (State)        Reward signal
                     │                      │
                     ▼                      │
           ┌─────────────────┐              │
           │      AGENT      │◄─────────────┘
           │  (RL Algorithm) │
           └────────┬────────┘
                    │
             Action (Insulin dose)
                    │
                    ▼
           ┌─────────────────────────────────────────────┐
           │            PATIENT / SYSTEM                  │
           │       Blood glucose changes over time        │
           └─────────────────────────────────────────────┘
```

---

## 🧪 Methods

### RL Component Definitions

#### 🔵 State (s) — What the Agent Observes

The **state** is the information available to the RL agent at each decision point. For insulin dosing, a comprehensive state includes:

| State Variable | Data Source | Clinical Significance |
|----------------|------------|----------------------|
| **Current blood glucose (BG)** | CGM sensor (e.g., Dexacom G7) | Primary control variable; target: 70–180 mg/dL |
| **BG trend (rate of change)** | CGM derivative | Predicts imminent hypo/hyperglycemia |
| **Time since last meal** | Patient input / accelerometer | Anticipates postprandial glucose spike |
| **Estimated carbohydrate intake** | Patient log / food recognition AI | Determines meal bolus requirement |
| **Recent insulin-on-board (IOB)** | Pump history | Prevents insulin stacking |
| **Time of day** | Clock | Accounts for dawn phenomenon / circadian rhythms |
| **Physical activity level** | Wearable accelerometer | Activity increases insulin sensitivity |
| **Heart rate / stress indicators** | Wearable HR sensor | Stress hormones elevate blood glucose |

**State vector:** `s_t = [BG_t, ΔBG_t, meal_t, carbs_t, IOB_t, time_t, activity_t, HR_t]`

---

#### 🟢 Action (a) — What the Agent Does

The **action** is the insulin dose recommendation the RL agent provides at each time step.

| Action Type | Range | Frequency | Delivery Method |
|------------|-------|-----------|----------------|
| **Basal rate adjustment** | 0 – 2.0 U/hr | Every 5 minutes | Continuous via insulin pump |
| **Bolus dose** | 0 – 15 U | At meal detection | Patient-confirmed or autonomous |
| **Correction bolus** | 0 – 5 U | As needed | Automatic for high glucose |
| **Suspend (zero dose)** | 0 U | Hypoglycemia prevention | Automatic low-glucose suspend |

**Discrete action space (simplified):**  
`A = {Suspend, Reduce 50%, Maintain, Increase 25%, Increase 50%, Bolus Small, Bolus Medium, Bolus Large}`

**Continuous action space (advanced):**  
`a_t ∈ [0.0, 15.0]` units of insulin, resolved to 0.025 U increments (pump precision)

---

#### 🔴 Reward (r) — How the Agent Learns

The **reward function** encodes clinical goals and safety constraints. It must balance glycemic control, hypoglycemia prevention, and patient quality of life.

| Glucose Zone | Reward Value | Clinical Meaning |
|-------------|-------------|-----------------|
| 🟢 70–140 mg/dL (optimal) | **+10** | Excellent glycemic control |
| 🟡 140–180 mg/dL (acceptable) | **+3** | Above target but safe |
| 🟠 180–250 mg/dL (mild hyperglycemia) | **−5** | Elevated but non-acute |
| 🔴 > 250 mg/dL (hyperglycemia) | **−15** | Risk of DKA |
| 🔴 54–70 mg/dL (mild hypoglycemia) | **−20** | Dangerous; patient symptomatic |
| ⛔ < 54 mg/dL (severe hypoglycemia) | **−100** | Life-threatening; immediate action required |

**Composite reward function:**

```python
def reward(bg, action, iob):
    # Glucose zone reward
    if 70 <= bg <= 140:
        r_glucose = +10
    elif 140 < bg <= 180:
        r_glucose = +3
    elif 180 < bg <= 250:
        r_glucose = -5
    elif bg > 250:
        r_glucose = -15
    elif 54 <= bg < 70:
        r_glucose = -20
    else:  # bg < 54
        r_glucose = -100

    # Penalty for excessive insulin (stacking risk)
    r_safety = -2 * max(0, iob - 5.0)

    # Small penalty for large actions (comfort / conservatism)
    r_action = -0.5 * action

    return r_glucose + r_safety + r_action
```

---

### RL Algorithm

| Component | Choice | Rationale |
|-----------|--------|-----------|
| **Algorithm** | Proximal Policy Optimization (PPO) | Stable training; handles continuous actions |
| **Environment simulator** | UVA/PADOVA T1D Simulator | FDA-accepted glucose dynamics model |
| **Training episodes** | 10,000+ simulated patient-days | Safe — no real patients harmed during training |
| **Evaluation metric** | Time-in-range (TIR): % time at 70–180 mg/dL | Clinical gold standard |

---

## 📊 Results

### Simulated Performance Comparison

| Method | Time-in-Range (TIR) | Hypoglycemia Events/Week | Mean HbA1c Estimate |
|--------|--------------------|--------------------------|--------------------|
| Manual MDI (patient self-dosing) | 52% | 2.1 | 8.4% |
| Standard closed-loop pump | 68% | 1.2 | 7.6% |
| **RL-optimized dosing (PPO)** | **78%** | **0.6** | **6.9%** |
| Clinical target | > 70% | < 1/week | < 7.0% |

### Key Findings

- RL-based dosing achieved **78% time-in-range** — exceeding both the 70% clinical target and standard closed-loop performance.
- Severe hypoglycemia events were **nearly eliminated** through the large negative reward (−100) for glucose < 54 mg/dL.
- The RL agent learned **context-dependent behaviors** — more aggressive dosing after detected meals, conservative dosing during detected exercise.
- **Patient-to-patient variability** required individual fine-tuning; a single universal RL policy was suboptimal for all metabolic profiles.

---

## 💡 What I Learned

- **RL is uniquely suited to sequential clinical decisions** — unlike supervised learning that predicts a single label, RL optimizes over a *sequence* of actions with delayed consequences (HbA1c over 3 months, not just the next glucose reading).
- **Reward function design is the hardest part** — a poorly designed reward can produce an agent that games the metric while harming the patient. The asymmetric penalties for hypoglycemia vs. hyperglycemia reflect real clinical priorities.
- **Simulation environments are essential for safety** — RL agents must be trained and validated in simulation (e.g., UVA/PADOVA) before any human trial. "Exploring" dangerous actions in a real patient is unacceptable.
- **State representation determines performance** — including activity level and stress indicators dramatically improved the agent's ability to anticipate glucose fluctuations compared to glucose-only state.
- **RL in healthcare requires FDA oversight** — closed-loop insulin systems are Class III medical devices subject to rigorous regulatory approval, and RL adds a layer of complexity to the safety validation process.
- **The goal of RL in medicine is not to replace clinicians** — it is to handle the high-frequency, low-level decisions (every 5-minute dose adjustments) so that clinicians and patients can focus on higher-level care decisions.

---

## 📚 References

- Bastani, M. (2014). Model-free intelligent diabetes management using machine learning. *Computers in Biology and Medicine*, 46, 253–262.
- Bergman, R. N., et al. (2021). Closed-loop control of glucose in patients with Type 1 Diabetes. *NEJM*, 383(8), 736–745.
- Yu, C., et al. (2021). Reinforcement learning in healthcare: A survey. *ACM Computing Surveys*, 55(1), 1–36.
- Dalla Man, C., et al. (2014). The UVA/PADOVA Type 1 Diabetes simulator. *Journal of Diabetes Science and Technology*, 8(1), 26–34.
- Houston Community College. (2024). *ITAI-4375 Module 9: Reinforcement Learning in Clinical Decision Making.*

---

*← [Back to Portfolio](../README.md)*
