---
title: "Statistical Skills"
author: "Samantha Richins"
date: "2022-05-29"
output: 
  html_document:
    keep_md: TRUE
---






# Data

mtcars in base R

---


## T Test

It is assumed that the miles per gallon (mpg) that cars attain is normally distributed. The null hypothesis states that mu equals zero. This is assumed to be true unless proven otherwise. The alternative hypothesis is accepted under the condition that the null hypothesis is rejected.

$$
  H_0: \mu = 0
$$
$$
  H_a: \mu \neq 0
$$

$$
 \alpha = 0.05
$$



```r
t.test(mtcars$mpg, mu = 0, alternative = "two.sided", conf.level = 0.95) %>% 
  pander::pander()
```


----------------------------------------------------------------------------
 Test statistic   df       P value       Alternative hypothesis   mean of x 
---------------- ---- ----------------- ------------------------ -----------
     18.86        31   1.526e-18 * * *         two.sided            20.09   
----------------------------------------------------------------------------

Table: One Sample t-test: `mtcars$mpg`

The level of significance was established at 0.05 prior to running the statistical test. The P-Value returned is **1.526e-18** which is below our level of significance so we will accept the null hypothesis.


```r
qqPlot(mtcars$mpg)
```

![](stats_skills_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

```
## [1] 20 18
```

The correlation in the graphic above demonstrates that the data is normally distributed. 

Based on the results of the t-test and QQ-plot, we can assume that the miles per gallon (mpg) data collection is normally distributed. 


