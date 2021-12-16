---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Data
order: 2
---
### Market quotations
After filtering out the quotations unrelated to the topico of interest, we are left with a total of 2962875 quotes. In this Section we present a deeper analysis about the characteristics of these quotes to gain a better understanding of the data at hand. Firstly, Figure XXX presents the WorldCloud chart where the most frequent words (after removal of stopwords) are written in a larger font. 

![WordCloud chart of word frequency](./images/WordCloud.png "WordCloud chart")

The reader can appreciate the prevelance of the words "market", "company", and "investment", which provides furhter evidence that the filtering of the quotes worked relatively well. Obviously, the frequency of the words is biased by the seed words we used to select the quotations in the first place, for instance the word "market" was indeed one of them. Nevertheless, the fact that "investment" and "company" were not seed words but appear very frequently in the selected quotes suggests that the filtering did manage to select financial quotes as intended. 

On the other hand, it is quite surprising to see the word "will" appearing so often in the quotations, probably suggesting the forward looking mindset characterizing the financial field. Also, from simply scrolling through the most frequent words there seem to be a rather abundance of words carrying a positive connotation such as "good", "opportunity", and "growth". We will further analyse this topic later in the sentiment analysis Section. 


### S&P500 data
