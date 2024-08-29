# Tuition-Variation-Research
#### Abstract
  This paper isolates and uses key factors to predict tuition for public and private four-year universities across the United States within the same year. Institutional, quality of life, and crime rate metrics will be observed and used to explain the differences between current university tuition rates.  The data used for this model consists of 60 observations, each representing a four-year university in the US. These 60 observations are a sample of the top 400 US universities.  This study uses seven predictors in a linear model to predict variability in tuition across universities and utilizes the leave one out cross validation technique.  The model was able to account for over 85% of the variability of the tuition rates, and found that the only significant institutional metrics contributing to tuition cost was The university’s national ranking.

#### Statment of Purpose
  Understanding the variations of tuition can add insight to much of the time series research, as these studies are usually only aggregates of tuition averages. As well as establish a market value for a college given key predictors. With this model, you can determine if a college is over or underpriced compared to the market value, allowing you to maximize your return on investment and minimize your personal student loan debt.

#### Variables
+ ***Institutional control*** is a categorical variable that states whether a university is public or private. Public is coded as 0, and private is coded as 1.
+ ***Rank*** a number assigned to each college according to the US News and World Report; the lower the number, the "higher rank" or more prestigious the university.
+ ***Number of undergraduates***, the number of undergraduates currently attending that university (2020)
+ ***Unemployment***, the percentage of the city population unemployed
+ ***Median income***, median income reported by the Economic Policy Institute (2022)
+ ***Diversity Rank*** (by race),  the ranking number of the city by diversity.  The more racially diverse the lower (numerically) the ranking number
+ ***Expend***, the amount of money the school uses per student.

#### Results
  These results show that we can explain most of the tuition variability while holding time constant. Tuition increases as the school rank gets better (lower in number). This relationship is expected because more desirable (prestigious) schools can leverage this and charge their students a premium. What's impressive is the significance of this relationship. In a simple linear regression, Rank accounts for 65% of tuition variation.
	Variables in this model that were insignificant tell us just as much about the higher education market as the ones that were. Besides Rank, no other institution metrics were statistically significant at the 0.1 confidence level (excluding the private vs. public control). Student-to-faculty ratios, graduation rate, or percentage of alumni donating to the university were irrelevant to predicting tuition despite these metrics being widely touted and used in recruitment brochures and websites. Today's college students pay for Prestige rather than a school that invests in them.
