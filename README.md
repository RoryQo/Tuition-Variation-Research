# Tuition Variation Research

### Table of Contents
1. [Abstract](#abstract)
2. [Statement of Purpose](#statement-of-purpose)
3. [Variables](#variables)
4. [Inferential Statistics](#inferential-statistics)
5. [Results and Conclusion](#results-and-conclusion)

### Abstract
This project isolates and analyzes key factors to predict yearly out-of-state tuition for public and private four-year universities across the United States. It examines institutional, quality of life, and crime rate metrics to explain the differences in tuition rates. The analysis is based on 60 observations, each representing a four-year university. This study utilizes seven predictors in a linear model to account for variability in tuition across universities and employs the leave-one-out cross-validation technique. The model accounts for over 85% of the variability in tuition rates, identifying the university's national ranking as the only significant institutional metric affecting tuition costs.

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
The model summary reveals that Institutional Rank, Institutional Control, and Median Income are significant predictors at the .001 significance level. Diversity Rank is significant at the .05 level, while Unemployment is significant at the .1 level. Among all predictors, Rank is the most significant, contributing to a substantial explanatory power with an adjusted R-squared value of 0.87. This robustness is further validated through cross-validation, where the model retains an R-squared value of 0.85, indicating minimal overfitting and potential for future applications with additional data.

### Results and Conclusion
The findings demonstrate that tuition variability can be largely explained while controlling for time. Tuition tends to increase as the university rank improves, which aligns with the expectation that more prestigious institutions can charge higher fees. Interestingly, beyond Rank, no other institutional metrics, such as student-to-faculty ratios or graduation rates, significantly predict tuition costs, suggesting that students are primarily paying for prestige rather than institutional support or investment.

Utilizing the model to evaluate the University of Pittsburgh, it appears that in-state tuition is priced below market value, while out-of-state tuition exceeds the expected value by $9,000. This analysis indicates that in-state students may experience a significantly higher return on investment compared to their out-of-state counterparts. Overall, this research highlights the critical role of university ranking in determining tuition costs and provides valuable insights for prospective students to make informed decisions about their educational investments.
