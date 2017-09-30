---
title: Decomposing personal finance data
author: Rajesh Korde
date: '2015-01-04'
slug: decomposing-personal-finance-data
categories:
  - Analysis
tags:
  - personal finance
  - time series analysis
disqusIdentifier: 20150104
showSocial: true
comments: true
---

Several personal finance management websites like mint or fidelity offer services to track your assets, liabilities and net worth over time. Some standard time series analysis techniques can be applied to this data to analyze your monthly spending habits, trends in your net worth and even predict your future net worth. In this post, I do a simple experiment on my personal finance data to break down my monthly spending habits.


I have always been fairly lax about tracking my money. When I bought a house back in 2007, I started a simple spreadsheet where each month I added a new row tracking my assets (investments, retirement funds, bank balance etc), liabilities (mortgage, car payments, credit card bills etc) and my net worth. Thus, I have roughly 7 years worth of data at a monthly granularity. I wanted to find out more about how my net worth changes month over month. So I created a new table that had the change in net worth each month. A large positive number means either the stock market went up, or I got a bonus at work etc. A large negative number would mean a big expense or a stock market correction. The plot below shows this data. The y-axis is obfuscated for privacy.

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506718853/Monthlydiffspixelated_sjo9y0.png">}}

Unfortunately, this graph is not very useful as its very hard to figure out any trend in this noisy data. Luckily, this time series can be decomposed into trend, seasonal and random graphs to get a clearer idea of the patterns in data. The observed graph below is the original graph and can be expressed as a sum of trend, seasonal and random graphs. The trend graph shows the overall trend in month over month net worth change. The seasonal graph extracts the cyclic spending habits. The random graph accounts for large abnormalities (big stock market surge, big expense etc) in the spending habits.

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506718853/DecompositionMonthlyDiffsPixelated_osshoe.png">}}

Key takeaways for me from the graph above:

* The overall trend in month over month change in net worth is positive :) but it seems to have plateaued off since middle of 2013 :(
* I tend to spend a lot May-July every year (usually traveling or expense anticipating the sept bonus) as indicated by #2. The spike in #1 is probably from the annual bonus around aug-sept.
* The random graph is pretty accurate at capturing large expenses. #3 was due to a trip to India and #4 matches nicely with an vacation in Africa in 2012.