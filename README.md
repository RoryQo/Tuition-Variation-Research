# Tuition-Variation-Research
#### Abstract
  This project isolates and uses key factors to predict yearly out-of-state tuition for public and private four-year universities across the United States within the same year. Institutional, quality of life, and crime rate metrics will be observed and used to explain the differences between current university tuition rates.  The data used for this model consists of 60 observations, each representing a four-year university in the US. These 60 observations are a sample of the top 400 US universities.  This study uses seven predictors in a linear model to predict variability in tuition across universities and utilizes the leave one out cross-validation technique.  The model was able to account for over 85% of the variability of the tuition rates and found that the only significant institutional metric contributing to tuition cost was The university’s national ranking.

#### Statment of Purpose
  Understanding the variations of tuition can add insight to much of the time series research, as these studies are usually only aggregates of tuition averages. As well as establish a market value for a college given key predictors. With this model, you can determine if a college is over or underpriced compared to the market value, allowing you to maximize your return on investment and minimize your personal student loan debt.

#### Variables
+ `Institutional control` is a categorical variable that states whether a university is public or private. Public is coded as 0, and private is coded as 1.
+ `Rank` a number assigned to each college according to the US News and World Report; the lower the number, the "higher rank" or more prestigious the university.
+ `Number of undergraduates`, the number of undergraduates currently attending that university (2020)
+ `Unemployment`, the percentage of the city population unemployed (as decimal)
+ `Median income`, median income reported by the Economic Policy Institute (2022)
+ `Diversity Rank` (by race),  the ranking number of the city by diversity.  The more racially diverse the lower (numerically) the ranking number
+ `Expend`, the amount of money the school uses per student.

#### Inferential Statistics

In the model summary of each predictor discussed above,  Institutional rank, Institutional control, and Median income were all significant at above the .001 significance level. Diversity rank was significant at the .05, and unemployment was significant at the .1 level.  Of all predictors, rank is the most significant, by at least two orders of magnitude above all other predictors. Overall the model has a large explanatory power of tuition,  with an adjusted R squared value of 0.87.  This explanatory power is further validated by the cross validation (LOOCV).  After validation the model still performed with a 0.85 R squared value, indicating there aren't any severe overfitting problems, and could be a useful model in the future with more data.  Table 3 displays the results of the cross validation.

#### Results
  These results show that we can explain most of the tuition variability while holding time constant. Tuition increases as the school rank gets better (lower in number). This relationship is expected because more desirable (prestigious) schools can leverage this and charge their students a premium. What's impressive is the significance of this relationship. In a simple linear regression, Rank accounts for 65% of tuition variation.
	Variables in this model that were insignificant tell us just as much about the higher education market as the ones that were. Besides Rank, no other institution metrics were statistically significant at the 0.1 confidence level (excluding the private vs. public control). Student-to-faculty ratios, graduation rate, or percentage of alumni donating to the university were irrelevant to predicting tuition despite these metrics being widely touted and used in recruitment brochures and websites. Today's college students pay for Prestige rather than a school that invests in them.  Testing whether I am paying too much for college, I imputed data according to the University of Pittsburgh and used the model to predict tuition based on these metrics.  It revealed that for in-state students, Pitt was priced below market value; however, for out-of-state students, it is $9,000 above the expected value.  As an instate student, it appears I am getting a high ROI compared to out of state students on my education investment.

#### Data Cited
+ Vaughan, Zach. (2016 &; January). City/Zip/County/FIPS- Quality of Life (US). Retrieved
2/21/2024 from City/ZIP/County/FIPS - Quality of Life (US) (kaggle.com).
+ Gupta, Yash. (2020 &; Month of dataset creation). US College Data. Retrieved 2/21/2024 from
https://www.kaggle.com/datasets/yashgpt/us-college-data/dataData (kaggle.com).

 
