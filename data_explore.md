---
title: "Final Project"
authors: "Daniel Beidelschies, Kai Akimoto, Tim Minot"
output: 
  html_document:
      keep_md: yes
---




The draft should include the following:

## Research Question 

+ For our project we will be utilizing the NHANES data set as well as the health_coverage data set. The NHANES data set contains verious health related information that help to shed light on the quality of life that an individual has. We aim to use this data to investigate how certain socioeconomic factors play role in quality of health.

## Data 

### NHANES

+ BPSysAve 
+ Poverty 
+ Race3 
+ PhysActivity 
+ Smoke 100 
+ Diabetes

### Graphs 


### Blood Pressure according to Race
![](data_explore_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

+ Shows average systolic blood pressure based on Race

### Change in average poverty levels accross different races based on incidence of Diabetes
![](data_explore_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

+ This shows the relationship between poverty and diabetes for different races


### Change in poverty based on Race as it is affected by Diabetes
![](data_explore_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

+ Relationship between poverty and diabetes for different races

### Relationship between Blood Pressure and Poverty and Physical Activity
![](data_explore_files/figure-html/unnamed-chunk-5-1.png)<!-- -->




### How smoking affects blood pressure in different Races

```
## Warning: Removed 1449 rows containing non-finite values (stat_boxplot).
```

![](data_explore_files/figure-html/unnamed-chunk-6-1.png)<!-- -->
+ All races are affected fairly the same, except for Mexicans

## Models
+ lm_health

```
## # A tibble: 6 x 5
##   term          estimate std.error statistic  p.value
##   <chr>            <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)    116.         1.11   104.    0       
## 2 Race3Black       4.94       1.36     3.63  0.000286
## 3 Race3Hispanic    0.549      1.53     0.359 0.719   
## 4 Race3Mexican    -2.05       1.42    -1.45  0.148   
## 5 Race3White       3.24       1.16     2.80  0.00517 
## 6 Race3Other       1.82       1.92     0.949 0.343
```
+ significant relationship between only some races and health

### lm_Poverty

```
## # A tibble: 2 x 5
##   term        estimate std.error statistic p.value
##   <chr>          <dbl>     <dbl>     <dbl>   <dbl>
## 1 (Intercept) 118.         0.383   308.      0    
## 2 Poverty       0.0183     0.115     0.159   0.874
```
+ poverty is not related with health

### lm.physical

```
## # A tibble: 2 x 5
##   term          estimate std.error statistic  p.value
##   <chr>            <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)     122.       0.284     428.  0.      
## 2 PhysActiveYes    -4.17     0.380     -11.0 7.58e-28
```

### lm.pov.act

```
## # A tibble: 3 x 5
##   term          estimate std.error statistic  p.value
##   <chr>            <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)   121.         0.421   288.    0.      
## 2 PhysActiveYes  -4.18       0.398   -10.5   1.33e-25
## 3 Poverty         0.0626     0.118     0.529 5.97e- 1
```

### lm.race.act

```
## # A tibble: 12 x 5
##    term                        estimate std.error statistic p.value
##    <chr>                          <dbl>     <dbl>     <dbl>   <dbl>
##  1 (Intercept)                 120.          1.77   67.9    0      
##  2 PhysActiveYes                -5.40        2.26   -2.39   0.0170 
##  3 Race3Black                    4.23        2.10    2.02   0.0437 
##  4 Race3Hispanic                -0.0568      2.29   -0.0247 0.980  
##  5 Race3Mexican                 -2.41        2.18   -1.11   0.269  
##  6 Race3White                    4.18        1.84    2.27   0.0230 
##  7 Race3Other                   -2.44        3.14   -0.776  0.438  
##  8 PhysActiveYes:Race3Black      2.47        2.76    0.893  0.372  
##  9 PhysActiveYes:Race3Hispanic   1.45        3.09    0.469  0.639  
## 10 PhysActiveYes:Race3Mexican    2.32        2.91    0.797  0.426  
## 11 PhysActiveYes:Race3White     -0.703       2.36   -0.298  0.766  
## 12 PhysActiveYes:Race3Other     10.5         4.02    2.61   0.00920
```



### lm.race.pov1

```
## # A tibble: 7 x 5
##   term          estimate std.error statistic   p.value
##   <chr>            <dbl>     <dbl>     <dbl>     <dbl>
## 1 (Intercept)     3.09      0.102     30.3   1.01e-183
## 2 Race3Black     -1.03      0.124     -8.32  1.14e- 16
## 3 Race3Hispanic  -1.11      0.136     -8.17  4.11e- 16
## 4 Race3Mexican   -1.30      0.129    -10.1   8.29e- 24
## 5 Race3White      0.0486    0.106      0.458 6.47e-  1
## 6 Race3Other     -0.708     0.168     -4.22  2.47e-  5
## 7 DiabetesYes    -0.217     0.0894    -2.43  1.53e-  2
```

### lm.race.pov2

```
## # A tibble: 12 x 5
##    term                      estimate std.error statistic   p.value
##    <chr>                        <dbl>     <dbl>     <dbl>     <dbl>
##  1 (Intercept)                 3.12       0.106    29.3   1.98e-173
##  2 Race3Black                 -1.09       0.130    -8.37  7.28e- 17
##  3 Race3Hispanic              -1.13       0.141    -7.99  1.76e- 15
##  4 Race3Mexican               -1.34       0.134   -10.0   2.44e- 23
##  5 Race3White                  0.0281     0.111     0.254 8.00e-  1
##  6 Race3Other                 -0.831      0.175    -4.75  2.05e-  6
##  7 DiabetesYes                -0.551      0.366    -1.50  1.32e-  1
##  8 Race3Black:DiabetesYes      0.603      0.430     1.40  1.61e-  1
##  9 Race3Hispanic:DiabetesYes   0.225      0.505     0.445 6.56e-  1
## 10 Race3Mexican:DiabetesYes    0.480      0.489     0.980 3.27e-  1
## 11 Race3White:DiabetesYes      0.227      0.383     0.591 5.54e-  1
## 12 Race3Other:DiabetesYes      1.58       0.622     2.53  1.13e-  2
```

### lm.diabetes

```
## # A tibble: 3 x 5
##   term          estimate std.error statistic  p.value
##   <chr>            <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)     120.       0.294    411.   0.      
## 2 DiabetesYes       8.89     0.648     13.7  2.37e-42
## 3 PhysActiveYes    -3.56     0.378     -9.41 6.66e-21
```

### lm.diabetes.active

```
## # A tibble: 4 x 5
##   term                       estimate std.error statistic  p.value
##   <chr>                         <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)               120.          0.301 400.      0.      
## 2 DiabetesYes                 8.89        0.835  10.6     2.82e-26
## 3 PhysActiveYes              -3.55        0.396  -8.97    3.57e-19
## 4 DiabetesYes:PhysActiveYes  -0.00528     1.32   -0.00399 9.97e- 1
```









## Inferences


+ H0 = 0 There is no relationship between race and blood pressure
+ HA ≠ 0 There is a relationship between race and blood pressure

### lm.race.pov.bp

```
## # A tibble: 12 x 5
##    term                  estimate std.error statistic p.value
##    <chr>                    <dbl>     <dbl>     <dbl>   <dbl>
##  1 (Intercept)           118.         2.41    48.8     0     
##  2 Race3Black             -0.290      2.78    -0.104   0.917 
##  3 Race3Hispanic          -1.12       3.01    -0.371   0.710 
##  4 Race3Mexican           -4.76       2.86    -1.67    0.0954
##  5 Race3White              3.48       2.52     1.38    0.167 
##  6 Race3Other              3.41       3.80     0.899   0.369 
##  7 Poverty                -0.527      0.681   -0.774   0.439 
##  8 Race3Black:Poverty      1.95       0.850    2.29    0.0219
##  9 Race3Hispanic:Poverty   0.638      0.989    0.645   0.519 
## 10 Race3Mexican:Poverty    1.06       0.936    1.14    0.256 
## 11 Race3White:Poverty     -0.0505     0.710   -0.0711  0.943 
## 12 Race3Other:Poverty     -1.04       1.19    -0.873   0.383
```
+ Relationship between only some races and blood pressure, there is only a relationship the interactions of black individuals and poverty on blood pressure


+ The number below represents the confidence interval for the intercept of BPSysAve when Age and Poverty are fully interacting.

```
## [1] 0.5653686
```

```
## # A tibble: 1 x 1
##      SE
##   <dbl>
## 1 0.565
```

```
## # A tibble: 1 x 2
##   lower upper
##   <dbl> <dbl>
## 1  117.  119.
```

```
## [1] 116.9043 119.1658
```


```r
lm.bp.race<- lm(BPSysAve~Race3,data=NHANES)

tidy(lm.bp.race)
```

```
## # A tibble: 6 x 5
##   term          estimate std.error statistic  p.value
##   <chr>            <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)    116.         1.11   104.    0       
## 2 Race3Black       4.94       1.36     3.63  0.000286
## 3 Race3Hispanic    0.549      1.53     0.359 0.719   
## 4 Race3Mexican    -2.05       1.42    -1.45  0.148   
## 5 Race3White       3.24       1.16     2.80  0.00517 
## 6 Race3Other       1.82       1.92     0.949 0.343
```




```
## # A tibble: 7 x 2
##   Race3        n
##   <fct>    <int>
## 1 Asian      288
## 2 Black      589
## 3 Hispanic   350
## 4 Mexican    480
## 5 White     3135
## 6 Other      158
## 7 <NA>      5000
```



