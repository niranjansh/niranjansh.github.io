---
layout: post
title:  "COVID-19: Helpful Dashboards"
date:   2020-04-02 20:30:50 
categories: covid19
---

Below are a few of the dashboards that I have found useful in tracking COVID-19.


[The John Hopkins Dash][jhu-dash]

This was one of the first dashboards on the scene back in January when most of the COVID-19 cases were concentrated in the Hubei province in China. I recollect seeing this on Jan 26 when there were less than 3000 confirmed cases worldwide, and hoping that this was the worst of the contagion. We are now at over 1 million confirmed cases worldwide, in a span of 2 months and a week since that date. I like that the dashboard provides overall and by country numbers for the number of confirmed cases (and a time series), and the number of deaths and recovered cases. The global map used to be useful when there were a few cases, but now it is awash with red and not particularly insightful. Certain countries (such as China and the US) have cases broken down by region, while for others the numbers are reported at a country level. This can be a little confusing at times, though to be fair, this may just be a function of how the data is available. I like the dark background and color coding. This was and remains one of the dashboards I check most frequently to get a pulse on the spread of COVID-19. The dashboard hasn't had many new features added over time. 

[1point3acres][1p3-acres]

This dashboard provides the most detailed information for the US and Canada, and particularly the US. I have found it particularly useful to track state and county level numbers for where I reside. It has good time series plots for national and state level cases and fatalities, along with links to news articles. I also like the trend in cases over time by country pegged to a common starting point of when each of them reached a 100 cases. The site is constantly evolving, with new visualizations and tabs added regularly. For example, the cases/million and tests/million in the Case Map, the tab on testing, and the tab that tracks which companies are hiring or laying off employees have been added over time. Yu, who is one of the developers of the dashboard, is one of the best data scientists with whom I have had the opportunity to work at a prior job. She has a Biostatistics PhD from Harvard and is very thorough when it comes to the data, as evidenced by the many universities and organizations that find their [data][1p3-acres-data] useful, including the CDC. 


[IHME][ihme-dash]

The Institute of Health Metrics and Evaluation (IHME) dashboard is exclusively US focused and provides projections at a national and state level of when the expected number of deaths are expected to peak, and also the corresponding resource requirements (beds, ICU beds, and invasive ventilators) over the next few months. In doing so, it presents information not covered by any of the previous dashboards. By matching resource requirements against resource availability, it is able to highlight what the shortages if any are likely to be at peak usage. As of this writing, the resource usage in the US is expected to peak on April 15, and the deaths a day later on April 16. For New York which has the most confirmed cases in the US, the peak usage and peak death/day dates are April 9 and 10th, while for California, they are both April 26. At a national level the projections for cumulative deaths are appx. 92k by the time the toll stabilizes in the next 4 months - 15x the current number of deaths of 6k - with a 95% uncertainty interval of 93k to 178k. 


[Bing COVID-19 Tracker][bing-tracker]

I found the Bing Tracker just about a week ago. What I like is the map overlay of confirmed case densities, with links to testing centers and resources. It does not provide a whole lot more information over the dashboards I mentioned earlier, and is not something I check frequently. 


[COVID-19 Direct][county-ts]

This dashboard provides a county level time series of confirmed cases, deaths, and importantly, tests conducted in the US. It provides information on the number of hospitals and beds, and the days it would take for the number of cases to double. Most of the information is available in the 1point3acres dashboard. I do like the cleaner visualization of the time series here. 

[jhu-dash]: https://gisanddata.maps.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6
[1p3-acres]: https://coronavirus.1point3acres.com/en
[1p3-acres-data]: https://coronavirus.1point3acres.com/en/data
[bing-tracker]: https://www.bing.com/covid/local/california_unitedstates
[county-ts]: https://covid-19.direct/county/CA/Alameda
[covid-proj]: https://covid19.healthdata.org/
[ihme-dash]: https://covid19.healthdata.org/


