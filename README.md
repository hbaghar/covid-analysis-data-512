# DATA 512: Human Centered Data Science

## Course Project

During the last three years we all have been experiencing a global pandemic. This has been tragic and disruptive to many countries and has taken a deep personal toll on many individuals and their families.

One aspect that has been hard to miss in the last three years is the datafication of the pandemic. That is, many aspects of the individual toll of the pandemic have been collected, aggregated and re-represented as data. This datafication gives us the privilege to examine the pandemic from potentially many different perspectives to understand how it has changed lives and how it has changed society. To be honest, we are actually at the very beginning of understanding and comprehending these impacts.

During this Course Project you are going to begin taking a look at some of the social aspects of the pandemic by conducting a human centered data science analysis of some available COVID-19 data. In Part 1- Common Analysis, every student in the course will work from the same datasets. Students will be assigned to analyze data for one specific County of the United States.

## Part 1: Common Analysis

Assigned county: Salt Lake County, Utah

### Data Sources

- `RAW_us_confirmed_cases.csv`: file from the Kaggle repository of [John Hopkins University COVID-19 data](https://www.kaggle.com/datasets/antgoldbloom/covid19-data-from-john-hopkins-university). Lists confirmed COVID-19 cases for each county in the US as a cumulative time series organized in a panel format.
- `US_State_and_Territorial_Public_Mask_Mandates_From_April_10__2020_through_August_15__2021_by_County_by_Day.csv`: Lists daily updates vis-a-vis masking policies enforced in various counties in the US. More information [here](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i)
- `mask-use-by-county.csv`: Lists masking compliance in various counties collected through survey data. More information [here](https://github.com/nytimes/covid-19-data/tree/master/mask-use)

### Visualization

![Final visualization for Step 2](output.png)

### Reflection

#### 1. The visualization

The figure above plots the growth rate of daily COVID-19 cases. We reduce the noise by first taking a moving average of daily COVID cases and then calculating day-over-day percentage growth in cases. Given that this was also noisy, we applied another moving average to further smooth the visualization. We have truncated some of the dates early into the pandemic because the percentage change in smaller number of cases was unstable and making it hard to view the rest of the pandemic as can be seen in the section above where we wer refining the visualization. The second axis plots a moving average of the daily COVID-19 cases reported.

From this graph, we can see that much of the growth rate is reducing in the green area of the chart and the bulk of negative growth rate (i.e. falling daily cases) is in the green region. While this may seem like a good correlation, it cannot be concluded to be as causation mainly because there were many interventions adopted during the pandemic. More vitally, vaccines were made available in this county from February 2021 and likely had an influential part to play in containing the growth as well, though that needs to be investigated more thoroughly. Another observation her is that the number of cases sharply increased when the mask mandate was in place (possibly why the mandate was instituted in the first place), and we ony see a dip after about the month or so of enforcing the mask mandate.

#### 2. Collaborative Activities

While the assignment emphasised on calculating a "derivative" for the data, I focused on making the analysis simple and easy to digest for someone who does not have a heavy mathematical background. Since, the derivative is basically a rate of change, for this analysis I used a percentage difference to understand how cases grow on a daily basis.

Collaborating with my peers allowed me to discuss different approaches to solve this problem and greatly speed up the data cleaning process. A lot of my peers used tools that calculated change points in the series and tried to infer if these change points are close to mask mandate related events. However, this method lacked in terms of quantifying what the change looked like, which is why I made use of a percentage difference.
