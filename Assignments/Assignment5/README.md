# 🧬 Assignment 5: Mirai — Breast Cancer Prognostic Model

## 📋 Overview

In this assignment, I analyzed **Mirai**, a deep learning model developed by researchers at MIT and Massachusetts General Hospital (MGH) that predicts a patient's risk of developing breast cancer within 1 to 5 years using standard mammogram images. Unlike diagnostic AI (which identifies existing disease), Mirai is a **prognostic model** — it forecasts future risk to enable earlier intervention.

---

## 🧪 Methods

I examined Mirai's approach by reviewing:

- **Model Architecture**: A deep convolutional neural network trained on over 200,000 mammograms.
- **Input Data**: Standard screening mammograms (no additional clinical data required).
- **Validation**: Tested across diverse populations in the U.S., Sweden, and Taiwan.
- **Performance Metric**: Area Under the ROC Curve (AUC) as the primary evaluation metric.
- Compared Mirai's performance against traditional risk models (Tyrer-Cuzick and Gail).

---

## 📊 Results

### Model Performance Comparison

| Model | AUC | Input Data | Prediction Window |
|-------|-----|-----------|-------------------|
| **Mirai** | **0.76** | Mammogram images only | 1–5 years |
| Tyrer-Cuzick | 0.62 | Clinical risk factors + family history | Lifetime |
| Gail Model | 0.58 | Age, family history, reproductive factors | 5-year |

### AUC Interpretation Guide

| AUC Range | Performance Level | Meaning |
|-----------|------------------|--------|
| 0.90–1.00 | Excellent | Near-perfect discrimination |
| 0.80–0.89 | Good | Strong predictive ability |
| **0.70–0.79** | **Fair** | **Useful for clinical screening (Mirai = 0.76)** |
| 0.60–0.69 | Poor | Limited clinical utility |
| 0.50 | No Discrimination | Equivalent to random chance |

---

## 💬 Discussion

Mirai represents a significant advancement in breast cancer risk prediction:

- **Image-Only Input**: Unlike traditional models that require detailed clinical questionnaires, Mirai uses only the mammogram image.
- **Diverse Validation**: Mirai maintained consistent performance across different patient populations worldwide.
- **Short-Term Risk Focus**: By predicting 1–5 year risk, Mirai helps clinicians identify women who may benefit from supplemental screening or preventive interventions sooner.
- **Limitations**: An AUC of 0.76 means the model is not perfect — it should complement, not replace, clinical judgment.

---

## 💡 What I Learned

- **Prognostic AI differs from Diagnostic AI**: Diagnostic models answer "Does the patient have cancer now?" while prognostic models answer "Will the patient develop cancer in the future?"
- **AUC is a powerful metric** for comparing models, but it does not capture the full clinical picture.
- **AI models trained on images** can capture subtle patterns invisible to the human eye.
- **Equitable validation** is critical — an AI model must work across diverse populations.

---

## 📚 References

1. Yala, A., et al. (2021). *Toward robust mammography-based models for breast cancer risk.* Science Translational Medicine, 13(578).
2. Yala, A., et al. (2019). *A deep learning mammography-based model for improved breast cancer risk prediction.* Radiology, 292(1), 60–66.
3. Tyrer, J., Duffy, S. W., & Cuzick, J. (2004). *A breast cancer prediction model.* Statistics in Medicine, 23(7), 1111–1130.
4. Gail, M. H., et al. (1989). *Projecting individualized probabilities of developing breast cancer.* JNCI, 81(24), 1879–1886.

---

[⬅️ Back to Portfolio](../../README.md)
