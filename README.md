---
title: "Regression Models Course Project"

date: "Thursday, June 18, 2015"
output: pdf_document
---


# Executive Summary

The objective of this exercise is to analyze a set of variables within the *mtcars* dataset in relationship to miles per gallon (MPG).  There are two questions to answer:

1.  Is an automatic or manual transmission better for MPG
2.  Quantify the MPG difference between automatic and manual transmissions

However, the analysis is to consider multiple models for greater impacts as well as check for residuals and diagnostics.  

# Exploratory Analysis
The dataset mtcars contains 32 readings across 11 variables.  The 11 variables reported in the mtcars dataset are:  mpg - Miles/(US) gallon; cyl - Number of cylinders; disp - Displacement (cu.in.);hp - Gross horsepower; drat - Rear axle ratio; wt - Weight (lb/1000); qsec - 1/4 mile time; vs - V/S; am - Transmission (0 = automatic, 1 = manual); gear - Number of forward gears; carb - Number of carburetors

```{r, echo = FALSE, fig.margin = TRUE,  fig.cap = "Automatic and Manual transmissions", fig.height= 1, fig.width= 1}
                 data(mtcars)
                 par(pin = c(1, 1))
                 plot(mpg ~ factor(am), data = mtcars, xlab = "Transmission")
 
```
The first question is an evaluation of which transmission type, either automatic(0) or manual(1) is better for mpg.  The boxplots show that the manual transmissions (am = 1) have the highest median MPG rating.  Therefore, manual transmissions on average have the better MPG.  

However, in looking at the simple linear model for the dataset, it is apparent that transmission type does not tell the entire story.  While the 95 percent confidence interval does not include zero, so we can reject the null hypothesis that there is no association between mpg and transmission type, the R-squared value is only 36% (.36) so 64 percent of the variation in mpg remains unexplained.  There are clearly factors other than transmission type which should help us understand the effect on mpg.
