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

### Results of the Sentiment Classification 
The plot below presents the percentage of posiive, negative, and neutral quotes from 2015 until 2020. 

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


