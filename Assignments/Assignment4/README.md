# 🔬 Assignment 4: DermaSensor — AI Diagnostic Test Evaluation

## 📋 Overview

In this assignment, I evaluated the **DermaSensor**, an AI-powered handheld device designed to assist clinicians in detecting skin cancer by analyzing skin lesions using spectroscopy and machine learning algorithms. The goal was to critically assess its diagnostic accuracy and understand the real-world implications of its sensitivity and specificity metrics.

---

## 🧪 Methods

I analyzed the diagnostic performance of DermaSensor by examining its key clinical metrics:

- **Sensitivity (True Positive Rate)**: The ability to correctly identify patients who have skin cancer.
- **Specificity (True Negative Rate)**: The ability to correctly identify patients who do not have skin cancer.
- Constructed a confusion matrix to visualize the outcomes.
- Evaluated the clinical trade-offs of high sensitivity vs. low specificity.

---

## 📊 Results

### Diagnostic Performance Summary

| Metric | Value | Interpretation |
|--------|-------|---------------|
| **Sensitivity** | 96% | Correctly identifies 96 out of 100 cancer cases |
| **Specificity** | 40% | Correctly identifies only 40 out of 100 non-cancer cases |
| **False Negative Rate** | 4% | Misses 4 out of 100 actual cancer cases |
| **False Positive Rate** | 60% | Incorrectly flags 60 out of 100 healthy patients |

### Confusion Matrix (per 1,000 patients, assuming 10% prevalence)

| | Predicted Positive | Predicted Negative |
|---|---|---|
| **Actually Positive (100)** | 96 (True Positive) | 4 (False Negative) |
| **Actually Negative (900)** | 540 (False Positive) | 360 (True Negative) |

---

## 💬 Discussion

DermaSensor's **high sensitivity (96%)** makes it an excellent screening tool — it catches nearly all cancer cases, which is critical in a disease where a missed diagnosis can be life-threatening. However, its **low specificity (40%)** means that a large number of healthy patients are flagged as potentially having cancer, leading to unnecessary biopsies, patient anxiety, and increased healthcare costs.

This is a common trade-off in medical screening: prioritizing sensitivity to minimize missed cases at the cost of more false alarms. In the context of skin cancer, this trade-off is generally acceptable because the consequences of a missed melanoma far outweigh the burden of additional testing.

---

## 💡 What I Learned

- The difference between **sensitivity** and **specificity** and why both metrics are essential for evaluating any AI diagnostic tool.
- In cancer screening, **high sensitivity is prioritized** because missing a true positive (cancer) has far more severe consequences than a false alarm.
- AI diagnostic tools like DermaSensor are designed to **assist, not replace** dermatologists.
- **Prevalence** significantly impacts the predictive value of a test.

---

## 📚 References

1. DermaSensor, Inc. (2024). *CLIFF Study: Clinical validation of an AI-powered spectroscopy device for skin cancer detection.* JAAD.
2. Esteva, A., et al. (2017). *Dermatologist-level classification of skin cancer with deep neural networks.* Nature, 542(7639), 115-118.
3. FDA (2024). *FDA authorizes marketing of DermaSensor for skin cancer detection.*
4. Baratloo, A., et al. (2015). *Part 1: Simple definition and calculation of accuracy, sensitivity and specificity.* Emergency, 3(2), 48-49.

---

[⬅️ Back to Portfolio](../../README.md)
