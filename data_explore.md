---
title: "Group check in 2"
authors: "Daniel Beidelschies, Kai Akimoto, Tim Minot"
output: 
  html_document:
      keep_md: yes
---




The draft should include the following:

## Describe the data and your research question. Where does it come from? How was it collected? What do you hope to learn?

+ For our project we will be utilizing the NHANES data set as well as the health_coverage data set. The NHANES data set contains verious health related information that help to shed light on the quality of life that an individual has. We aim to use this data to investigate how certain socioeconomic factors play role in quality of health.

## 2-4 graphs with explanations about what the graphs show. 

![](data_explore_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

+ This graph shows the relationship between Systolic Blood pressure of older individuals with Diabetes. As you can see, as individuals get older, they are more likely to have incidence of diabetes as well as a higher blood pressure.

![](data_explore_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

+ This shows how people of different races are affected by diabetes based on their level of poverty. The lower the y value, the more poverty that the race has on average. 

## At least 2 models. Explain why you chose to fit these models and interpret the coefficients of the model. What do they mean in the context of your research question? 

```
## # A tibble: 7 x 5
##   term          estimate std.error statistic   p.value
##   <chr>            <dbl>     <dbl>     <dbl>     <dbl>
## 1 (Intercept)     98.0      1.04       93.9  0.       
## 2 Age              0.457    0.0112     40.7  6.66e-306
## 3 Race3Black       5.51     1.16        4.77 1.94e-  6
## 4 Race3Hispanic    1.55     1.30        1.20 2.32e-  1
## 5 Race3Mexican     1.72     1.21        1.42 1.56e-  1
## 6 Race3White       1.46     0.985       1.48 1.40e-  1
## 7 Race3Other       4.07     1.63        2.49 1.27e-  2
```

+ This partial interaction model helps to show how Race and Age interact to affect Systolic Blood Pressure because it helps to shed light on how certain races are more likely to experience an increase in blood pressure (which associated with poorer health). 

+ The intercept represents Asian individuals at the age of 0. The Age coefficient represents the average unit of increase for bloodpressure as individuals get older. As you can see, there is an extremely high p-value, supporting the strong relationship between age and bloodpressure increase. 

+ Race3Hispanic, Race3Mexican, Race3White, coefficients represent the increase of blood pressure for individuals that are Hispanic, Mexican, or White respectively. These coefficients are not dependent on Age and these estimates are purely the average unit of increase for these races. As you can see, the p-value for individuals of these races are very high, meaning that there the liklihood of the Blood pRessure Increase for these indviduals is not likley to be due to their race. 

+ Race3Black coefficient represents the avaerage unit of increase for blood pressure of inidividuals that are Black. As you can see that black individuals have a significantly higher increase of blood pressure, "+5.51", than other races. Furthermore, the p-value of this coefficient is significantly lower, outlining a very strong relationship between an indidual being black and their systolic blood pressure increase. 


```
## # A tibble: 4 x 5
##   term        estimate std.error statistic   p.value
##   <chr>          <dbl>     <dbl>     <dbl>     <dbl>
## 1 (Intercept)  99.1      0.690      144.   0.       
## 2 Age           0.524    0.0161      32.5  6.01e-218
## 3 Poverty       0.354    0.225        1.57 1.16e-  1
## 4 Age:Poverty  -0.0283   0.00503     -5.62 1.97e-  8
```
+ This full interaction model shows how both Age and Poverty interact with each other to affect systolic blood pressure. The data shows how people of higher economic status will have a lower blood pressure on average than those of a lower economic status. 
+ Intercept coefficient represents the average systolic blood pressure when both the age and poverty level is 0.
+ As we've established in previous models and graphs, Age and systolic blood pressure increase are very strongly related. As the p value for the age coefficient is quite miniscule showing a strong relationship
+ The poverty coefficient is the average unit increase depending on the categorical numerical value of poverty. In this integer-based numerical category, 1 is indicative of most poverty stricken and 5 is least poverty stricken. 
+ The Age:Poverty coefficient is the average unit of change of Systolic blood pressure for aging individuals depending on their poverty level. Since the estimate is negative, we can determine that as individuals get older, the less poverty stricken they are (i.e. 5), the more their blood pressure will decrease.


## Make some inferences, using either hypothesis testing or confidence intervals. What did you learn?

+ The number below represents the confidence interval for the intercept of BPSysAve when Age and Poverty are fully interacting.

```
## [1] 0.5653686
```

+ Based on the analysis, our hypothesis is that Age affects health quality. We infer that socioeconomic factors (specifically race, poverty, *Physical Activity)  affect health qualtity. Based on our preliminary investigation, we can infer that the health of certain races are more impacted by poverty than others. 

## Discuss next steps. 

+ Our next step would be to look at how physical activity and poverty are related to see if certain lifestyle that promote better health are associated with higher economic status (poverty). 

+ We are also interested in looking at lifestyle practices such as sleep, substance usage, and physical activity play a role in the quality of health of individuals of different economic categories and races.
