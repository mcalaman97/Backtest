# Portfolio Backtesting
This script allows users to backtest their investment strategies using historical data from Yahoo Finance. The script loads data for securities in the portfolio, and users can enter the weights of the portfolio for each rebalance date where they trade. The script uses the yfinance library to load data from Yahoo Finance, pandas for data manipulation, and scipy for optimization.

# Usage
Create an instance of the Portfolio class. The class takes the following parameters:

- start_date: string in the "YYYY-MM-DD" format, the start date of the backtest
- end_date: string in the "YYYY-MM-DD" format, the end date of the backtest
- investment_universe: list of tickers used throughout the life of the portfolio
- ptf_size: int, the dollar size of the portfolio at inception
- monthly_data: string, optional parameter. If different from 'N', then the function loads monthly data.

Example:
portfolio = Portfolio("2020-01-01", "2020-12-31", ["AAPL", "GOOG", "AMZN"], 1000000)

Use the rebalance() method to update the weights of the portfolio on a rebalance date. The method takes the following parameters:

- date: string in the "YYYY-MM-DD" format, the date of the rebalance
- weights: dictionary containing the weights of the new portfolio after rebalance. The keys are the securities tickers, values are the correspondent weights.

Example:
portfolio.rebalance("2020-02-01", {"AAPL":0.5, "GOOG": 0.3, "AMZN": 0.2})

Use the get_portfolio_performance() method to get the performance of the portfolio at any date. Portfolio returns will be saved in the attributes index_levels and index_returns
