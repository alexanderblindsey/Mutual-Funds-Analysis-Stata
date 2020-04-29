# Mutual Funds Analysis

### The Project
This project was submitted as an assignment for an upper-level econometrics class at the University of British Columbia. The assignment received an A+.

In this project, I analyze the causal effect of portfolio manager's education, age, and tenure on the performance of their funds. Data was collected from over 2000 managers who responded to a survey. A manager's education is measured by their SAT score and if they have an MBA or not, a dummy variable with value = 1 if True and =0 if False. Tenure refers to the number of years in the position. Fund returns are measured by fund's risk-adjusted excess returns at a specific date.

### The Data
The data used in this project was lost as initially I did not have the intention of making it public. A printout of the Stata log file containing all the code is included at the end of the report. The raw log file has also been lost.  

### Findings

My primary multiple linear regression model is return=BETA0+BETAmba+BETAsat+BETAtenure+BETAage+u.

The constant B0 measures expected return when the value of all other variables is 0. This is irrelevant in our data as it is impossible to have 0 age and 0 sat.

SAT scores, sat, were found to have a coefficient, or BETA, of ~0.005, meaning that a one unit *ceteris parabus* increase in SAT scores would increase returns by ~0.005 units. The p-value is ~0.00 meaning we reject the null hypothesis that BETAsat=0 at any standard significance level used in the social sciences, typically 0.10, 0.05, and 0.01. The ln of SAT, lnsat, was found to have a coefficient of ~5.84 and a p-value of 0.00, again siginifant at any significance level. This means a 1% increase in SAT scores increases returns by 0.0584 units.

Having an MBA was found to have a coefficient of ~0.674, meaning that having an MBA vs. not having an MBA increased returns by .674 units. The p-value was found to be 0.073, meaning that we fail to reject the null hypothesis that BETAmba=0 at the 5% significance level. 

Age was found to have a coefficient of aprox. -0.1405, indicating a negative relationship between age and returns, which is unexpected as one would expect age and experience are correlated. With a p-value of 0.001, we reject the null hypothesis that BETAage=0 at the 5% significance level. 

Tenure was found to have a coefficient of ~0.082, indicating that a one unit increase in tenure would increase average returns by 0.082. With a very high p-value of .641, we fail to reject the null hypothesis that BETAtenure=0 at a 5% significance level as .641 > 0.05.   

The insignificance of tenure and the negative value of BETAage possibly suggest that a better variable measuring 'experience' is required, so I drop these variables from the model. Both models were then assesed with an F-test and by comparing the R-squared to see the effect of dropping these variables. I then explore the validity of both models by testing the data against the six Gauss-Markov assumptions.


