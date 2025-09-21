
#  Machine Learning Court: Loan Denial Case Study

##  Project Overview

This notebook investigates a real-world style case where an applicant, **Jane Dow**, was denied a premium credit product because a machine learning model predicted her income as ≤\$50K. Using **explainable AI (XAI)** methods, we analyze whether the model’s decision may have been unfair or biased.

The work is part of an assignment for exploring **fairness, transparency, and accountability in AI**.

---

##  Case Background

* **Applicant:** Jane Dow (37 years old, professional, Bachelor’s degree, full-time executive role)
* **Bank’s Model:** Trained on the UCI Adult Income dataset to predict income as a proxy for credit eligibility
* **Outcome:** Model predicted ≤\$50K → loan denied
* **Dispute:** Jane argues the model unfairly relied on irrelevant or biased features

---

## Methods Used

Applied two XAI techniques to analyze the decision:

1. **LIME (Local Interpretable Model-agnostic Explanations)**

   * Explains individual predictions (Jane’s case specifically)
   * Shows which features pushed her prediction toward approval (>50K) or denial (≤50K)

2. **SHAP (SHapley Additive exPlanations)**

   * Explains model behavior globally (all applicants) and locally (Jane’s case)
   * Highlights which features consistently influenced predictions

##  Key Findings

### LIME (Local)

* **Negative factors:** No capital gains, marital status, and certain country-related features
* **Positive factors:** Education level and occupation helped slightly, but not enough
* Suggests the model may unfairly penalize personal/social factors rather than financial capacity

### SHAP (Global)

* Top features: **Age, marital status, education, hours per week, capital gains**
* **Gender (male vs. female)** shows up as a feature with influence, raising fairness concerns
* The model relies heavily on demographic features that may encode bias

---

##  Conclusion

Both LIME and SHAP suggest that the loan denial may have been **unfairly influenced by personal or demographic features** (marital status, gender, native country), rather than strictly financial indicators. This raises concerns about **bias and fairness in AI decision-making** for high-stakes contexts like credit eligibility.

---

##  How to Run

1. Clone the repo and install requirements:

   ```bash
   git clone <repo_url>
   cd machine_learning_court
   pip install -r requirements.txt
   ```
2. Open the notebook:

   ```bash
   jupyter notebook machine_learning_court.ipynb
   ```
3. Run all cells to reproduce the LIME and SHAP analysis.
