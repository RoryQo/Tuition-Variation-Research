# Tuition Variation Research

### Table of Contents
1. [Abstract](#abstract)
2. [Statement of Purpose](#statement-of-purpose)
3. [Variables](#variables)
4. [Inferential Statistics](#inferential-statistics)
5. [Results and Conclusion](#results-and-conclusion)

### Abstract
This project isolates and analyzes key factors to predict yearly out-of-state tuition for public and private four-year universities across the United States (holding time constant). It examines institutional, quality of life, and crime rate metrics to explain the differences in tuition rates. The analysis is based on 60 observations, each representing a four-year university. This study utilizes seven predictors in a linear model to account for variability in tuition across universities and employs the leave-one-out cross-validation technique. The model accounts for over 85% of the variability in tuition rates, identifying the university's national ranking as the most significant metric affecting tuition costs.

### Statement of Purpose
Understanding the variations in tuition provides valuable insights into educational financing and market trends. This research establishes a market value for colleges based on key predictors, enabling prospective students to determine whether a college is overpriced or underpriced compared to its market value. Ultimately, this can help students maximize their return on investment and minimize student loan debt.

### Variables
- **Institutional Control**: A categorical variable indicating whether a university is public (coded as 0) or private (coded as 1).
- **Rank**: A numerical ranking assigned to each college by the US News and World Report; lower numbers indicate higher prestige.
- **Number of Undergraduates**: The total number of undergraduate students enrolled in the university as of 2020.
- **Unemployment**: The percentage of the city's population that is unemployed (expressed as a decimal).
- **Median Income**: The median income reported by the Economic Policy Institute (2022).
- **Diversity Rank**: A ranking of the city based on racial diversity; lower numbers indicate greater diversity.
- **Expend**: The amount of money spent per student by the university.

### Inferential Statistics
In the model summary, Institutional Rank, Institutional Control, and Median Income were significant at the .001 significance level. Diversity Rank was significant at the .05 level, and Unemployment was significant at the .1 level. Rank was the most significant predictor, by at least two orders of magnitude above all others. Overall, the model demonstrates substantial explanatory power regarding tuition, with an adjusted R-squared value of 0.87. This power is validated through leave-one-out cross-validation (LOOCV), where the model maintains a 0.85 R-squared value, indicating no severe overfitting issues and the potential for future usefulness with additional data.

### Results and Conclusion
These results show that we can explain most of the tuition variability while holding time constant. Tuition increases as the school rank improves. This expected relationship indicates that more desirable (prestigious) schools can leverage their status and charge a premium. Notably, Rank accounts for 65% of tuition variation. Other institutional metrics, such as student-to-faculty ratios and graduation rates, were not statistically significant predictors of tuition. This suggests that today's college students often pay for prestige rather than for schools that invest in their education.

Utilizing the model to evaluate the University of Pittsburgh, it appears that in-state tuition is priced below market value, while out-of-state tuition exceeds the expected value by $9,000. This analysis indicates that in-state students may experience a significantly higher return on investment compared to their out-of-state counterparts. Overall, this research highlights the critical role of university ranking in determining tuition costs and provides valuable insights for prospective students to make informed decisions about their educational investments.
