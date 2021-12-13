---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Sentiment Classification
order: 4
---
### Sentiment Classification
The key step to answer our research questions is to detect the sentiment expressed in each one of the quotations, that is, we need to perform a Sentiment Analysis task. The State-of-the-art methods for Sentiment Analysis are often supervised methods. However, such methods require a large amount of labeled observations in order to be trained or fine-tuned, and without fine-tuning the perfromance can be quite unsatisfactory. Another solution was to use unsupervised models. Althought these methods would overcome the problem of labeled data, they showed a limited capabilty of detecting the correct sentiment in trial sentences. To combine the best of the two worlds, we decided to employ the so-called "Zero-Shot NLP models" which are pretrained (supervised) models that are able to perform well on tasks other than that used for training and on unseen data, without requiring fine-tuning. The reader can experiment with sentiment analysis perfromed by the pretrained (and not fine-tuned) BERT model, the unuspervised VADER model, and the Zero-Shot Classifier.

INCLUDE SIMULATION???

### Results of the Sentiment Classification 
The plot below presents the percentage of posiive, negative, and neutral quotes from 2015 until 2020. 

We also analyzed how the average sentiment expressed in financial quotes developed over time in the past years. Can we related that to certain events? 

Finally, we perfrom the same analysis as before regardin the frequency of the words used to see what are the most importnat words used in the quotes that are categorized as negative, positive and neutral. 

