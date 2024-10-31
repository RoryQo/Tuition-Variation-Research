<div align="center"> 

# Tuition Variation and Prediction Project
<br>

[![Download Full Paper](https://img.shields.io/badge/Download%20Full%20Paper-0056A0?style=for-the-badge&logo=github&logoColor=white&labelColor=0056A0)](https://raw.githubusercontent.com/RoryQo/R-Tuition-Variation-Research/main/Full%20Paper%3A%20Paying%20for%20Prestige.pdf)


</div>


<table align="center">
  <tr>
    <td colspan="2" align="center" style="background-color: white; color: black;"><strong>Table of Contents</strong></td>
  </tr>
  <tr>
    <td style="background-color: white; color: black; padding: 10px;">1. <a href="#statement-of-purpose" style="color: black;">Statement of Purpose</a></td>
    <td style="background-color: gray; color: black; padding: 10px;">6. <a href="#data" style="color: black;">Data</a></td>
  </tr>
  <tr>
    <td style="background-color: gray; color: black; padding: 10px;">2. <a href="#abstract" style="color: black;">Abstract</a></td>
    <td style="background-color: white; color: black; padding: 10px;">7. <a href="#usage" style="color: black;">Usage</a></td>
  </tr>
  <tr>
    <td style="background-color: white; color: black; padding: 10px;">3. <a href="#key-findings" style="color: black;">Key Findings</a></td>
    <td style="background-color: gray; color: black; padding: 10px;">8. <a href="#limitations-and-future-research" style="color: black;">Limitations and Future Research</a></td>
  </tr>
  <tr>
    <td style="background-color: gray; color: black; padding: 10px;">
      4. <a href="#methodology" style="color: black;">Methodology</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#data-collection" style="color: black;">Data Collection</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#variables" style="color: black;">Variables</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#wrangling" style="color: black;">Wrangling</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#exploration" style="color: black;">Exploration</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#statistical-modeling" style="color: black;">Statistical Modeling</a>
    </td>
    <td style="background-color: gray; color: black; padding: 10px;">
      5. <a href="#model-summary" style="color: black;">Model Summary</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#regression-results" style="color: black;">Regression Results</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#regression-analysis" style="color: black;">Regression Analysis</a><br>
      &nbsp;&nbsp;&nbsp;- <a href="#model-assumptions" style="color: black;">Model Assumptions</a>
    </td>
  </tr>
</table>















## Statement of Purpose
This paper isolates and uses key factors to predict tuition for public and private four-year universities across the United States within the same year. Institutional, quality of life, and crime rate metrics are observed to explain the differences between current university tuition rates. While much research has been conducted to explain time series data of tuition increases, research to explain the variation in tuition prices while holding time constant is scarce. Understanding these variations can provide insights into time series research and establish market value for colleges based on key predictors, helping students maximize their return on investment and minimize student loan debt.

## Abstract
This paper isolates and uses key factors to predict tuition for public and private four-year universities within the same year. A total of 60 observations from the top 400 US universities are analyzed using seven predictors in a linear model. The model accounts for over 85% of the variability in tuition rates, with the university's national ranking identified as the only significant institutional metric contributing to tuition cost.

## Key Findings
These results show that we can explain most of the tuition variability while holding time constant. Tuition increases as the school ranks improve. This relationship is expected because more desirable (prestigious) schools can leverage this and charge their students a premium. What's impressive is the significance of this relationship. In a simple linear regression, Rank accounts for 65% of tuition variation.
	
 Variables in this model that were insignificant tell us just as much about the higher education market as the ones that were. Besides Rank, no other ***institutional*** metrics were statistically significant at the 0.1 confidence level (excluding the private vs. public control). Student-to-faculty ratios, graduation rate, or percentage of alumni donating to the university were irrelevant to predicting tuition despite these metrics being widely touted and used in recruitment brochures and websites. Today's college students pay for Prestige rather than a school that invests in them.

To evaluate my own tuition costs, I applied the model to the University of Pittsburgh (Pitt). The analysis indicated that out-of-state students face tuition that is approximately $9,000 above the expected value. This indicates that, as out-of-state student at pitt are receiving a lower than average ROI. Unfortunately, I did not have data to apply to in-state tuition or cost-after aid.  As an in-state student, I have a much higher ROI than out-of-state students, considering we are both receiving the same education. Notably, the model's successful prediction of Pitt's tuition underscores its practical applicability in real-world scenarios, offering valuable insights for prospective students evaluating their educational investments.

## Methodology

### Data Collection
The data used for this model consists of 60 observations representing four-year universities in the US, sourced from three publicly available datasets. These datasets include metrics such as institutional characteristics, quality of life, and crime rates.

### Variables
The study uses seven predictors:
- **Institutional Control**: Categorical variable indicating if a university is public (0) or private (1).
- **Rank**: National ranking assigned by US News and World Report.
- **Number of Undergraduates**: Total number of undergraduates attending the university in 2020.
- **Unemployment**: Percentage of the city's population that is unemployed.
- **Median Income**: Reported median income for the surrounding city.
- **Diversity Rank**: Ranking of the city's racial diversity (lower is more diverse).
- **Expenditure per Student**: Financial resources spent per student.


### Wrangling
- Conducted systematic data cleaning and organization to prepare for analysis:
  - Merged three separate datasets to create a comprehensive dataset:
    - **US College Data** from Kaggle, providing institutional characteristics.
    - **Quality of Life Data** sourced from the FCC, offering economic indicators.
    - **Crime Rates by City** dataset from City-Data.com, detailing safety metrics.
  - Identified and addressed missing values through imputation or removal.
  - Categorical variables were appropriately encoded for analysis.
  - Checked continuous variables for outliers and inconsistencies.
- Ensured all variables were correctly formatted to align with analytical requirements.
- Final dataset comprised 60 well-structured observations reflecting top US universities.


### Exploration
- Conducted data exploration through visualizations and descriptive statistics:
  - Utilized histograms and scatter plots to illustrate the distribution of tuition rates and correlations among predictors.
  - Calculated descriptive statistics to summarize central tendency, dispersion, and data distribution shape.
- Identified patterns and anomalies in the data, informing the modeling process and enhancing understanding of factors influencing tuition rates across institutions.
<img src="https://raw.githubusercontent.com/RoryQo/R-Tuition-Variation-Research/main/graph1.jpg" width="400" />



### Statistical Modeling
  ```math
     Tuition = \beta_0 + \beta_1 institution_i + \beta_2 rank + \beta_3 undergrads + \beta_4 unemployment +\beta_5 income + \beta_6 diversity + \beta_7 expenditure + \epsilon_i
  ```
<br>

- Constructed a comprehensive linear model using seven identified predictors to assess tuition variability.

```
# Model selection
# Use Forward and Backward Stepwise Regression Selection (AIC)

min_model = lm(Tuition ~ 1, data = obs_60_final)
max_model = formula(lm(Tuition ~ Rank + S.F.Ratio + Unemployment + Diversity_Rank_Race + Expend+ institutionalControl+number_Undergrads+Median_Income+Grad.Rate+Crime.Rate+Cost_of_Living, data = obs_60_final))
best_model = step(min_model, direction = "both", scope = max_model)

# View best model
best_model
```
- Employed leave-one-out cross-validation (LOOCV) for model validation:
  - Iteratively trained the model on all observations except one.
  - Used the excluded observation as a test set.
  - Provided a rigorous assessment of predictive capabilities across multiple iterations.
```
  # Model validation
# Use Leave One Our Cross Validation

ctrl = trainControl(method = "LOOCV")
model1 = train(Tuition ~ Rank + institutionalControl + Median_Income + 
Diversity_Rank_Race + Unemployment + number_Undergrads + Expend, data = obs_60_final, method = "lm", trControl = ctrl)
model1$results
```



## Model Summary
The model results reveal significant predictors of tuition rates. The analysis provides estimates for each predictor, indicating that higher(numerically)-ranked institutions tend to have lower tuition. Significant predictors include institutional control, rank, median income, and expenditure per student.

### Regression Results

<div style="display: flex; justify-content: center; align-items: flex-start;">
  <img src="https://raw.githubusercontent.com/RoryQo/Tuition-Variation-Research/main/graph3.jpg" alt="Graph 3" style="width: 45%; height: auto;">
  <img src="https://raw.githubusercontent.com/RoryQo/Tuition-Variation-Research/main/graph4.jpg" alt="Graph 4" style="width: 45%; height: auto;">
</div>

### Regression Analysis
- Focused on fitting a linear model to the cleaned dataset using selected predictors.
- Evaluated the significance of each predictor's contribution to the overall model:
  - Highlighted the critical role of institutional rank in explaining tuition variability.
  - Demonstrated that other metrics were largely insignificant.
- Indicated minimal overfitting using leave-one-out cross-validation (LOOCV):
  - R-squared value remained stable across various data subsets.
  - Suggested effective generalization to unseen data, enhancing model reliability.

### Model Assumptions
- Check model assumptions with QQ and residual plot
	- The plot show a random distribution of residuals about zero (no clear pattern)
 	- The qq plot shows that the pattern of residuals follows a straight line indicating a linear relationship.

<img src="https://raw.githubusercontent.com/RoryQo/Tuition-Variation-Research/main/graph2.jpg" alt="Graph 2" style="width: 50%; height: auto;">



## Data
The datasets were collected from reputable sources, ensuring quality and reliability. The final dataset was cleaned and prepared for analysis, focusing on the top 400 universities in the US.

## Usage
To use the analysis scripts:
1. **Install Required Packages**: Ensure you have the necessary R packages installed.
2. **Load the Data**: Import the cleaned dataset for analysis.
3. **Run the Analysis**: Execute the provided R scripts to generate the model and visualizations.
4. **Review Results**: Analyze the summaries and visualizations to interpret the findings.

## Limitations and Future Research
While the model performed well, the sample size is limited, which may not capture the full variability in tuition prices. Future research could explore differences between public and private institutions more deeply or validate the model with different datasets to identify evolving market factors.

## References
- DeLeeuw, J. (2012). "Unemployment rate and tuition as enrollment predictors."
- Hanson, M. (2023). Student Loan Debt Statistics. Education Data Initiative.
- Lucca, D. O., Nadauld, T., & Shen, K. (2018). "Credit Supply and the Rise in College Tuition."
- McGurran, B. (2023). College Tuition Inflation: Compare The Cost Of College Over Time.
- Vaughan, Z. (2016). "City/Zip/County/FIPS- Quality of Life (US)."
- Wahyuddin, S., Fauzi, I. E., & Rijanto, E. (2019). "Analysis of Factors Affecting Tuition Fee in a Private University."
