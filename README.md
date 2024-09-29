# Tuition Prediction Project README

## Table of Contents
1. [Statement of Purpose](#statement-of-purpose)
2. [Abstract](#abstract)
3. [Methodology](#methodology)
   - [Data Collection](#data-collection)
   - [Data Wrangling](#data-wrangling)
   - [Variables](#variables)
   - [Statistical Modeling](#statistical-modeling)
   - [Regression Analysis](#regression-analysis)
   - [Exploration](#exploration)
4. [Results and Conclusions](#results-and-conclusions)
   - [Descriptive Statistics](#descriptive-statistics)
   - [Model Summary](#model-summary)
   - [Key Findings](#key-findings)
5. [Data](#data)
6. [Usage](#usage)
7. [Limitations and Future Research](#limitations-and-future-research)
8. [References](#references)

## Statement of Purpose
This paper isolates and uses key factors to predict tuition for public and private four-year universities across the United States within the same year. Institutional, quality of life, and crime rate metrics are observed to explain the differences between current university tuition rates. While much research has been conducted to explain time series data of tuition increases, research to explain the variation in tuition prices while holding time constant is scarce. Understanding these variations can provide insights into time series research and establish market value for colleges based on key predictors, helping students maximize their return on investment and minimize student loan debt.

## Abstract
This paper isolates and uses key factors to predict tuition for public and private four-year universities within the same year. A total of 60 observations from the top 400 US universities are analyzed using seven predictors in a linear model. The model accounts for over 85% of the variability in tuition rates, with the university's national ranking identified as the only significant institutional metric contributing to tuition cost.

## Methodology

### Data Collection
The data used for this model consists of 60 observations representing four-year universities in the US, sourced from three public datasets available on Kaggle. These datasets include metrics such as institutional characteristics, quality of life, and crime rates.

### Data Wrangling
In this step, the raw datasets were cleaned and prepared for analysis. Key processes included:
- **Handling Missing Values**: Any missing data points were addressed either by imputation or removal.
- **Standardizing Formats**: Ensured all variables were in consistent formats (e.g., numerical values for income).
- **Creating Categorical Variables**: Converted necessary variables into categorical formats for regression analysis.

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

### Regression Analysis
In this section, the linear regression model was fitted to the data, allowing us to evaluate the relationship between tuition and the predictors. Key steps included:
- **Model Fitting**: The model was fitted using ordinary least squares (OLS) regression.
- **Significance Testing**: Coefficients were evaluated for statistical significance to identify influential predictors.

### Exploration
Exploratory data analysis (EDA) was conducted to visualize and understand the data better. Techniques included:
- **Histograms and Boxplots**: Used to visualize distributions of key variables.
- **Correlation Analysis**: Examined relationships between predictors and the response variable (tuition).
- **Summary Statistics**: Generated to provide a quick overview of the data characteristics.

## Results and Conclusions

### Descriptive Statistics
The sample consists of 37 private universities and 23 public universities, with different rank distributions.

### Model Summary
The model results reveal that:
- Institutional rank, control, and median income were all significant at the 0.001 level.
- Diversity rank was significant at the 0.05 level, and unemployment at the 0.1 level.
- Among all predictors, rank is the most significant, by at least two orders of magnitude above all other predictors.

Overall, the model demonstrates substantial explanatory power for tuition, evidenced by an adjusted R-squared value of 0.87. This robustness is further supported by leave-one-out cross-validation (LOOCV), which yielded an R-squared value of 0.85, indicating minimal risk of overfitting. Thus, this model has strong potential for future applications with additional data.


### Key Findings
The analysis indicates that tuition increases as the university's rank improves, underscoring that prestige plays a significant role in tuition pricing. Interestingly, no other institutional metrics were statistically significant at the 0.1 level, highlighting that the market currently favors prestige over other factors.

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
