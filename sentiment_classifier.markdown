---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Sentiment Classification
order: 4
---
### Sentiment Classification
The key step to answer our research questions is to detect the sentiment expressed in each one of the quotations, that is, we need to perform a Sentiment Analysis task. To do so, we had the choice between pretrained supervised models (BERT), unsupervised models (VADER), or Zero-SHot NLP model. The following table summurizes our thought process.

| Model |  Pros |  Cons |
|-------|-------|-------|
| Pre-trained BERT | State-of-the-art sentiment analysis results | Without fine-tuning the perfromance was unsatisfactory and fine-tuning requires labeled data |  
| Unsupervised VADER | Does not require any labeled data | The performance on sample sentences was unsatisfactory|
| Zero-Shot Classifier | Does not require labeled data for fine-tuning and predicted reasonable sentiments on sample sentences | Heavier to run| 

Given the above pros and cons in the end we decided to use the later model, i.e., the pretrained Zero-Shot Classifier.

INCLUDE SIMULATION???

### Is Trumo a negative word?
In order to check if the sentiment classification worked as expected, we look into the most common words that are not stopwords for each category: positive, negative, and neutral. We visualize the results in Figure ???. It can be noticed that, while certain words, e.g. market and company, are common to all categories because in general relevant for the finaincial field, it can be seen that semantic-carrying words most of the times belong to the correct semantic class. For example, good is quite often present in quotations categorized as posiitve while difficult and crisis can be often found among the negative class of quotations. On the other hand, it should be kept in mind throughout the project that the sentiment categories are the result of an (unsupervised) algorithm, meaning that they should be considered with caution. Nevertheless, it appears that the senitment classification has worked as expected. 


![WordCloud chart of word frequency per sentiment class](./images/WordCloud_all.png "WordCloud chart of word frequency per sentiment class")

Keeping in mind that the senitment has been detected in a unsupervised way, there are some interesting points that can be made:
- The word "technology" appears very frequently among the class of positive quotes, which is in agreement with the storng growth of the so called "Big Tech" companies in the past years. 
- The word "bank" does not seem to be among the most common positive words but it appears relatively frequent among quotations carrying a negative senitment.
- It is also quite surprising to see that among the most common words within negative sentences there are the words "American" and "Trump". The fact that the selected quotations cover the 2 years before the elections and the first 3 full years of Trump's Presidency might indicate a general discontent towards the economic ideologies or policies proposed by Trump. 

### Are we happy about our economy? 
The sentiment expressed in the news is an extremely useful tool to detect how the financial sector and the overall economical stability are perceived at a certain point in time. In this section we analyze the overall sentiment expressed within all the over 3 million quotations to see if the time series of the sentiment displays regulariteis that can be associated with known financial events. 

First, the following plot show 


We also analyzed how the average sentiment expressed in financial quotes developed over time in the past years. The plots presented here show for each year, starting from 2015 until 2020, the average financial sentiment. 

![WordCloud chart of word frequency](./images/average_sentiment_time_series.png "Time series of the average sentiment")

Finally, we perfrom the same word frequency analysis to find the most important words used in the quotes that are categorized as negative, positive and neutral. 

<iframe src="/images/plot_2.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>


