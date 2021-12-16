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

---

### Data rangling
For our analysis we will consider the 100 people with the hugest amount of quotations in our filtered dataset. While we were counting the quotes for each speaker we encountered an issue: we found in those names both ‘President Donald Trump’ and ‘Donald Trump’ as different speakers. Moved by this problematic we decided to make a check on each speaker in order to see if the names were correct. We first selected the first 200 speakers with the biggest number of quotations, we split the name of each speaker in its different parts (name, surname, …) and then checked if a person’s surname appeared different times. Doing that we discovered that Trump wasn’t the only one that appeared with different names. In fact, we found that we had the same issue with Obama (‘President Obama’, ’President Barack Obama’, ’Barack Obama’), with Theresa May (‘Prime Minister Theresa May’, ’Theresa May’) and Rick Scott (‘Gov. Rick Scott’). For overcoming this problem we decided to delete the prefix from all this names and set them with their original name.
-	‘Prime Minister Theresa May’, ’Theresa May’ =>  ’Theresa May’
-	‘President Obama’, ’President Barack Obama’, ’Barack Obama’ =>  ’Barack Obama’
-	‘President Trump’, ’President Donald Trump’, ‘Donald Trump’ =>  ‘Donald Trump’
-	‘Gov. Rick Scott’ => ‘Rick Scott’

In the graphs below we show the twenty most citated people in the dataset obtained with all these processes.

![20 most quotated people](./images/data.png "20 most quotated people")

---


### S&P500 data
We used the SPY([S&P500](https://en.wikipedia.org/wiki/S%26P_500)) dataset from 2015 until 2020 that can be retrieved from the yahoofinance library. This dataset contains all the Open, Close and Volume daily values of this stock market from 2015 to 2020. Analysing the dataset we discovered that many dates were missing, this is because the market is closed on the weekend and on festivities so we didn't have data for those days. We decided not to interpolate or fake the values for those days but just not consider them in our analysis. Furthermore, we add a daily value, 'day_variation', that for the day n is computed as a difference between the Open value of the day n+1 and the Open value of the day n, so it represents how much the stock market has changed in this day n.  

{% include day_variance.html %}
{% include Volume.html %}





