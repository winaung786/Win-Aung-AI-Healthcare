# 👨‍⚕️ Assignment 7: Case Study — AI Risk Stratification for a Diabetic Patient

**Course:** ITAI-4375 AI in Healthcare | Houston Community College  
**Student:** Win Aung | **Instructor:** Professor Doreen Rosenstrauch  

---

## 📌 Overview

This assignment presents a **clinical case study** of a 58-year-old patient — Mr. James Carter — living with **Type 2 Diabetes Mellitus (T2DM)** for 12 years. The case identifies three high-priority health risks identified through AI-driven clinical decision support, and proposes corresponding AI-powered interventions to reduce those risks and improve long-term outcomes.

This type of case analysis mirrors real-world clinical practice where AI tools are increasingly embedded into the electronic health record (EHR) workflow to flag at-risk patients before crises occur.

---

## 🏥 Patient Profile

| Attribute | Detail |
|-----------|--------|
| **Name** | Mr. James Carter (fictional) |
| **Age** | 58 years old |
| **Condition** | Type 2 Diabetes Mellitus (12 years) |
| **HbA1c** | 9.2% (poorly controlled; target < 7%) |
| **BMI** | 34.1 (Obese Class I) |
| **Blood Pressure** | 148/92 mmHg (Stage 2 Hypertension) |
| **Medications** | Metformin 1000 mg BID, Lisinopril 10 mg QD |
| **Social History** | Lives alone, food-insecure, limited mobility |
| **Last Ophthalmology Visit** | 3 years ago |

---

## 🧪 Methods

### AI Risk Stratification Approach

Mr. Carter's EHR data was fed into an **AI-powered risk stratification engine** that integrates:
- Structured clinical data (labs, vitals, medications)
- Unstructured clinical notes (NLP-extracted SDOH flags)
- Population health benchmarks

The system generated a **composite risk score** and identified three prioritized, actionable risks.

---

## 📊 Results

### Risk 1: Diabetic Retinopathy 👁️

| Item | Detail |
|------|--------|
| **Risk Level** | High (no eye exam in 3 years; HbA1c 9.2%) |
| **AI Tool** | DeepMind's EyeCare / Google Diabetic Retinopathy AI |
| **How it works** | CNN analyzes retinal fundus photographs for microaneurysms, hemorrhages, and neovascularization |
| **Performance** | AUC 0.99; sensitivity 90%, specificity 98% |
| **AI Recommendation** | Immediate referral for retinal screening; telemedicine option available |
| **Expected Outcome** | Early-stage retinopathy detected and treated → prevention of blindness |

> **Clinical Reasoning:** With an HbA1c of 9.2% for over a decade, Mr. Carter has a high cumulative glycemic exposure. The 3-year gap in ophthalmology visits puts him at significant risk for undetected sight-threatening retinopathy.

---

### Risk 2: Diabetic Kidney Disease (Nephropathy) 🫘

| Item | Detail |
|------|--------|
| **Risk Level** | Moderate-High (hypertension + poor glycemic control) |
| **AI Tool** | CKD progression prediction model (eGFR trajectory AI) |
| **How it works** | Time-series ML model uses sequential creatinine, eGFR, and blood pressure values to predict CKD stage progression over 24 months |
| **Performance** | C-statistic 0.81; validated in VA healthcare system |
| **AI Recommendation** | Order urine albumin-to-creatinine ratio (UACR); intensify Lisinopril if UACR > 30 mg/g |
| **Expected Outcome** | Early CKD detected → slowed progression → avoided dialysis |

> **Clinical Reasoning:** Hypertension + T2DM is the leading cause of end-stage renal disease (ESRD). Mr. Carter's BP of 148/92 mmHg is undertreated, accelerating nephron damage.

---

### Risk 3: 30-Day Readmission / Avoidable Hospitalization 🏨

| Item | Detail |
|------|--------|
| **Risk Level** | High (food insecurity + social isolation + poor adherence) |
| **AI Tool** | EPIC's Deterioration Index / Jvion Care Optimization AI |
| **How it works** | Gradient boosting model integrating clinical + SDOH factors to predict hospitalization within 30 days |
| **Performance** | AUC 0.78; outperforms traditional LACE score |
| **AI Recommendation** | Assign care coordinator; connect to community food program; medication adherence reminder app |
| **Expected Outcome** | Reduced ER visits; lower hospitalization costs; improved quality of life |

> **Clinical Reasoning:** Living alone, being food-insecure, and having limited mobility means Mr. Carter lacks the support system needed to manage a complex chronic disease. Social isolation is independently associated with 29% higher mortality in diabetic patients.

---

### Summary of AI-Recommended Actions

| Priority | Risk | AI Tool | Action |
|----------|------|---------|--------|
| 🔴 High | Diabetic Retinopathy | DL fundus image AI | Teleretinal screening referral |
| 🟠 Moderate-High | Diabetic Nephropathy | eGFR trajectory ML | Order UACR; optimize BP meds |
| 🔴 High | Avoidable Hospitalization | Readmission AI + SDOH | Assign care coordinator + SNAP referral |

---

## 💡 What I Learned

- **AI transforms reactive care into proactive care** — rather than waiting for Mr. Carter to lose his vision or develop end-stage kidney disease, AI identifies risk years before complications emerge.
- **Risk stratification requires multi-modal data** — combining labs, vitals, imaging, and social data produces far richer risk estimates than any single data type alone.
- **SDOH integration is non-optional** — Mr. Carter's food insecurity and social isolation are as clinically relevant as his HbA1c. Ignoring them produces incomplete risk assessments.
- **AI tools must be actionable** — a risk score is only valuable if it triggers a concrete, feasible clinical or social intervention.
- **Patient communication matters** — presenting AI-generated risk scores to patients requires sensitivity and health literacy awareness; not every patient can or should receive probabilistic risk data without support.
- **Clinicians remain in the decision loop** — AI flags the risks; the physician and care team decide how to respond, weighing patient preferences and available resources.

---

## 📚 References

- Gulshan, V., et al. (2016). Development and validation of a deep learning algorithm for detection of diabetic retinopathy. *JAMA*, 316(22), 2402–2410.
- Tangri, N., et al. (2016). A predictive model for progression of chronic kidney disease to kidney failure. *JAMA*, 315(16), 1765–1766.
- Rajkomar, A., et al. (2018). Scalable and accurate deep learning with electronic health records. *NPJ Digital Medicine*, 1, 18.
- Houston Community College. (2024). *ITAI-4375 Module 7: AI Case Studies in Chronic Disease.*

---

*← [Back to Portfolio](../README.md)*
