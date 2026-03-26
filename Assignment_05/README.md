# 🩺 Assignment 5: Prognostic Model — Mirai Breast Cancer Prediction

**Course:** ITAI-4375 AI in Healthcare | Houston Community College  
**Student:** Win Aung | **Instructor:** Professor Doreen Rosenstrauch  

---

## 📌 Overview

This assignment examines **Mirai**, a deep learning prognostic model developed by researchers at MIT and Massachusetts General Hospital to predict **future breast cancer risk** from a single mammogram. Unlike diagnostic tools that identify existing disease, Mirai is a *prognostic* model — it estimates the probability that a patient will develop breast cancer over the next 1–5 years.

Mirai represents a paradigm shift from reactive detection (finding cancer that already exists) to proactive risk stratification (identifying who is most likely to develop cancer in the future), enabling earlier interventions and personalized screening schedules.

---

## 🧪 Methods

### Model Architecture
Mirai is a **convolutional neural network (CNN)** trained on digital mammography images. It learns complex imaging features associated with long-term cancer risk — features that human radiologists may not consciously register.

| Component | Description |
|-----------|-------------|
| **Input** | Full mammogram image (all 4 standard views) |
| **Architecture** | Multi-task CNN with risk calibration layer |
| **Training Data** | 200,000+ mammograms from MGH (2000–2017) |
| **Output** | 1-year, 2-year, 3-year, 4-year, and 5-year risk scores |
| **Validation** | Multi-institutional across diverse populations |

### Evaluation Metric: AUC
The primary performance metric is the **Area Under the Receiver Operating Characteristic Curve (AUC)**:

| AUC Range | Interpretation |
|-----------|---------------|
| 1.0 | Perfect classifier |
| **0.76** | **Mirai (breast cancer, 5-year)** |
| 0.70–0.79 | Acceptable / Good performance |
| 0.50 | No better than random chance |

The **ROC curve** plots:
- **X-axis:** False Positive Rate (1 − Specificity)
- **Y-axis:** True Positive Rate (Sensitivity)

AUC summarizes overall discriminative ability across all possible classification thresholds.

---

## 📊 Results

| Metric | Mirai | Tyrer-Cuzick (traditional model) |
|--------|-------|----------------------------------|
| **5-Year AUC** | **0.76** | 0.62 |
| Short-term (1-yr) AUC | 0.82 | 0.68 |
| High-risk group enrichment | 2.87× | 1.85× |
| Populations validated | USA, Sweden, Singapore | USA only |

### Key Findings

- Mirai outperforms the gold-standard **Tyrer-Cuzick** clinical risk model by a meaningful margin (AUC 0.76 vs. 0.62).
- The model generalizes across **diverse patient populations and imaging equipment**, addressing a common limitation of AI in healthcare.
- Patients identified as "high risk" by Mirai were **nearly 3× more likely** to develop breast cancer within 5 years compared to the overall screened population.
- Mirai's predictions are **independent of traditional risk factors** (family history, BRCA status), meaning it captures imaging-based signals not encoded in clinical risk calculators.

### Clinical Implications

```
Mirai High-Risk Flag
      │
      ▼
Supplemental MRI screening + shorter recall intervals
      │
      ▼
Earlier stage detection → improved survival rates
```

---

## 💡 What I Learned

- **Prognosis and diagnosis are fundamentally different AI tasks** — prognosis predicts future events; diagnosis identifies present disease.
- **AUC is a threshold-independent metric** that tells us how well the model ranks patients by risk, regardless of the specific cutoff used.
- Deep learning can extract **latent imaging biomarkers** invisible to the human eye, providing value beyond expert radiologist interpretation.
- **Validation across diverse populations** is critical for AI health tools — a model that only works on one demographic is not ready for real-world deployment.
- **Prognostic AI creates ethical responsibilities** — telling someone they have a high 5-year cancer risk has psychological and financial consequences that require careful clinical communication.
- Combining AI risk scores with human clinical factors (family history, lifestyle) provides a more comprehensive risk picture than either alone.

---

## 📚 References

- Yala, A., et al. (2021). Toward robust mammography-based models for breast cancer risk. *Science Translational Medicine*, 13(578).
- Shen, Y., et al. (2021). AI system reduces false-positive findings in breast ultrasound. *Nature Communications*, 12, 5645.
- Lehman, C. D., et al. (2019). Mammographic breast density assessment using deep learning. *Radiology*, 290(1), 52–59.
- Houston Community College. (2024). *ITAI-4375 Module 5: Prognostic AI Models.*

---

*← [Back to Portfolio](../README.md)*
