Distance Prediction
========================================================
author: Kevin
date: Jan 20, 2015

App Summary
========================================================

- The Shiny App is used to predict the braking distance based on speed.
- The prediction is based on a linear model constructed from cars data.
- The App could take an speed input and a confidence level input.
- The App outputs the prediction and the associate confidence interval.

Cars Data Preview
========================================================


```
     speed           dist    
 Min.   : 4.0   Min.   :  2  
 1st Qu.:12.0   1st Qu.: 26  
 Median :15.0   Median : 36  
 Mean   :15.4   Mean   : 43  
 3rd Qu.:19.0   3rd Qu.: 56  
 Max.   :25.0   Max.   :120  
```
Regression Line
========================================================

![plot of chunk unnamed-chunk-2](Rpres-figure/unnamed-chunk-2.png) 

Shiny App Details
========================================================

- The input speed default value is 16, and range is 4 - 25.
- The input confidence level input default value is 0.95 and range is 0.80 - 0.99
- The results could be calculated using the following code:


```r
x <- data.frame(speed=16)
predict(lm(dist~speed, data=cars), newdata=x, interval='confidence', level = 0.95)
```

```
    fit   lwr   upr
1 45.34 40.94 49.74
```
