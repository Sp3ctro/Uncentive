---
layout: post
title: "Backtests don't account for Fear, Uncertainty and Doubt"
author: "Uncentive"
categories: post
tags: [Backtesting]
---

# Backtests don't account for Fear, Uncertainty and Doubt

Backtesting is an important step in creating trading automated or systematic strategies. Google "best practices for backtesting" and you'll find many article or blog post cautioning against data snooping, over-fitting, and look-ahead bias. Look-ahead bias in particular specifically is defined according to Investopedia as:

> [...] using information or data in a study or simulation that would not have been known or available during the period being analyzed.

It's important to avoid using a trading signal from $T+1$ in our backtest that we shouldn't yet have as part of our trading actions taken on $T$. If we do, then our backtest is invalid.

Another important but "softer" benefit of backtests is that they help us determine whether we can mentally and emotionally tolerate the strategy's volatility. If you have a strategy that's profitable in the long run, but which has extreme short-term fluctuations, it will very hard to keep it running in spite of large drawdowns.

What do our the "emotional" risk tolerance level have to do with backtests?

## Heating Oil humbled me
I recently put a trend-focused strategy live. When designing the strategy I backtested thoroughly and observed many graphs which looked approximately like this...

<p align="center"><img src="assets/img/backtest_fud.png" /></p>

We're looking at 5[^1] years of data, and as you can see, there are ups and downs - slow and fast alike. Somewhere in there is a 1-day loss of over 10% of the starting capital. During another period, there's a 100% gain followed by a sharp mean-reversion resulting in a 40% peak-to-valley loss. When you look at the graph - which shows the long(ish)-run behavior of the strategy - you might say to myself "yeah, this will be volatile, but I can stick with it because I know the long run results will be great."

But once you're trading live, with real money, are you sure you'd be this confident?

In my case, my strategy's portfolio included the CME Heating Oil contract. For me that's a big trade. At current rates it exposes the buyer (or seller) to about \$140,000 worth of Heating Oil, which currently has an annualised standard deviation of ~%40. A 1-day, 1 standard deviation move is about ~\$3.5k USD. That's the expected 1-day, 1 standard deviation of my entire strategy *not including* CME Heating Oil. This is a huge position for me to trade. "But look at the long-run backtest!" I say to myself. "Sure it's a big position and sure it swings a lot, but the long run behavior is worth it."

I was nowhere near this sanguine when I turned the strategy on in live trading and went Long CME:HO along with 5 other grown-up sized contracts...

**Day 1:** By 11am I'm down $2k on HO. "Well, that's just a few hours in. I can't determine anything based on 1 day, let alone 2 hours".

**Day 2:** I check my PnL twice as often as Day 1. At 10am I'm down \$3k on HO. "Ok this is starting to not be enjoyable...I guess this is how it's going to be". I look back at the backtests, I validate that the 95%ile 1 day VaR is $\$x$, and that a 5 standard deviation move based on the observed returns distribution is $\$y$.

**Day 3:** HO is flat. But I check my PnL several times each hour. I dread the idea of my portfolio having a third loss of the magnitude i'm now experiencing.

**Day 4:** HO has resumed selling off. I am now questioning myself. "Is my backtest actually representative?" and "What if my backtest was just a lucky period for the strategy?". "If I could see into the future and know whether things get better, i'd happily just deal with this."

**Day 5:** HO begins to sell off at lunch time. I've had enough - I know based on logic and my backtest that this can happen, but experiencing it first-hand is too much to bear. I sell at market and go looking for smaller contracts to replace it with.

When you backtest, you can dispassionately observe the ups and downs of a strategy and contextualise its volatility versus the long-run expected return. But in reality, once you trade it live, you won't have the luxury of foresight anymore. You'll experience similar or worse losses "out of sample" without having the reassurance that the performance will pick up again. This puts us at risk of being discouraged from trading our strategy which - all things considered - might actually be great.

## What can we do to avoid it?
In my experience, these three practices are a great start to avoiding this pattern:

- **Simulate the portfolio:** Use a paper trading account for a few weeks to experience the feeling of not knowing what's coming next. It doesn't solve the issue entirely as we know intuitively that the PnL won't be real, but it certainly helps.

- **Start MUCH smaller:** In my case, I also started too big. When going live with a strategy, start as small as possible. Rather than a big CME futures contract, consider using the Mini or Micro contract, for example. Take 1-lot positions instead of 5-lot clips. Validate the expected behavior; get acquainted with the daily ebb & flow, and resolve any post-go live issues during this period.

- **Use "Training Wheels":** When you go live, put on a hedge for your initial set of positions for the first day or two with another asset or contract which is inversely correlated. This will allow you to be trading live at your small initial size without much risk. As you get more confident, you can reduce, or entirely unwind the hedge. Once you're ready and comfortable, ramp up the size over time.

There are, of course, numerous other ways to not "freak out" but perhaps these three above are a good starting point for your own approach.

[1]: For a backtest, we know that 5 years is not a long time. 10+ years is ideal, with lots of varied market regimes thrown in. But for the purpose of this article, the *length* of the backtest isn't the topic of discussion.