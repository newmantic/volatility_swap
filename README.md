# volatility_swap


A Volatility Swap is a financial derivative that allows an investor to speculate on or hedge against future volatility of an underlying asset. Unlike options, where the payoff depends on the direction of the asset price, volatility swaps are purely based on the magnitude of price movements, regardless of direction. The payoff of a volatility swap is determined by the difference between the realized volatility of the underlying asset and a pre-agreed strike volatility.


Underlying Asset (S): The asset whose volatility is being traded (e.g., a stock, index).
Strike Volatility (K_vol): The fixed level of volatility agreed upon at the inception of the swap.
Realized Volatility (sigma_realized): The actual volatility of the underlying asset observed over the life of the swap.
Notional Amount (N): The dollar amount per volatility point. This scales the payoff of the swap.
Maturity (T): The time until the swap expires.



Log Returns: Volatility is typically measured using the log returns of the underlying asset's price. The log return from time t to t+1 is given by:
R_t = ln(S_{t+1} / S_t)
Where:
R_t is the log return at time t.
S_t is the price of the underlying asset at time t.

Realized Volatility (sigma_realized): Realized volatility is calculated as the standard deviation of the log returns over the life of the swap. It can be annualized by multiplying by the square root of the number of trading days in a year (commonly 252 days):
sigma_realized = sqrt((1/n) * sum_{t=1}^{n} (R_t - R_avg)^2) * sqrt(252)
Where:
n is the number of time intervals (e.g., daily returns).
R_avg is the average log return over the period.

Volatility Swap Payoff: The payoff of the volatility swap at maturity is the notional amount multiplied by the difference between the realized volatility and the strike volatility:
Payoff = N * (sigma_realized - K_vol)
Where:
N is the notional amount.
sigma_realized is the realized volatility.
K_vol is the strike volatility.

If sigma_realized > K_vol, the payoff is positive, benefiting the holder of the swap. Conversely, if sigma_realized < K_vol, the payoff is negative, and the holder would incur a loss.
