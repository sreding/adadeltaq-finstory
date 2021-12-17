---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Data
order: 2
---
### Market quotations
After filtering out the quotations unrelated to the topic of interest, we are left with a total of 2962875 quotes. In this Section we present a deeper analysis about the characteristics of these quotes to gain a better understanding of the data at hand. Firstly, the next figure presents the WorldCloud chart where the most frequent words (after removal of stopwords) are written in a larger font. 

![WordCloud chart of word frequency](./images/WordCloud.png "WordCloud chart")

The reader can appreciate the prevelance of the words "market", "company", and "investment", which provides further evidence that the filtering of the quotes worked relatively well. Obviously, the selection strongly depends on the seed words used to filter the sentences. Nevertheless, we notice that none of the most frequent words is one of the seed words we used for filtering, possibly indicating that the filter managed to capture the general financial semantic context. 

On the other hand, it is quite surprising to see the word "will" appearing so often in the quotations, probably evidencing the forward-looking mindset that characterises the financial area. Also, from simply scrolling through the most frequent words there seem to be a rather abundance of words carrying a positive connotation such as "good", "opportunity", and "growth". We will further analyse this topic later in the Sentiment Classification section. 

---

### Data wrangling
For our analysis we will consider the 100 people with the largets amount of quotations in our filtered dataset. While counting the quotes for each speaker we encountered an issue: ‘President Donald Trump’ and ‘Donald Trump’ were categorized as different speakers. We then decided to check if any other speaker had a similar problem. To do so, We first selected the 200 speakers with the largest number of quotations, then we split the name of each speaker in its different parts (name, surname, …), and last we checked if a person’s surname appeared different times. With this procedure, we discovered that Trump was not the only speaker that appeared with different names. In fact, we found that President Obama appeared with three different names (‘President Obama’, ’President Barack Obama’, ’Barack Obama’) and Prime Minister Theresa May appeared with two different names (‘Prime Minister Theresa May’, ’Theresa May’). To overcome this problem we decided to delete the title in front of each name and set the name using the name-surname structure.
-	‘Prime Minister Theresa May’, ’Theresa May’ =>  ’__Theresa May__’
-	‘President Obama’, ’President Barack Obama’, ’Barack Obama’ =>  ’__Barack Obama__’
-	‘President Trump’, ’President Donald Trump’, ‘Donald Trump’ =>  ‘__Donald Trump__’

In the graph below we present the twenty most cited people in our financial dataset.

{% include speakers.html %}

---


### S&P500 data
Since our intention is to study how influential certain individuals are in the financial market, we decide to use the S&P500 index since it is often used as a proxy for the general trend of the economy.

In Quotebank, we are given both a date and a time for each quotation, but it is not clear what this time refers to, since each quotations is published on different journals and it is unlikely that all the publications have been published at the same time. Consequently, we decided to appraoch the problem at a more general level and consider daily values. We leave the more fine-grained analysis as suggestion for future work. We used the SPY([S&P500](https://en.wikipedia.org/wiki/S%26P_500)) dataset from 2015 until 2020 that can be retrieved from the yahoofinance library. This dataset contains all the "Open", "Close" and "Volume" daily values of the S&P500 index from 2015 to 2020. The "Open" value represents the price of the index at the beginning of the day, while the "Close" one is the price at the end of the day. The index trading "Volume" refers to the daily number of shares traded. Analysing the dataset we discovered that many dates were missing, this is because the market is closed on the weekends and on festivities. Since the information accumulated over the weekend impacts the market on the first opening day, we consider the quotes that have been published during closing days as if they were published on the first following opening day.

Now, both index value and volume have their pros and cons for the analysis. On one hand, the price allows us to study whether the sentiment expressed by a certain individual correlates with market movements and whether positive sentiment leads to positive (increase) changes. However, according to the Efficient Market Hypothesis, the price adjusts almost immediately to new information and so financial quotes usually lead to short terms changes in prices because the market will then readjust to its long term trend. Since we look at daily values, we are likely to miss this short term changes. For this reason, we decide to study also the volume. While this does not allow us to see if the change in sentiment agrees with the market movements since the volume traded increases irrespectively of the direction of the price change, it captures short term effects because they will lead to a traded volume larger than average at the end of the day. To further understand this point, here we plot the daily percentage variation of both prices (red) and volumes (blue). It is clear that volume has a larger variation from one day to the other, exactly because it captures also short term variations that happened during the day.

{% include stock_value_varuiation_vs_volume_variation.html %}

Consequently, we will perform the analysis using both the daily volume and the the daily price variation, that is, for each day __n__ we compute the difference between the Open value of the day __n+1__ and the Open value of the day __n__, so it represents how much the stock market has changed over the day __n__. In the graphs below we show two timseries containing the data from 2015 to 2020. In particular we represent the _day_variation_ of these years and the _Volume_.

{% include day_variation.html %}
{% include Volume.html %}

