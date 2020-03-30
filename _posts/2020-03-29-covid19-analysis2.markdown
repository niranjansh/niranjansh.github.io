---
layout: post
title:  "COVID-19: A Review of a Prior Prediction"
date:   2020-03-29 20:30:50 
categories: covid19
---

Back on March 15, when the number of confirmed cases in the US was still under 4000, I had [made a prediction][pred-prev] for the number of confirmed cases in the US for the upcoming week using a set of countries - Italy, Iran, and South Korea as a reference. Our worst case scenario was using Italy as a reference, with a predicted 12,315 cases. For the first few days, the US was slightly above the predicted values. However, as you can see below, starting March 19, the US was off on its own trajectory. On March 22, the US had 33,276 cases - nearly 3x what I had predicted. 

<img src="{{site.baseurl}}/assets/images/us_prediction_march16_22_update.png">

One of the caveats I had mentioned in my previous post was that it did not take into account the number of tests being conducted in the US. When we look at the number of tests, we observe that it has ramped up quite a bit through March 16-22, as seen below

<img src="{{site.baseurl}}/assets/images/us_test_cases_march16_22.png">

The number of tests has increased from 25k on March 15 to 225k on March 22, an 8.75x increase. The confirmed cases are a subset of the actual number of COVID-19 cases in the population. As we ramp up testing, we are able to identify more instances of infections. The dramatic increase in the number of confirmed cases can partly be attributed to an increase in the number of tests being conducted. But that is just part of the answer. 

When we look at the ratio of confirmed cases (cumulative) to all tests with results (cumulative), we observe a general increasing trend from March 18 to 29, as seen below. 

<img src="{{site.baseurl}}/assets/images/us_test_positive_ratio_mar_4_29.png">

There could be many reasons for this trend. Part of it is the underlying spread of infection, though there could also be confounding effects as states ramp up their testing. Testing in the early phases was limited to at-risk population (those that had traveled or come in contact with someone with COVID-19), resulting in a higher positive outcome rate. As tests become more prevalent, those with symptoms can now get tested. If the pace of testing outpaces the spread of the virus, then we would expect the proportion of positive outcomes to begin its decline. The worst case scenario, if everyone has the virus, results in a positive ratio of 1 and the best case scenario - where no one has the virus - results in a positive ratio of 0. As of now, we are at a ratio of 0.17 i.e. nearly one in 6 people that have been tested in the US and whose results are available have tested positive for COVID-19. 

[pred-prev]: https://niranjansh.github.io/covid19/2020/03/16/covid19-analysis1.html