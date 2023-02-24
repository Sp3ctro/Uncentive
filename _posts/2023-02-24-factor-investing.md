--
layout: post
title: "An Introduction to Factor Investing"
author: "Uncentive"
categories: post
tags: [Investing, Factors]
---

Factor Portfolios, also known as Style Portfolios, offer an alternative approach to investment decision-making. They originated from the Fama French 3-Factor Model and were later extended to the 4 and 5-Factor Models. These portfolios, which are often market-neutral, aim to isolate specific themes, styles, or "anomalies" such as "Small-Sized Companies" or "Cheap Companies" rather than investing in a particular market such as U.S. or APAC stocks.

By focusing on specific factors, investors can potentially benefit from diversification and risk reduction, as well as potentially higher returns. For instance, the Small Size factor has historically outperformed the overall market, while the Value factor has exhibited long-term out-performance compared to Growth. By constructing a portfolio based on these factors, investors can potentially generate higher returns while mitigating some of the risks associated with investing in a single market.

Factor portfolios are a popular investment strategy used by both institutional and individual investors. They are often used in conjunction with other investment strategies and can be tailored to meet specific investment objectives. Overall, factor investing provides investors with a powerful tool to enhance their returns and better manage risk in their portfolios.

## The Capital Asset Pricing Model
One of the fundamental concepts in finance is the Capital Asset Pricing Model (CAPM), which suggests that assets are priced based on their level of risk relative to the overall market. The model is expressed as follows:

$$R_{i,t} = R_{f} + \beta_{i} \times (R_{M} - R_{f})$$

This equation states that the return on any investment $i$ at time $t$ is equal to the Risk-Free Rate of Return $R_{f}$ plus a coefficient $\beta$ that measures the investment's level of risk relative to the market, which is given by the market's excess returns above the risk-free rate $(R_{M} - R_{f})$.

While the CAPM has theoretical appeal, it has been subject to empirical challenges, as evidenced by the following:

- The R-squared value of the regression is often quite low, indicating that the model has limited explanatory power in reality.
- The CAPM implies that all assets can be replicated by some multiple of the market return, which suggests that it is impossible for investors to outperform the market on a risk-adjusted basis, an assumption that is not supported by empirical evidence.

Despite these challenges, William Sharpe was awarded the Nobel Prize in Economics in 1990 for his contributions to the development of the CAPM. While the model has limitations, it remains an important tool for understanding how asset prices are determined in finance.

## The Fama French 3 and 5 Factor Models
The Fama-French 3 and 5 Factor models extend the CAPM and turn it into - what is essentially - a "multi-factor" model, vs. the CAPM which is a "single factor" model. Eugene Fama & Ken French suggest that...

$$R_{i,t} - R_{f,t} = \beta_{i} \times (R_{M,t} - R_{f,t}) + s_{i} \times SMB_{t} + h_{i} \times HML_{t} + \epsilon_{i,t}$$

where:

-   $R_{i,t}$ is the return of asset $i$ at time $t$.
-   $R_{f,t}$ is the risk-free rate at time $t$.
-   $\beta_{i}$ is the sensitivity of asset $i$ to the market factor.
-   $R_{M,t}$ is the return on the market portfolio at time $t$.
-   $SMB_{t}$ is the return difference between small and large firms at time $t$.
-   $s_{i}$ is the sensitivity of asset $i$ to the SMB factor.
-   $HML_{t}$ is the return difference between high and low book-to-market equity firms at time $t$.
-   $h_{i}$ is the sensitivity of asset $i$ to the HML factor.
-   $\epsilon_{i,t}$ is the idiosyncratic error term.

In words; the model asserts that the return on any investment $i$ at time $t$ is equal to some fixed "alpha" return, plus some coefficients $\beta$ of the market's excess returns as before, as well as some coefficient of the "size premium" and "value premium", plus or minus some noise given by $\epsilon_{i,t}$.

The Size Premium is a phenomenon observed in the stock market where smaller companies tend to outperform larger companies over the long term. This effect is not a guarantee, but it is supported by empirical evidence. The rationale behind this premium is that smaller companies have greater growth potential compared to larger, more established companies. As a result, investors demand a higher return for investing in smaller companies due to their higher volatility.

The Value Premium is another well-documented anomaly in the stock market where companies with lower price-to-book ratios tend to outperform companies with higher price-to-book ratios. This anomaly can be explained by the market's tendency to overestimate the growth potential of expensive companies and underestimate the growth potential of cheaper companies. Value investors often look for stocks that are trading at a discount to their intrinsic value, and this strategy has been popularized by legendary investor Warren Buffett.

Therefore, it is not accurate to say that the Size Premium implies that you should get lower expected returns for investing in Big Companies vs. Small Companies or that the Value Premium implies that you should get lower expected returns for investing in Expensive Companies (relative to Book Value) vs. Cheap Companies (relative to Book Value). Rather, both premiums suggest that investing in smaller and cheaper companies can lead to higher expected returns over the long term, but this is not a guarantee and investors should carefully consider their investment goals and risk tolerance before making any investment decisions.

The Model was later extended to include 2 more factors...

- Investment, which is the premium you get for owning stocks of companies who invest aggressively in their growth, vs. companies who invest conservatively in the growth (e.g. high/low CAPEX)
- Profitability, which is the premium you get for owning more profitable firms vs. less profitable firms (e.g. EBITDA)

Eugene Fama won a Nobel Prize for this too.

## The "Factor Zoo"
The Fama French model has been instrumental in advancing our understanding of asset pricing and has provided a framework for researchers to identify new factors that may explain asset returns. However, the proliferation of new factors has led to concerns about data mining and overfitting, where researchers may identify spurious relationships that do not hold up in out-of-sample testing.

While some factors such as Betting Against Beta, Low Volatility, and Momentum have been widely accepted and implemented in investment strategies, the sheer number of research papers on new factors has led to a "factor zoo" of sorts. This has caused some academics in Finance to feel embarrassed as it has become more of a race to publish new papers on novel factors for the sake of citation counts, rather than advancing our understanding of asset pricing.

It is true that some researchers may have engaged in data mining to find relationships between accounting metrics and future returns, but it is important to note that legitimate research on new factors can provide valuable insights into the behaviour of financial markets. Nonetheless, investors should be cautious when considering new factors and should rely on a thorough understanding of the underlying economic rationale and robust out-of-sample testing before implementing them in their investment strategies.

# Factor Investing
Factors are designed to be market neutral. For instance, consider the Value factor, which represents the difference in returns between holding high-value companies and low-value companies. This essentially means that you pay a price in the form of lower returns for owning high-value companies over low-value companies. If we aim for higher returns, it implies that we can buy low-value companies and sell high-value companies. To construct such a portfolio, we can create two positions:

-   Long Low Value = + Stocks with Low Value characteristics + everything else
-   Short High Value = - (Stocks with High Value characteristics + everything else)

Here, "everything else" refers to the other factors in the models such as the Risk Free Rate, the Size factor, and the market return, among others. Simplifying the equation, we can write:

Portfolio Holdings = + Stocks with Low Value characteristics + everything else - Stocks with High Value characteristics - everything else

The "everything else" term cancels out, leaving us with:

Portfolio Holdings = + Stocks with Low Value characteristics - Stocks with High Value characteristics

In practice, if we go long on 10 stocks and short 10 stocks, and size the positions appropriately, we achieve a "delta neutral" position, meaning that any movement in the overall market is hedged.

## What's next?
Given that we've provided a high-level overview of the history of Factor Investing and covered some of the interesting topics in the field, in the next post we'll conduct a review and back-testing of some of the popular factor strategies to evaluate their performance over time.
