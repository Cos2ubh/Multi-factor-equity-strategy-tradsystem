📈 Real-Time Multi-Factor Algorithmic Trading System (Paper Trading)

Overview

This project implements a real-time, multi-factor algorithmic trading system in Python.
It simulates live trading (paper trading) using market data from Yahoo Finance and applies a momentum-based factor strategy with automated portfolio rebalancing.

The system is designed with modular architecture, separating data ingestion, strategy logic, portfolio management, execution simulation, and performance monitoring.

⚠️ This system is for educational and research purposes only.
No real capital is used.

✨ Key Features

Live market data ingestion using yfinance
Factor-based signal generation (momentum strategy)
Automatic portfolio rebalancing
Position and cash management
Persistent portfolio state (JSON)
Performance tracking (PnL, equity curve)
Logging for full traceability
Jupyter & script-compatible execution

🚀 What This Project Does

Fetches live and historical stock market data
Applies a momentum-based trading strategy
Automatically rebalances the portfolio
Simulates buy/sell trades (paper trading)
Tracks portfolio value and returns
Saves portfolio state and trade history

🏗️ How the System Is Structured
Data → Strategy → Portfolio → Trades → Performance

📂 Project Structure

├── trading_system.ipynb     # Main notebook
├── trading.log              # Runtime logs
├── portfolio_state.json     # Saved portfolio data
├── README.md                # Project documentation
└── requirements.txt         # Dependencies

🛠️ Tech Stack
1. Python 3.8+
2. pandas
3. numpy
4. yfinance
5. matplotlib
6. schedule
7. logging

1️⃣ Create the Trading Engine

tickers = [
    'AAPL', 'MSFT', 'GOOGL', 'AMZN',
    'META', 'TSLA', 'NVDA', 'JPM'
]

engine = LiveStrategyEngine(
    tickers=tickers,
    initial_capital=100000,
    rebalance_frequency='monthly'
)

2️⃣ Run a Trading Cycle

engine.run_trading_cycle()
This will Fetch latest prices, Calculate signals, Rebalance the portfolio (if needed), Log trades and portfolio value

3️⃣ View Performance

plot_equity_curve(engine.portfolio)
calculate_performance_metrics(engine.portfolio)

📊 Example Log Output

RUNNING TRADING CYCLE
Portfolio Value: $101,230.45 (PnL: +1.23%)
Rebalancing portfolio...
BUY 20 shares of AAPL @ $187.60
SELL 15 shares of TSLA @ $245.10
Portfolio state saved

🔮 Future Enhancements

Machine Learning–based signal generation
Risk parity or volatility targeting
Transaction cost modeling
Broker API integration (Zerodha, Alpaca)
Web dashboard (Streamlit)
Multi-asset support (ETFs, crypto)

📚 Academic Relevance

This project demonstrates:
Algorithmic trading system design
Financial data engineering
Portfolio optimization principles
Risk-adjusted performance analysis

Software architecture for quantitative systems
Suitable for:

Final-year projects
Quant research portfolios
FinTech / trading interviews

📜 Disclaimer
This software is provided as-is for learning and research.
The author is not responsible for any financial losses arising from the use of this code.
