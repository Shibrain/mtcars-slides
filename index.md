---
title       : Mtcars App
subtitle    : mtcars shiny application
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---libray(shiny)

## Variables used for the model

1. Hourse Power
2. Wiegth
3. Transmission Type

--- .class #id 

## Preparation Code


```r
mcars <- read.csv(file = "../mtcars.csv")
mcars[mcars$am == 0, c("tm")] <- gsub("0", "automatic", mcars[mcars$am == 0, 
    c("am")])
mcars[mcars$am == 1, c("tm")] <- gsub("1", "manual", mcars[mcars$am == 1, c("am")])
mcars$tm <- as.factor(mcars$tm)
carsfit <- lm(mpg ~ tm + wt + hp - 1, data = mcars)
```



---

## Model Summary
  

```r
summary(carsfit)
```

```
## 
## Call:
## lm(formula = mpg ~ tm + wt + hp - 1, data = mcars)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -3.422 -1.792 -0.379  1.225  5.532 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## tmautomatic 34.00288    2.64266   12.87  2.8e-13 ***
## tmmanual    36.08659    1.73634   20.78  < 2e-16 ***
## wt          -2.87858    0.90497   -3.18  0.00357 ** 
## hp          -0.03748    0.00961   -3.90  0.00055 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 2.54 on 28 degrees of freedom
## Multiple R-squared: 0.987,	Adjusted R-squared: 0.985 
## F-statistic:  538 on 4 and 28 DF,  p-value: <2e-16
```

  
  
---

## Thank You



---


## Thank You
