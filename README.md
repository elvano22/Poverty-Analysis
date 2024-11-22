# Poverty-Analysis

This repository contains the analysis and modeling of poverty in Indonesia using statistical methods, particularly focusing on **Geographically Weighted Regression (GWR)**. The study identifies influential factors and constructs predictive models to analyze poverty across Indonesia's 34 provinces. 

## Key Insights

Two datasets were analyzed, **"Kemiskinan"** and **"Kemiskinan2"**, to determine which provides better insights into poverty modeling:
- **Kemiskinan2** outperformed **Kemiskinan** in terms of accuracy, explanatory power, and interpretability.
- All subsequent analysis and modeling use the **Kemiskinan2** dataset for its superior performance.

---

## Repository Contents

1. **`Kemiskinan.xlsx` and `Kemiskinan2.xlsx`**:
   - Datasets containing poverty data across Indonesia's provinces.
   - `Kemiskinan2` includes refined indicators for better model performance.

2. **`The Code.Rmd`**:
   - The R Markdown script for performing the statistical analysis and regression modeling.
   - Steps include data exploration, testing for multicollinearity, and building regression models (OLS, WLS, and GWR).

3. **`The Paper.docx`**:
   - Detailed documentation of the analysis, including methodology, results, and discussions.

---

## Methodology

### 1. Models Used
- **Ordinary Least Squares (OLS)**: Baseline linear regression model.
- **Weighted Least Squares (WLS)**: Addresses heteroscedasticity issues in OLS.
- **Geographically Weighted Regression (GWR)**: Incorporates spatial heterogeneity to improve model precision.

### 2. Evaluation Metrics
- **R-Squared**: Measures the proportion of variance explained by the model.
- **AIC (Akaike Information Criterion)**: Evaluates model fit, penalizing for complexity.

---

## Results: Why Kemiskinan2?

| Model | Dataset       | R-Squared | AIC      | Remarks                           |
|-------|---------------|-----------|----------|-----------------------------------|
| GWR   | **Kemiskinan2** | **81.95%** | **530.18** | Best fit; explains spatial variation effectively. |
| GWR   | Kemiskinan    | 74.03%    | 537.70   | Suboptimal; lower explanatory power. |
| OLS   | Kemiskinan2   | 60.34%    | 559.59   | Poor fit compared to GWR.         |
| OLS   | Kemiskinan    | 57.29%    | 556.11   | Lowest fit; lacks spatial insights.|

- **Kemiskinan2** enables GWR to achieve the highest R-Squared and lowest AIC values, making it the most effective dataset for capturing spatial variability in poverty.

---

## Steps to Reproduce

1. Install necessary R packages:
   ```R
   install.packages(c("sp", "ggplot2", "GWmodel", "car"))
   ```
2. Open `The Code.Rmd` in RStudio or another compatible IDE.
3. Run the script to perform:
   - Data preprocessing
   - Model training and evaluation
   - Visualizations and result interpretation.

---

## Conclusion

The **GWR model** using **Kemiskinan2** is the most effective for analyzing poverty in Indonesia:
- Explains 81.95% of data variability (R-Squared).
- Provides actionable insights for targeted poverty reduction strategies.
- Highlights key variables such as **education completion rate**, **adequate sanitation**, and **drinking water** as critical to reducing poverty.

For further exploration, future research can incorporate advanced machine learning techniques or additional socioeconomic indicators to enhance the model.
