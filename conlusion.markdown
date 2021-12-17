---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Conclusion
order: 6
---
In conclusion, in this project we have studied **whether certain people seem to me more influential on the stock market than others**. We have done this by studying whether the sentiment they expressed in their quotes correlated significantly with the daily change in price of the S&P500 index and the the daily volumne of shares traded. 

First we extracted the financial quotations using vector representations of the quotes and their simialrity with certain pre-selected seed words. Then, we extracted the sentiment employing a Zero-Shot pretrained classifier. We first noticed that the time series of the average sentiment over the full dataset of financial quotations displayed good correspondence with known financial events that happend in the last years. 

Last, we found that only **7 speakers seem to influence significantly the overall market: Barack Obama, Hilary CLinton, Gerorge Osborn, David Cameron, Richard Cordray, Janet Yellen, Raghuram Rajan, and Arun Jaitley**. As expected, the top leaders of the United States and United Kingdom were found to be the ones with the strongest influence on the market. 

This analysis does not come without limitations. First of all, due to the lack of time, both the selection of the financial quotations and the detection of the sentiments has been done without human supervison, i.e. using only unsupervised methods. Secondly, as already mentioned in the datastory, performing the same analysis using a higher time granularity, perhaps hourly, might lead to more accurate estimates. To do so, a better understanding of the time variable included in the Quotebank is required in order to avoid biasing the analysis. Last, studying only the correlation might leave ou important information. In future projects more advanced statistical methods for time serieses could be employed. 

## Thank you for making it all the way to the end, we very much appreciate it 😊 
