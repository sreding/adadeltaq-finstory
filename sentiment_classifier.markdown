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
| Zero-Shot Classifier | Does not require labeled data fro fine-tuning | Heavier to run| 

Given the above pros and cons in the end we decided to use the later model, i.e., the pretrained Zero-Shot Classifier.

INCLUDE SIMULATION???

### Results of the Sentiment Classification 
The plot below presents the percentage of posiive, negative, and neutral quotes from 2015 until 2020. 

We also analyzed how the average sentiment expressed in financial quotes developed over time in the past years. Can we related that to certain events? 

Finally, we perfrom the same analysis as before regardin the frequency of the words used to see what are the most importnat words used in the quotes that are categorized as negative, positive and neutral. 

