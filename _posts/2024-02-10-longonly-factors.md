---
layout: post
title: "Non-Traditional Long Only Factor Returns"
author: "Uncentive"
categories: post
tags: [Investing, Factors]
---
As a follow up to the factors we explored previously, I wanted to share some very high level analysis I did on various implementations of Long Only Factor portfolios using non-traditional return drivers, such as...

| Return Driver    | Category        | Core Idea                                                          | How it is measured                                             | Ideal Values are... |
|------------------|-----------------|--------------------------------------------------------------------|----------------------------------------------------------------|---------------------|
| High EBIT / EV   | Growth           | Earnings before interest and taxes relative to enterprise value    | EBIT divided by enterprise value                               | High                |
| FCF/Price        | Value           | Free cash flow relative to stock price                             | Free cash flow divided by stock price                          | High                |
| Cash/Assets      | Value           | Proportion of assets held in cash                                  | Cash divided by total assets                                   | High                |
| Inventory Change | Fundamentals    | Efficiency of inventory management                                 | Change in inventory over a period                              | High                |
| Asset Turnover   | Fundamentals    | Efficiency of asset utilization                                    | Revenue divided by average assets                              | High                |
| ROE              | Fundamentals    | Profitability relative to shareholder equity                       | Net income divided by shareholder equity                       | High                |
| ROA              | Fundamentals    | Profitability relative to total assets                             | Net income divided by total assets                             | High                |
| FCF Per Share    | Fundamentals    | Amount of free cash flow generated per share                       | Free cash flow divided by number of shares                     | High                |
| EBITDA Margin    | Fundamentals    | Operating profitability excluding certain expenses                 | EBITDA divided by revenue                                      | High                |
| ROCE             | Fundamentals    | Efficiency of capital employed                                     | Earnings before interest and taxes divided by capital employed | High                |
| Momentum         | Technical/Price | Price trend indicating continued performance in the same direction | Rate of change in price over time                              | High                |
| Low Beta         | Technical/Price | Lower beta compared to market                                      | Measure of systematic risk relative to market                  | Low                 |
| Low Vol          | Technical/Price | Lower volatility compared to market                                | Measure of standard deviation of returns                       | Low                 |
| Price/Sales      | Technical/Price | Ratio of market capitalization to total sales                      | Market capitalization divided by total sales                   | High                |

For each of these return drivers above, I rank all companies in the S&P 500 from best to worst and go long the top 10, rebalancing each month. For example for the first return driver - EBIT / EV - every month I am ranking companies based this ratio and because the "Ideal Values" are high values, I sort companies by EBIT/EV from high to low and go long the "best" 10.

The investment universe is companies in the S&P 500 at the given time in the backtest, who have at least 1 year of price data, and who are not in the top 10% of firms ranked by Beta. There's evidence to suggest that extremely high beta firms generally don't do well in the long run so I filter those out across all tests. The backtest periods are from 1 January 2000 to 1 July 2023. I won't be sharing the nitty gritty details of these factors and their construction but the outcomes in general are indicative I think...

|                  | Avg. Ann. Return | Avg. Ann. Std | Annual Sharpe | Worst  Loss 1Y | Winning  Years |
|------------------|------------------|---------------|---------------|----------------|----------------|
| Inventory Change | 10.30%           | 20.50%        | 0.50          | -52.11%        | 79.17%         |
| Asset Turnover   | 11.52%           | 14.74%        | 0.78          | -29.84%        | 87.50%         |
| ROE              | 11.42%           | 17.08%        | 0.67          | -25.21%        | 79.17%         |
| ROA              | 9.90%            | 19.56%        | 0.51          | -49.22%        | 83.33%         |
| EBIT/EV          | 9.32%            | 25.21%        | 0.37          | -52.24%        | 75.00%         |
| FCF Per Share    | 12.92%           | 29.92%        | 0.43          | -96.46%        | 79.17%         |
| EBITDA Margin    | 8.76%            | 23.35%        | 0.38          | -62.64%        | 70.83%         |
| FCF/Price        | 10.34%           | 29.09%        | 0.36          | -70.58%        | 62.50%         |
| Low Beta         | 8.87%            | 11.03%        | 0.80          | -23.18%        | 83.33%         |
| ROCE             | 7.36%            | 17.63%        | 0.42          | -54.32%        | 83.33%         |
| Momentum         | 7.37%            | 24.29%        | 0.30          | -77.60%        | 75.00%         |
| Low Vol          | 10.17%           | 11.43%        | 0.89          | -13.87%        | 75.00%         |
| Cash/Assets      | 8.95%            | 24.97%        | 0.36          | -73.99%        | 70.83%         |
| Price/Sales      | 10.35%           | 28.25%        | 0.37          | -71.79%        | 75.00%         |

Of course if you were to implement these yourself, I recommend doing your own research (standard "This is not financial advice" disclaimer here). It's also important to reiterate that these are 10-position long only portfolios so your mileage will vary if you add more stocks.
