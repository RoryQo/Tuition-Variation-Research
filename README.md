<div align="center">

# Tuition Variation and Prediction Project

</div>

## Table of Contents
1. [Statement of Purpose](#statement-of-purpose)
2. [Abstract](#abstract)
3. [Key Findings](#key-findings)
4. [Methodology](#methodology)
   - [Data Collection](#data-collection)
   - [Variables](#variables)
   - [Statistical Modeling](#statistical-modeling)
   - [Wrangling](#wrangling)
   - [Regression Analysis](#regression-analysis)
   - [Exploration](#exploration)
5. - [Model Summary](#model-summary)
6. [Data](#data)
7. [Usage](#usage)
8. [Limitations and Future Research](#limitations-and-future-research)
9. [References](#references)

## Statement of Purpose
This paper isolates and uses key factors to predict tuition for public and private four-year universities across the United States within the same year. Institutional, quality of life, and crime rate metrics are observed to explain the differences between current university tuition rates. While much research has been conducted to explain time series data of tuition increases, research to explain the variation in tuition prices while holding time constant is scarce. Understanding these variations can provide insights into time series research and establish market value for colleges based on key predictors, helping students maximize their return on investment and minimize student loan debt.

## Abstract
This paper isolates and uses key factors to predict tuition for public and private four-year universities within the same year. A total of 60 observations from the top 400 US universities are analyzed using seven predictors in a linear model. The model accounts for over 85% of the variability in tuition rates, with the university's national ranking identified as the only significant institutional metric contributing to tuition cost.

## Key Findings
These results show that we can explain most of the tuition variability while holding time constant. Tuition increases as the school ranks improve. This relationship is expected because more desirable (prestigious) schools can leverage this and charge their students a premium. What's impressive is the significance of this relationship. In a simple linear regression, Rank accounts for 65% of tuition variation.
	
 Variables in this model that were insignificant tell us just as much about the higher education market as the ones that were. Besides Rank, no other institutional metrics were statistically significant at the 0.1 confidence level (excluding the private vs. public control). Student-to-faculty ratios, graduation rate, or percentage of alumni donating to the university were irrelevant to predicting tuition despite these metrics being widely touted and used in recruitment brochures and websites. Today's college students pay for Prestige rather than a school that invests in them.

To evaluate my own tuition costs, I applied the model to the University of Pittsburgh (Pitt). The analysis indicated that out-of-state students face tuition that is approximately $9,000 above the expected value. This indicates that, as an in-state student, I am likely receiving a higher return on investment (ROI) compared to my out-of-state peers. Notably, the model's successful prediction of Pitt's tuition underscores its practical applicability in real-world scenarios, offering valuable insights for prospective students evaluating their educational investments.

## Methodology

### Data Collection
The data used for this model consists of 60 observations representing four-year universities in the US, sourced from three public datasets available on Kaggle. These datasets include metrics such as institutional characteristics, quality of life, and crime rates.

### Variables
The study uses seven predictors:
- **Institutional Control**: Categorical variable indicating if a university is public (0) or private (1).
- **Rank**: National ranking assigned by US News and World Report.
- **Number of Undergraduates**: Total number of undergraduates attending the university in 2020.
- **Unemployment**: Percentage of the city's population that is unemployed.
- **Median Income**: Reported median income for the surrounding city.
- **Diversity Rank**: Ranking of the city's racial diversity (lower is more diverse).
- **Expenditure per Student**: Financial resources spent per student.

### Statistical Modeling
A linear model was constructed using the seven predictors to assess the variability of tuition across universities. Leave-one-out cross-validation (LOOCV) was utilized to validate the model.

### Wrangling
Data was cleaned and organized to ensure compatibility with the analysis. Missing values were addressed, and variables were formatted correctly.

### Regression Analysis
The regression analysis involved fitting a linear model to the data using the selected predictors. The use of leave-one-out cross-validation (LOOCV) indicated minimal overfitting, as the R-squared value remained stable across different subsets of the data. This suggests that the model generalizes well to unseen data, enhancing its reliability for future applications.

### Exploration
Data exploration included visualizations and descriptive statistics to understand the distribution and relationships among the variables.

## Model Summary
The model results reveal significant predictors of tuition rates. The analysis provides estimates for each predictor, indicating that higher-ranked institutions tend to have lower tuition. Significant predictors include institutional control, rank, median income, and expenditure per student.

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
