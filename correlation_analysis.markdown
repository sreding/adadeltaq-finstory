---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Analysis and Results
order: 5
---

In order to see if some people quatations impact the stock market, we decided to make two different analysis. The first one consists on studying the correlation between the sentiment expressed by people quotes and the daily variation of the stock market value. The second analysis involves the study of the correlation between the amount of people not neutral quotes and the stock market volume. 

1.  The idea of this first analysis is to detect if a person's quote sentiment could impact negatively or positively the value of the market. We firstly transform the positive, negative and nautral values of the sentiment analysis into integers, 1,-1 and 0 respectively. Because many speakers have more than one quote per day we decided to set as daily sentiment the sum of the sentiments of all the quotes published in the same date because we believe that if a sentiment is repeated it should impact more on the daily market variation. At this point, we evaluated the Spearman rank correlation between the sentiment vector and the daily stock variation vector. We used the Spearman rank correlaton to detect also a non-linear correlation between the two. We apply this procedure for all the speakers selected before.
2.  The idea of the second analysis is to detect if the amount of person's quotes published has an impact on the stock market volume. Here we don't make a difference betweern positive and negative quotes because both of them could have an impact on the amount of traded shares. So, for this analysis we set as quotes vector the one having as component the sum of all positive and negative daily quotes. We first make a one side t-test (where the alternative hypothesis states that volume values associated with dates with no quotes are statistically smaller) in order to compare the mean value of the volume of the days when some non-neutral quote has been published with the mean of the other days, because we know that the mean is not robust to outliers we decided to first remove them from the dataset. As a consequence we removed all the dates that fall outside the boxplot below. 

![boxplot](./images/boxplot.png "boxplot")

We now compare the results obtained with this two methods, in particular our aim is to find people whose results satisfy both tests. The scatter graph below represents what we obtained, the x-axis represents the p-value of the t-test of point 2, while the y-axis represents the p-value of the Spearman rank test o point 1. The colors represent the correlation coefficients of the Spearman rank test. 

{% include plot_results.html %}

As we can see, there are no people that have a low p-value in both tests (so placed in the bottom-left corner), but for instance there are people with low p-value in only one test. Additionally, the two analysis seem not to be correlated, in fact, if we focus on data with the second analysis t-test p-value bigger than 0.95 their first method p-values seem to be uniformly distributed. 

After this analysis we decided to focus on the second method because we believe that due to its assumptions it is less likely to be incorrect. For instance, the first analysis uses the sentiment analysis in a more specific way, but since we only associated to quotes a positive or negative value, without specyfing how much positivie or negative they are, we can not have precise results.   

From the remained t-test we decided to keep only speaker with a p-value smaller than 0.1. These eight seleceted people could potentially have an impact on the S&P500. We than compute the Spearman rank correlation only on this subset between the number of non-neutral daily quotes and the daily stock market volume. From the results only one of them has a a negative correlation, meaning that he doesn't have an impact on it. While the other seven people have positive coefficients and a significant p-value, so we believe that these speakers could have had an impact on the stock market volume. We now present some of them.

- __Barack Obama__
<p align="center">
<img src="./images/obama.jpg" alt="drawing" width="200"/>
</p>

Barack Obama is a politician, in particular he was president of the United States of America from 2009 to 2017. So it's reasonable to think that he could have an impact on the market. In the timeseries below we show the graphical correlation between the amount of quotes and the stock volume. What is interesting to notice is that the amount of quotes is higher in the first two years (so his last years of charge).

{% include Barack_Obama_volume_changed_vs_number_quotes.html %}

- __Hillary Clinton__
<p align="center">
<img src="./images/clinton.jpg" alt="drawing" width="200"/>
</p>

Hillary Clinton is a politician, she has had an important role in the american gouvernment. As we can notice in the timeseries below, she has the highest amount of quotes between mid 2015 and 2017, so during the election campaign with the democratics against Trump.

{% include Hillary_Clinton_volume_changed_vs_number_quotes.html %}

- __David Cameron__
<p align="center">
<img src="./images/cameron.jpg" alt="drawing" width="300"/>
</p>

David Cameron is a politician, he was the Britain prime minister from 2010 to 2016. We again noticed that he was more active during the years of his charge.

{% include David_Cameron_volume_changed_vs_number_quotes.html %}

- __George Osborne__
<p align="center">
<img src="./images/osborne.jpg" alt="drawing" width="200"/>
</p>

Geroge Osborne is a politician, he's a member of the Britain conservative party, in particular he was Chancellor of the Exchequer from 2010 to 2016, menaning that he was the finance minister of England during those years. In fact, as it is shown in the graphic below, he has his highest peaks during those years.

{% include George_Osborne_volume_changed_vs_number_quotes.html %}
 
