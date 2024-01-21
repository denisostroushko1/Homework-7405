# Homework-7405

Homework for Fall 2022 PUBH 7405 at the University of Minnesota. I found a lot of cool ways to present tables with summary statistics, as well as test and models output. I also 
found a lot of useful packages that interact with `ggplot` mainly. 

Also, textbook and lecture materials cover way more intro-level regression methods and theory, and I wish to use this file as a table of  contents. 

By default, I use `kable`, `kableExtra`, `tidyverse`, and `ggplot2` a lot, so I will only be making notes of new packages 
I find and use for the analysis. 

# HW1

* Statistical Concepts: 

  + two-sample t-test, two-sample Wilcoxon test for difference in medians
  + test of independence for two continuous variables using Pearson's and Spearman's Rho correlation coefficients 
  + z-transformation for correlation coefficient confidence interval 
  
* Implementation via R code
  + pooled standard error calculation for the two-sample difference in means  
  + transformation to and from z-scale for Pearson's correlation coefficient confidence interval 

# HW2

* Statistical Concepts: 
  + Simple Linear Regression 
  + Prediction of average response level $\large \hat{Y_h}$, estimation of standard error for the estimate
  + Prediction of a response $\large \hat{Y_h}$ for a single observation, estimation of standard error for the estimate
  + Overall ANOVA test for the regression model 
  + Calculation of $F^*$ cutoff statistic and p-value using degrees of freedom for the overall ANOVA test and 
  
* Implementation via R code: 
  + Calculation of SLR model estimates $\large \hat{\beta_i}$ using formulas
  + Average response and a single observation estimate, standard error, and C.I. for a given value of X

# HW3

* Statistical Concepts: 
  + Weighted average slope from univariate regression models for the two treatment groups. Estimation of standard error for the 
    weighted average slope. 
  + G-statistic and $\large \chi^2$ to test if the change in predictor is different between the two treatment groups. 
  + Relative Potency of a drug: a way to compare response to a drug between controls and treated
  + Diagnostic plots for residuals from Gaussian Regression (Or Normal Error Regression Model = NERM) with identity link 
  + Brown-Forsythe test to evaluate constancy of residual variance 
  + Obtaining corresponding theoretical quantiles for observed values of residuals for the QQplot diagnostic. 
  
* Implementation via R code: 
  + calculation of corresponding theoretical quantiles for observed values of residuals for the QQplot diagnostic. Implementation of the formula
  + Brown-Forsythe test implementation using pooled variance of residual groups and a t-test. 

# HW4 

* Statistical Concepts: 
  + Multivariate Gaussian Regression Model: test if all predictors have slope 0 using an F-test 
  + A small dive into matrix version of OLS equations.  
  
* Implementation via R code: 
  + Calculation of F-statistics and test p-value from the residual sum of squares using base R code 
  + Calculation of $\textbf{X}$ and $\textbf{Y}$ design matrices for the OLS model, small examples of matrix multiplication 
    for $\large \hat{\beta}$ estimates

# HW5 

* Statistical Concepts: 
  + Testing Gaussian GLM with identify link for a lack of fit using an F-test (ANOVA)
  + Parallel line Analysis for the response to dose of drug between two treatment groups/arms 
  + Relative potency, standard error estimation using an established formula 
    - Derivation of the variance formula is not provided 
  + Decomposition of SSR (Regression Sum of Squares) in order of variable addition to the model 
    - decomposition explains how much additional variance of the response we can explain by adding a given predictor to the model 
  + F-test for testing significance of a group of predictors after accounting for other predictors 'already-in-the-model'
  
* Implementation via R code: 
  + coding fo the relative potency variance estimator using base R variance/covariance functions 
  + coding of SSR decomposition using base functions in R and base `lm` models
  
# HW6 

* Statistical Concepts: 
  + Interpretation of the quadratic regression term coefficient, in terms of how the coefficient affects parabola shape 
  + Visualization of higher order model terms 
  + Step wise regression building and evaluation of candidate models using AIC and Adjusted R-square metrics. Other metrics are 
    available in the mentioned package. 
  + Multiple comparison adjustments via Bonferroni, Hochberg, Holm adjustments. 
    - specific needs and appropriate use of these adjustments for false discovery and other rates, as well as Tukey adjustment,  are covered in the following course [PUBH 7406 Spring 2023](https://github.com/denisostroushko1/Homework-7406) in [HW1](https://github.com/denisostroushko1/Homework-7406/tree/main/HW1)
  
* Implementation via R code: 
  + `ggpredict`: obtain fitted values from a linear regression model for a given model terms. Results are stored in a data frame 
    for a ggplot 
  + Multiple comparison adjustments are written using iterative loops using base R code. 
    - packages to obtain adjusted p-values are available, which I did not bother to check at that time. 
  
* Packages: 
  + `ggeffects`: a ggplot-compatible package to obtain marginal effect plots for given predictor using a given `lm` or `glm` model
  + `olsrr`: a nice step wise regression algorithm using `ols_step_best_subset()` function 
  
# HW7

* Statistical Concepts: 
  + Added variable plot for regression diagnostics. Evaluating relationships between a given predictor and a response after accounting for other variables. 
    - Looking for linear fit of residuals from a full model and a reduced model. 
    - Full model = all predictors, reduced model = all predictors minus a predictor of interest 
    - Non-linear smoothed patterns suggest that a non-linear, higher order, or other transformations are needed. 
    - Also looking for a constant variance of data points around the fitted and smooth lines on the ggplot 
  + Variance Inflation Factors (VIF) to evaluate collinearity of predictors 
  + Plots of residuals against predictors 
    - looking for no linear or other relationships, indicating that residuals are distributed the same at all levels of predictors   
    
* Implementation via R code: 
  + added variable plots are obtained by fitting `lm` model, getting residuals, and passing them into a ggplot 
  + VIF implemented using base R `lm` functions and r-squared values 
  
# HW8

* Statistical Concepts: 
  + Treatment crossover study design and appropriate statistical models. 
  + Estimation of coefficients from the data and statistical inference using a t-test. 
    - Ideally, will need to use an F-test or a bootstrap method to assess variance equality assumption first. 
  + First look at concepts in Causal Inference. Assessing covariates balance using log-odds of propensity score and a t-test 
  
* Implementation via R code: 
  + Logistic regression fit using base R glm 
  + Obtaining propensity scores for each person, calculating log odds as a function of propensity scores
  + Comparing means of log odds using a t-test 
    - can use any other robust or non-parametric test
  
  
# HW10

* Statistical Concepts: 
  + First look at survival analysis concepts. 
