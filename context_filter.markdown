---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Context Filter
order: 3
---

The sheer size of Quotebank makes reductions unavoidable. We filter:
1. Quotes that are not useful for our purposes: Speaker can't be identified with certainty
2. Columns: `phase` and `probas` (after identifying the speaker)
3. Off-topic quotes

While the first two points can be trivially executed, the third criteria requires more care. In the following we will briefly outline how we extracted the semantics from quotes to filter off-topic quotes.

### Methodology
The selection of the quotes that are relevant to the topic of financial markets is done using vector representations of words, in particular we employ [fastText](https://fasttext.cc/) , a state-of-the-art model for text representations.
We tokenize the data and convert to lower case, removing any english stopwords.
We then train the model using the standard unsupervised fastText. This way, each quote is transformed into a set of word embeddings. We define a set of keywords that we consider representative of the topic we are analyzing, i.e.`[stockmarket, stock, bonds, shares, obligations, finance]` and compute the mean vector representation of each word. We then compare the embedding of each word in a quote to the computed key word vector and choose the closest distance as representative value for similarity of the whole quote. We filter quotes by some threshold of similarity to reduce data.

### Results

{% include PCA.html %}

We can see in the above figure the 2D PCA of:
1. The Median of the Keywords (yellow)
2. The Keywords (Green)
3. Randomly Sampled tokenized versions of words from Quotes (small red)

We can see that even in this low dimension, some semantic difference are apparent. Despite the fact that quotes data has relatively small context to provide to fasttext, the filtering works well.
