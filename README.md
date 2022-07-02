# Trader Strategy - Interview


Your goal is to create new emporus trading strategy, after you'll create the strategy you need
to test it works on simple scenario and afterwards back test it, so we can show it can run
on data from 01.01.2019 and print its statistics.

The data source from where you are going to take the close prices is yfinance: https://pypi.org/project/yfinance/
in order to apply your requested strategy you can use the libriary called ta-lib, this lib already implemented the
technical indicators as RSI, SMA, etc... but you can choose whatever lib you are comfortable with.
If you choose to go with ta-lib there are examples of how to use it with yfinance: http://blog.adnansiddiqi.me/introduction-to-technical-analysis-in-python-using-ta-lib/ and
https://towardsdatascience.com/technical-analysis-of-stocks-using-ta-lib-305614165051.
The library source page is: https://mrjbq7.github.io/ta-lib/


## Strategy to implement
The Event we want to add is a "Weekly OverSold using Bollinger Bands"
* The logic is:  if the Weekly Close Price of the asset, is Lower than the Weekly Lower Bollinger Band (20,2), consider this as a Bullish Signal.
* Assume each signal would be entered on the following week's Open, and closed on the weekly close 5 weeks after the signal. 
Meaning if I'll receive one signal on 04.07.2022 it will last until 08.08.2022 so if any other signal which will be between those periods will be ignored, 
since we already have a live signal.

## Provide in the exercise:
* instructions + requirements.txt in order to execute your project.
* Method which have an input(ticker, start_date, end_date) and will print:
  * Win Ratio % (what % of the trades were positive) - 
    * trade is considered to open on the date of the event and closed on the event end time
  * What was the average return per trade (how much% in average does these trades win/lose)
  * Benchmark Beating Ratio (what % of the trades gave better returns than the "SPY" ETF)
  * What was the average outperformance  (for example, in a specific signal - if IBM long trade gave 6.5% in 5 weeks, and the SPY ETF rose 4% in that period of 5 weeks, the Outperformance for this signal is 2.5%)
* Test scenario: For the timeframe from 01.01.2019 for the symbol "IBM", please identify all the dates this event gave a Bullish signal and the statistics above

Feel free to write down additional assumptions if you feel are needed. (edite)