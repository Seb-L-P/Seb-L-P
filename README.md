## Sebastian Leeming-Price

Second-year Electrical & Electronic Engineering at Imperial College London.


### Projects

| | What it is | Stack |
|---|---|---|
| **[Low-Latency Limit Order Book](https://github.com/Seb-L-P/low-latency-order-book)** | Price-time priority matching engine: array-indexed price ladder, intrusive lists, zero hot-path allocation. Validated by differential testing against an independent `std::map` book over 20k randomised operations. 41 ns median add, 10.6M ops/sec — and one benchmark where the design honestly loses. | C++20, CMake |
| **[Backtest Validation](https://github.com/Seb-L-P/backtest-validation)** | A backtester whose real content is the validation suite: deflated Sharpe, block bootstrap, a random-entry test at matched exposure, and walk-forward that correctly reports in-sample +1.3 vs out-of-sample −2.1 on a random walk. | Python, pandas, SciPy |
| **[Options Pricing Engine](https://github.com/Seb-L-P/options-pricing-engine)** | Four independent pricers (Black-Scholes, CRR binomial, Monte Carlo, Longstaff-Schwartz) cross-validated to ~0.1%, finite-difference Greeks, and an implied-vol solver recovering the skew from a real SPY chain. | Python, NumPy |
| **[Avellaneda-Stoikov Market Maker](https://github.com/Seb-L-P/avellaneda-stoikov-market-maker)** | The 2008 optimal quoting model against a spread-matched naive baseline over tens of thousands of simulated days, extended with adverse selection and inventory caps. | Python, NumPy |
| **[Portfolio Risk Engine](https://github.com/Seb-L-P/portfolio-risk-engine)** | Four optimisers on a 20-year 8-asset universe, VaR/CVaR measured three ways, walk-forward backtests with costs, and 2008/2020 stress tests. | Python, SciPy |
| **[Blackjack Kelly Simulator](https://github.com/Seb-L-P/blackjack-kelly-simulator)** | Conditional edge by true count over millions of hands, turned into a Kelly bet ramp with risk of ruin from a block bootstrap over whole shoes. | Python, NumPy |

Also: a [real-time OpenGL renderer](https://github.com/Seb-L-P/Graphics-engine) with
shadow mapping and an editor, and an [autonomous lunar rover](https://github.com/Seb-L-P/ELEC40006-Lunar-Rover-Group-9)
built as a first-year EEE group project.

### How I try to write these up

Every README states what was measured, on what hardware, with what seed, and
how to reproduce it. Each one also has a limitations section listing the
assumptions that flatter the result. Where a result went against the design
I'd chosen, that's the part I wrote up most carefully — the order book's tail
latency and the LSM one-pass bias are both there because the interesting
number is usually the one you didn't want.
