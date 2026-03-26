# 🌍 Assignment 6: Social Determinants of Health (SDOH) and AI

**Course:** ITAI-4375 AI in Healthcare | Houston Community College  
**Student:** Win Aung | **Instructor:** Professor Doreen Rosenstrauch  

---

## 📌 Overview

This assignment explores how **Social Determinants of Health (SDOH)** — non-medical factors such as food insecurity, housing instability, and education level — profoundly influence individual and population health outcomes. More importantly, it examines how **artificial intelligence can identify, predict, and address** SDOH gaps to reduce health disparities.

The World Health Organization defines SDOH as "the conditions in which people are born, grow, live, work, and age." These factors account for **30–55% of health outcomes** — often more than clinical care itself. Addressing SDOH requires AI tools that go beyond the clinic and into communities.

---

## 🧪 Methods

### Framework: Healthy People 2030 SDOH Domains

| Domain | Examples | Health Impact |
|--------|----------|--------------|
| 🍎 **Food Insecurity** | Hunger, poor nutrition, food deserts | Diabetes, obesity, poor immunity |
| 🏠 **Housing Instability** | Homelessness, overcrowding, lead exposure | Mental illness, asthma, injury |
| 🎓 **Education** | Low literacy, school dropout | Lower health literacy, worse outcomes |
| 💼 **Economic Stability** | Poverty, unemployment | Stress, deferred care |
| 🏘️ **Community Context** | Violence, discrimination, social isolation | Depression, cardiovascular disease |

### AI Approaches for SDOH

| AI Method | SDOH Application |
|-----------|-----------------|
| **Predictive modeling** | Identify patients at risk of food insecurity using EHR + census data |
| **NLP on clinical notes** | Extract unstructured SDOH mentions from physician notes |
| **Risk stratification** | Prioritize social worker referrals for highest-need patients |
| **Geospatial AI** | Map food deserts and housing risk zones at zip-code level |
| **Chatbots / conversational AI** | Screen patients for SDOH needs at check-in |

---

## 📊 Results

### Focus Area 1: Food Insecurity 🍎

- **Prevalence:** ~10.5% of U.S. households experience food insecurity (USDA, 2022).
- **Health consequences:** 2× higher rate of type 2 diabetes; increased hospitalization.
- **AI solution:** Machine learning models trained on Medicaid claims + neighborhood-level census variables can identify food-insecure patients with >80% accuracy, enabling automatic referrals to food banks or SNAP enrollment assistance.

### Focus Area 2: Housing Instability 🏠

- **Prevalence:** ~580,000 Americans experience homelessness on any given night.
- **Health consequences:** 3–4× higher mortality rate; unmanaged chronic conditions; substance use.
- **AI solution:** Predictive algorithms can flag patients at risk of housing instability prior to discharge, enabling hospital social workers to intervene before homelessness occurs.

### Focus Area 3: Education & Health Literacy 🎓

- **Prevalence:** ~36% of U.S. adults have limited health literacy (NAAL).
- **Health consequences:** Medication non-adherence, inability to navigate the healthcare system, delayed diagnoses.
- **AI solution:** NLP-powered patient portals can simplify clinical documentation to an 8th-grade reading level automatically. AI health coaches provide plain-language education tailored to individual literacy levels.

### Summary Table

| SDOH Factor | Population Affected | AI Tool | Expected Outcome |
|-------------|--------------------|---------|--------------------|
| Food insecurity | 34M Americans | Predictive ML + referral automation | ↓ diabetes complications |
| Housing instability | 580K homeless | Discharge risk scoring | ↓ readmissions |
| Low health literacy | 77M adults | NLP document simplification | ↑ medication adherence |

---

## 💡 What I Learned

- **SDOH are upstream causes of disease** — treating only the biological manifestations of illness without addressing root social causes results in revolving-door healthcare.
- **AI alone cannot solve SDOH** — it can identify need and route referrals, but community resources, policy changes, and human caseworkers are essential partners.
- **Algorithmic bias is a major concern** — if AI models are trained on data that underrepresents marginalized communities, they may systematically miss the populations most in need.
- **EHR systems are underutilized** — most EHRs collect some SDOH data but rarely use it for automated risk scoring or referral generation.
- **Intersectionality matters** — patients often face multiple simultaneous SDOH challenges, and AI models must account for these compounding effects rather than treating each factor in isolation.
- Addressing SDOH is not just ethically right — it is **economically efficient**: every $1 invested in addressing SDOH saves an estimated $4.00 in acute care costs.

---

## 📚 References

- Healthy People 2030. (2024). *Social Determinants of Health.* U.S. Department of Health and Human Services. https://health.gov/healthypeople/priority-areas/social-determinants-health
- Obermeyer, Z., Powers, B., Vogeli, C., & Mullainathan, S. (2019). Dissecting racial bias in an algorithm used to manage the health of populations. *Science*, 366(6464), 447–453.
- Gottlieb, L. M., et al. (2020). Advancing social prescribing with implementation science. *JMIR*, 3(4).
- Houston Community College. (2024). *ITAI-4375 Module 6: AI and Social Determinants of Health.*

---

*← [Back to Portfolio](../README.md)*
