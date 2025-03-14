# The Relationship Between Medicaid/CHIP Expenditures and Enrollment in the COVID-19 Public Health Emergency

## Overview

This project investigates the relationship between Medicaid/CHIP enrollment and expenditure costs before, during, and after the COVID-19 pandemic (2018-2023). Given the significant policy shifts, economic impact, and increased reliance on public healthcare programs during the pandemic, this study provides insights for policymakers, healthcare providers, and stakeholders.

## Data Description

The dataset consists of:
- **Medicaid & CHIP enrollment and expenditures** (2018-2023) from Medicaid.gov.
- **State-level demographic variables** from IPUMS NHGIS, US Census, and the American Community Survey.
- **Control variables** such as unemployment rate and median income.

### **Key Trends**
- Enrollment declined slightly from 2018 to 2019, but increased sharply in 2020 due to mass unemployment and continuous enrollment policies.
- Medicaid & CHIP expenditures increased steadily from 2018 to 2023, with rapid growth after 2020.
- Medicaid-to-CHIP enrollment ratios fluctuated significantly over time.
- Post-pandemic policies may lead to declines in enrollment as federal supports phase out.

## **Methodology**
### **First-Difference Regression with Fixed Effects**
We employed a first-difference regression model to analyze the impact of Medicaid expenditures on enrollment changes, accounting for:
- Year-over-year changes in Medicaid/CHIP enrollment and expenditures.
- COVID dummy variables (2020-2022) to isolate pandemic effects.
- Interaction terms to assess differential impacts during the pandemic.
- Control variables such as unemployment rate and median income.

**Model Specification:**
\[
\Delta \ln(\text{enrollment}) = \beta_0 + \beta_1 \cdot \Delta \ln(\text{expenditure}) + \beta_2 \cdot \text{COVID dummy} + \beta_3 \cdot (\Delta \ln(\text{expenditure}) \times \text{COVID dummy}) + \beta_4 \cdot \Delta(\text{control variables}) + \epsilon
\]

### **LSTM-Based Medicaid and CHIP Enrollment Prediction**
To predict future Medicaid/CHIP enrollment, we implemented a **Long Short-Term Memory (LSTM) model**, using:
- **Input features**: 14 demographic and economic factors.
- **Architecture**: 2-layer stacked LSTMs with dropout to prevent overfitting.
- **Training**: 80% train / 20% test split.
- **Optimization**: Adam optimizer with Mean Squared Error (MSE) loss function.

## **Findings**
### **Regression Analysis**
- Medicaid/CHIP enrollment increased significantly during COVID years.
- Changes in expenditures had a positive effect on enrollment but were not significantly different during the pandemic.
- Policymakers should not assume that increasing expenditures alone will drive higher enrollment in crisis periods.

### **LSTM Predictions**
- The model successfully captured enrollment trends.
- Future projections (2024-2026) suggest fluctuations, with a dip in 2025 and recovery in 2026.

## **Challenges & Limitations**
- **Data availability**: Limited demographic data for 2020, missing variables could not be imputed.
- **Policy confounders**: Federal stimulus packages and state-level variations were not directly modeled.
- **Granularity**: State-level analysis may not capture within-state disparities.
- **LSTM Limitations**: Computationally intensive and lacks interpretability for policy decisions.

## **Usage & Impact**
This study provides data-driven insights for:
- **State & Federal Policy**: Budget planning for Medicaid in public health crises.
- **Public Health Preparedness**: Evaluating continuous enrollment policies.
- **Healthcare Research**: Understanding economic and demographic trends in Medicaid participation.

