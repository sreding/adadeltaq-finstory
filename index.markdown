---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Project Introduction
order: 1
---

## Are random fluctuations of the stock market really random?
#### The datastory to the ADADELTA-Q project in the context of the EPFL [Applied Data Analysis](https://dlab.epfl.ch/teaching/fall2021/cs401/) course (2021 edition).

### Abstract
The goal of this project is to construct a pipeline that allows to identify those individuals whose quotes have an impact on the stock market and its fluctuations. We use the [Quotebank](https://zenodo.org/record/4277311#.YX0LcpuxW0o) dataset as it includes a large amount of quotations from different sources since 2015. We filter these quotes to retain only quotations related to the stock market. Then, we classify the sentiment of each quote as either positive, neutral, or negative, and we study whether for each individual these sentiments are correlated with a sudden change in the US stock market.
![General Overview of Data Pipeline](./images/overview.png "Proposed Pipeline")