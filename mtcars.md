MtCars
========================================================



```r
library(caret)
```

```
## Loading required package: lattice
## Loading required package: ggplot2
```

```
## Warning: couldn't connect to display ":0"
```

```r
require(stats)
require(graphics)
auto <- subset(mtcars, am == 0)
manual <- subset(mtcars, am == 1)
autofit <- lm(mpg ~ ., data = auto)
manualfit <- lm(mpg ~., data= manual)
summary(autofit)
```

```
## 
## Call:
## lm(formula = mpg ~ ., data = auto)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -2.035 -1.049  0.384  0.696  2.240 
## 
## Coefficients: (1 not defined because of singularities)
##             Estimate Std. Error t value Pr(>|t|)  
## (Intercept)   8.6435    21.5112    0.40    0.697  
## cyl          -0.5339     1.1274   -0.47    0.647  
## disp         -0.0203     0.0174   -1.16    0.275  
## hp            0.0622     0.0461    1.35    0.210  
## drat          0.5916     3.0119    0.20    0.849  
## wt            1.9541     2.2313    0.88    0.404  
## qsec         -0.8843     0.7584   -1.17    0.274  
## vs            0.7389     2.5119    0.29    0.775  
## am                NA         NA      NA       NA  
## gear          8.6542     3.8956    2.22    0.053 .
## carb         -4.8105     1.9004   -2.53    0.032 *
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 1.8 on 9 degrees of freedom
## Multiple R-squared:  0.889,	Adjusted R-squared:  0.779 
## F-statistic: 8.03 on 9 and 9 DF,  p-value: 0.00238
```

```r
summary(manualfit)
```

```
## 
## Call:
## lm(formula = mpg ~ ., data = manual)
## 
## Residuals:
##      Mazda RX4  Mazda RX4 Wag     Datsun 710       Fiat 128    Honda Civic 
##         1.0709        -0.7741        -0.7553         2.6959         0.0313 
## Toyota Corolla      Fiat X1-9  Porsche 914-2   Lotus Europa Ford Pantera L 
##        -1.2328        -0.6375         0.2716         0.2968        -0.3018 
##   Ferrari Dino  Maserati Bora     Volvo 142E 
##        -0.8400         0.5734        -0.3984 
## 
## Coefficients: (1 not defined because of singularities)
##             Estimate Std. Error t value Pr(>|t|)
## (Intercept) -137.907     69.149   -1.99     0.14
## cyl           -1.281      4.537   -0.28     0.80
## disp           0.180      0.176    1.02     0.38
## hp            -0.160      0.143   -1.12     0.34
## drat          -4.950      5.468   -0.91     0.43
## wt           -10.542      4.996   -2.11     0.13
## qsec           8.095      3.451    2.35     0.10
## vs             0.943      5.089    0.19     0.86
## am                NA         NA      NA       NA
## gear          12.328      6.660    1.85     0.16
## carb           4.689      4.065    1.15     0.33
## 
## Residual standard error: 2.08 on 3 degrees of freedom
## Multiple R-squared:  0.972,	Adjusted R-squared:  0.886 
## F-statistic: 11.4 on 9 and 3 DF,  p-value: 0.035
```

Residual plots


```r
plot(resid(autofit))
abline(0, 0)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-21.png) 

```r
plot(resid(manualfit))
abline(0, 0)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-22.png) 

