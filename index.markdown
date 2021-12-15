---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Project Introduction
order: 1
---

## Whose Sentiment towards the Market influences the Market Sentiment?
#### The datastory to the ADADELTA-Q project in the context of the EPFL [Applied Data Analysis](https://dlab.epfl.ch/teaching/fall2021/cs401/) course (2021 edition).

### Introduction 
"Bitcoin Price Slips on Elon Musk’s Breakup Meme Tweet". This was the heading of an [article](https://www.wsj.com/articles/bitcoin-price-slips-on-elon-musks-breakup-meme-tweet-11622805958) of The Wall Street Journal published the 4th of June 2021. On that day, Elon Musk tweeted "#Bitcoin ₿ 💔", and the cryptocurrency market went crazy. This is all it took to Elon Musk to cause a drop of about 4% in the value of Bitcoin and other cryptocurrencies, one word and two emojis. Now, cryptocurrencies have been proven to be much more volatile than financial markets, which could explain its susceptibility to influential peoples' statements. But this got us thinking.. **Can this phenomenon also happen in the financial market? Are there individuals that can influence the behaviour of the market?** This is what we are going to study in this project.

Market Sentiment, as described in this [article](https://www.investopedia.com/terms/m/marketsentiment.asp), "refers to the overall attitudes of investors towards a financial market". In this project we use the [Quotebank](https://zenodo.org/record/4277311#.YX0LcpuxW0o) dataset to study whether the Market Sentiment can be affected, in the sort-term, by the Sentiment expressed in financial quotations published in news articles. We do so by following the pipeline presented here:

![General Overview of Data Pipeline](./images/overview.png "Proposed Pipeline")
