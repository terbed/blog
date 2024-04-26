---
title: Advances in FinML Chapter 02 - Financial Data Structures
tags: finml data
categories: Book-Digest
toc: true
comments: true
---

<div class="abstract-block">
<strong>TL;DR</strong>
This is a book digest of the <b>Advances in Financial Machine Learning</b> book by <i>Marcos Lopez de Prado</i>. I highly recommend you get a copy of this masterpiece, a must-have financial ML book. In this article, we delve into the book's second chapter, which is about financial data structures. We will discuss the different types of economic data, how to handle them, and the importance of data structures in financial machine learning. Understanding the data structures is crucial for building effective machine learning models in finance, as the heart of the ML model is the data it is trained on. We can only make an appropriate model if we know the data well.
</div>

# Introduction
It is advisable to work with the raw unstructured data sources and make our own structured data.

# Types of Financial Data
1. Fundamental Data
2. Market Data
3. Analytical Data
4. Alternative Data

# Bars
Bars are the most common data structure in finance which aggregates and compresses raw tick trades data.
We structure raw trades data (tick) data into bars. Bars aka candle-stick-data describes a block of raw trades data
with OHLCV (Open, High, Low, Close, Volume) values. The main goal of bars is to reduce the noise in the data and make it more manageable[[One day of BTC tick data is approx. 60 MB in 2023. If the volume increases this size also increases.::rsn]]. 

We can determine the bar size by the time, tick, volume, or dollar amount. The most common is the time bar, although it is not the most informative and predictive.


## Time Bars
This is the most common way to aggregate data: we have a fix time window for which we calculate the OHLCV data. The most common time bars are daily bars, but we can also gather hourly, minute, second, or any desired time interval bars. The problem with time bars is that they are not informative and predictive. The market is not active all the time, and the most important information is not evenly distributed in time. The dynamics of the market is always changing, time bars are not able to capture this information.

Here you can see the 1 minute time bars candlestick plot of BTC/USDT for one day: 
<iframe src="/assets/figs/afinml02/time_bars2.html" width="100%" height="500" frameborder="0"></iframe>

If you zoom in around 12:00 you can see large price movements and market activity and a volume spike.

## Tick Bars

## Volume Bars

## Dollar Bars

## Custom Information-Driven Bars

### Imbalance Bars

### Run Bars

# Multi-Product Series
In this section Prado discusses how to handle multi-product series and futures roll. I have no experience with this topic, so I will skip this part. I work with single-product series, and I am not familiar with futures roll as I have only worked with spot prices and perpetual futures where there is no roll and expiration date. I don't see why we would construct a multi-product series, we could just train a predictive model for each product separately. I will come back to this part later when I have more experience with this topic. Please let me know if you have any insights on this topic in the comments.

<div class="block question-block">
  <strong>QUEST</strong> Let me know in the comments if you have insights on how the ETF trick could be used in practice and when would it be beneficial. 
</div>

# Sampling Features

# Exercises and Solutions