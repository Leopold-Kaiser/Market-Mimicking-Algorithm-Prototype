This project implements a market-mimicking framework designed to replicate the price formation process of a limit order book (LOB) by modeling the interaction of heterogeneous trading strategies.

The framework represents different trader types through a distribution of investment strategies and bid–ask quoting behaviors, each parameterized by strategy weights and bid/ask offsets relative to the last transaction price. These parameters determine how agents place orders and interact in the simulated market environment.

To calibrate the model, the algorithm employs a custom joint optimization objective that learns the trader distribution and quoting behavior that best reproduces observed market prices. The objective minimizes the squared deviation between simulated and observed closing prices while incorporating an L2 regularization term on bid–ask offsets to penalize overly aggressive quoting behavior and prevent offset-driven overfitting.

This formulation shifts the explanatory power toward changes in trader composition rather than excessive parameter tuning, effectively allowing the model to infer the latent distribution of trading strategies that drives price dynamics.

The calibrated parameters are then embedded in a forward simulation and backtesting framework, where the simulated market mechanism generates price forecasts and corresponding trading signals.

The resulting system integrates market microstructure modeling, machine-learning style parameter estimation, and algorithmic trading evaluation, providing a structural approach to understanding and forecasting market price formation.
