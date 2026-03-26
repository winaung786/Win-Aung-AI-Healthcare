# 🔬 Assignment 4: Diagnostic Test Evaluation — DermaSensor

**Course:** ITAI-4375 AI in Healthcare | Houston Community College  
**Student:** Win Aung | **Instructor:** Professor Doreen Rosenstrauch  

---

## 📌 Overview

This assignment evaluates the **DermaSensor** device, an AI-powered handheld tool designed to assist clinicians in the early detection of skin cancer—particularly melanoma. The analysis focuses on interpreting key diagnostic performance metrics: **sensitivity** and **specificity**, and what those numbers mean for real-world clinical use.

DermaSensor uses a spectroscopic sensor combined with a machine-learning algorithm to analyze skin lesions non-invasively. After scanning a lesion, the device outputs a risk classification that prompts the clinician toward referral or reassurance.

---

## 🧪 Methods

### Diagnostic Test Design
The study compared DermaSensor output against histopathology results (the "gold standard") across a cohort of patients presenting with suspicious skin lesions.

| Metric | Definition |
|--------|-----------|
| **Sensitivity** | Proportion of actual cancer cases correctly identified (True Positive Rate) |
| **Specificity** | Proportion of non-cancer cases correctly identified (True Negative Rate) |
| **PPV** | Probability that a positive result truly indicates cancer |
| **NPV** | Probability that a negative result truly rules out cancer |

### Confusion Matrix Framework

|  | Predicted Positive | Predicted Negative |
|--|-------------------|--------------------|
| **Actual Positive** | True Positive (TP) | False Negative (FN) |
| **Actual Negative** | False Positive (FP) | True Negative (TN) |

$$\text{Sensitivity} = \frac{TP}{TP + FN} \quad \text{Specificity} = \frac{TN}{TN + FP}$$

---

## 📊 Results

| Performance Metric | DermaSensor Value | Clinical Benchmark |
|-------------------|------------------|--------------------|
| **Sensitivity** | **96%** | ≥ 90% (high priority) |
| **Specificity** | **40%** | ≥ 70% (desired) |
| Study Population | 1,000+ lesions | Mixed skin types |
| Comparator | Dermatologist unaided | Clinical standard |

### Interpretation

- **96% Sensitivity** means DermaSensor correctly flags 96 out of every 100 true skin cancer cases — an excellent safety net for a life-threatening disease.
- **40% Specificity** means 60 out of every 100 benign lesions are flagged as suspicious — a high false-positive rate that leads to unnecessary referrals and patient anxiety.

### Trade-off Analysis

```
High Sensitivity (96%) → Catches almost all cancers → Minimizes missed diagnoses (FN ↓)
Low Specificity (40%)  → Many false alarms         → Increases unnecessary biopsies (FP ↑)
```

This trade-off is acceptable for a **screening tool** where missing a cancer is far more costly than an unnecessary referral. However, the low specificity means DermaSensor should complement — not replace — dermatologist evaluation.

---

## 💡 What I Learned

- **Sensitivity vs. Specificity is a clinical trade-off**, not a technical flaw. For cancer screening, erring toward high sensitivity is deliberate and appropriate.
- A device can have outstanding sensitivity but poor specificity and still be **clinically valuable** as a first-line triage tool.
- The **clinical context determines acceptable thresholds** — a 40% specificity that's unacceptable for a confirmatory test can be perfectly reasonable for a screening device.
- **AI-assisted diagnostics augment clinician judgment** rather than replace it. DermaSensor flags cases; the dermatologist decides next steps.
- Understanding **PPV and NPV** alongside sensitivity/specificity is essential because they shift with disease prevalence in the population.

---

## 📚 References

- Winkelmann, R. R., et al. (2023). Prospective clinical study of an AI-powered handheld device for skin cancer detection. *JAMA Dermatology*.
- Lallas, A., & Argenziano, G. (2020). Artificial intelligence and melanoma diagnosis. *Dermatology Practical & Conceptual*, 10(3).
- Topol, E. J. (2019). High-performance medicine: The convergence of human and artificial intelligence. *Nature Medicine*, 25, 44–56.
- Houston Community College. (2024). *ITAI-4375 Module 4: Diagnostic AI.*

---

*← [Back to Portfolio](../README.md)*
