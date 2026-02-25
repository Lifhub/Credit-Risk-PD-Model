# Credit-Risk-PD-Model
Probability of Default (PD) modeling using Logistic Regression and Basel III standards.
# Credit Risk Framework: Probability of Default (PD) Modeling

## Project Overview
This project develops a transparent, Basel-compliant Credit Scorecard framework to estimate the **Probability of Default (PD)** for a consumer loan portfolio. Rather than utilizing a "black-box" machine learning approach, I implemented a **Logistic Regression** model paired with **Weight of Evidence (WoE)** transformations. This ensures the model meets the high interpretability standards required by institutional risk management and regulatory bodies.

## Key Quantitative Features
* **Feature Engineering:** Implemented **Weight of Evidence (WoE)** binning to transform non-linear variables (Income, DTI) into a linear risk scale.
* **Feature Selection:** Utilized **Information Value (IV)** to quantify the predictive power of variables and prevent model noise.
* **Calibration:** Developed a scaling engine to transform raw probabilities into a standard **300-850 Credit Score** using the "Points to Double the Odds" (PDO) methodology.
* **Validation:** Focused on the **Gini Coefficient** and **AUC-ROC** as primary metrics to assess the model's discriminatory power in the presence of class imbalance.

### **Mathematical Methodology**

To ensure the model remains robust and compliant with Basel III regulatory standards, the following mathematical transformations were applied:

#### **1. Weight of Evidence (WoE)**
Used to linearize features and handle outliers, WoE measures the strength of a grouping for separating "Good" and "Bad" risk:
$$WoE_i = \ln \left( \frac{\% \text{ Non-Events}_i}{\% \text{ Events}_i} \right)$$
 
#### **2. Information Value (IV)**
Variables were selected based on their Information Value to ensure maximum predictive power without overfitting:

$$IV = \sum_{i=1}^{n} \left( \% \text{ Non-Events}_i - \% \text{ Events}_i \right) \times WoE_i$$

#### **3. Model Validation**
The model's discriminatory power is evaluated via the **Gini Coefficient**, derived from the Area Under the ROC Curve (AUC):

$$Gini = 2 \times AUC - 1$$

## Technical Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib
* **Methodology:** Logistic Regression, WoE/IV, Scorecard Scaling
