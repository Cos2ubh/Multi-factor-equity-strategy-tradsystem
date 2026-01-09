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

🧠 Strategy Logic (High Level)
Factor Used

3-Month Momentum

Stocks are ranked by past returns

Position Rules

Top 20% → Long positions

Bottom 20% → Short positions

Neutral stocks → No position

Rebalancing

Configurable frequency:

Daily

Weekly

Monthly

🏗️ System Architecture
├── LiveDataManager
│   ├── Fetches live prices
│   └── Fetches historical data
│
├── Strategy Engine
│   ├── Calculates factor signals
│   └── Determines target weights
│
├── Portfolio Manager
│   ├── Tracks cash & positions
│   ├── Executes simulated trades
│   └── Stores trade history
│
├── Execution Layer
│   └── Paper trade simulation
│
├── Monitoring
│   ├── Logs
│   └── Performance metrics

📂 Project Structure
.
├── trading_system.ipynb      # Main Jupyter notebook
├── trading.log               # Runtime logs
├── portfolio_state.json      # Saved portfolio state
├── README.md                 # Project documentation
└── requirements.txt          # Dependencies

🔧 Tech Stack

Python 3.8+

pandas

numpy

yfinance

matplotlib

schedule

logging

▶️ Example Usage
Initialize the Trading Engine
tickers = [
    'AAPL', 'MSFT', 'GOOGL', 'AMZN',
    'META', 'TSLA', 'NVDA', 'JPM'
]

engine = LiveStrategyEngine(
    tickers=tickers,
    initial_capital=100000,
    rebalance_frequency='monthly'
)

Run a Single Trading Cycle (Jupyter Safe)
engine.run_trading_cycle()


This will:

Fetch latest prices

Evaluate rebalancing conditions

Generate signals

Execute simulated trades

Save portfolio state

Visualize Portfolio Performance
plot_equity_curve(engine.portfolio)

Calculate Performance Metrics
calculate_performance_metrics(engine.portfolio)


Outputs:

Total Return

CAGR

Sharpe Ratio

Maximum Drawdown

📊 Sample Output (Logs)
RUNNING TRADING CYCLE
Portfolio Value: $101,245.30 (PnL: +1.24%)
Rebalancing portfolio...
BUY 15 shares of AAPL @ $189.45
SELL 10 shares of TSLA @ $243.20
Portfolio state saved

📈 Performance Metrics Explained
Metric	Description
Total Return	Net portfolio gain
CAGR	Annualized return
Sharpe Ratio	Risk-adjusted return
Max Drawdown	Worst peak-to-trough loss
⚠️ Assumptions & Limitations

No transaction costs or slippage

Yahoo Finance data latency

No corporate action adjustments in real-time

Short selling simulated without margin constraints

Market hours depend on exchange timezone

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
