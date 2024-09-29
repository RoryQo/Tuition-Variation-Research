# Tuition Variation Research

## Table of Contents
1. [Abstract](#abstract)
2. [Statement of Purpose](#statement-of-purpose)
3. [Variables](#variables)
4. [Inferential Statistics](#inferential-statistics)
5. [Results and Conclusion](#results-and-conclusion)
6. [Data Wrangling](#data-wrangling)
7. [Data Exploration](#data-exploration)
8. [Regression Analysis](#regression-analysis)
9. [Usage](#usage)

## Abstract
This project isolates and uses key factors to predict yearly out-of-state tuition for public and private four-year universities across the United States. Institutional, quality of life, and crime rate metrics are observed to explain the differences in current university tuition rates. The data consists of 60 observations representing four-year universities, selected from the top 400 in the US. Using seven predictors in a linear model, we predict tuition variability and employ leave-one-out cross-validation, achieving over 85% explanatory power.

## Statement of Purpose
Understanding tuition variations adds insight to time series research, which often focuses on averages. This model allows for an evaluation of a college's market value based on key predictors, enabling students to assess whether a college is over or underpriced. This can help maximize return on investment and minimize student loan debt.

## Variables
- **Institutional Control:** Categorical variable indicating public (0) or private (1) universities.
- **Rank:** Numeric rank from US News and World Report; lower numbers indicate higher prestige.
- **Number of Undergraduates:** Total undergraduate enrollment.
- **Unemployment:** City unemployment percentage (decimal).
- **Median Income:** Median income reported by the Economic Policy Institute (2022).
- **Diversity Rank (by Race):** Ranking based on city diversity; lower numbers indicate higher diversity.
- **Expend:** Expenditure per student.

## Inferential Statistics
The model reveals significant predictors at varying levels: institutional rank, control, and median income are significant at the 0.001 level, while diversity rank and unemployment are significant at the 0.05 and 0.1 levels, respectively. Rank is the most significant predictor, explaining 65% of tuition variability in a simple linear regression. Other common metrics, such as student-to-faculty ratios and graduation rates, proved statistically insignificant.

## Results and Conclusion
The analysis shows that tuition increases as school rank improves, affirming the notion that prestigious institutions can command higher tuition fees. When evaluating the University of Pittsburgh, the model predicts that in-state students pay below market value, while out-of-state students pay $9,000 above expected values, indicating a high return on investment for in-state students.

## Data Wrangling
Data is merged from various sources, including university rankings, city demographics, and crime rates, to create a comprehensive dataset for analysis. Key steps include:
- Loading necessary libraries and datasets.
- Merging datasets to create a single data frame, `obs_60_final`.
- Removing excess columns and renaming for clarity.

## Data Exploration
Exploratory data analysis includes:
- Filtering data for private and public schools.
- Creating histograms to visualize distributions of rank and tuition.
- Generating a correlation matrix to explore relationships between key predictors.

## Regression Analysis
Regression modeling focuses on identifying the relationship between tuition and various predictors:
- Initial models assess the impact of expenditure and rank on tuition.
- Full models incorporate multiple factors to predict tuition.
- Model selection employs stepwise regression to identify the best predictors, validated through Leave-One-Out Cross Validation.

## Usage
To utilize this analysis:
1. Load the required libraries.
2. Prepare the datasets by following the data wrangling steps.
3. Perform exploratory analysis to understand data distributions.
4. Fit regression models to predict tuition based on selected predictors.
5. Use the final model to assess specific universities' tuition against predicted values.

### Code Example
```r
# Load necessary libraries
library(dplyr)
library(caret)
library(readxl)

# Load the final dataset
obs_60_final <- read.csv('path/to/obs_60_final.csv')

# Fit the model
model <- lm(Tuition ~ Rank + Expend + ... , data = obs_60_final)
summary(model)
