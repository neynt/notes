## Chapter 1

- Equity/stock/share: Small bit of company
- Dividend: Money given to people with equity
  - cum: Stock comes with next dividend
  - ex: Stock does NOT come with next dividend
- Commodity: Raw products
- Currency: Also a thing that is traded
  - Every pair has an exchange rate
  - Market called foreign exchange (forex / FX)
- Index: Fund made up of basket
  - Basket: The underlying stocks
- Fixed-income security: like, CDs
- Inflation-proof bonds
- Forward contract: "I will buy X from Y for $P at time D"
  - D: Delivery date / Maturity
  - P: Delivery price
- Futures contract: Forward contract, but with daily "marking to market"
  - Margin: Account for marking to market

## Chapter 4

- 4.3. Markov property: No memory beyond the present.
- 4.4. Martingale property: E[Si|Sj] = Sj, j < i
- 4.5. Quadratic variation is sum of squares of differences of adjacent values.
- 4.6. Brownian motion is a finite continuous random walk.
  - It is Markov and Martingale.
  - Its quadratic variation from time 0 to t → t.
  - Normality: X(ti) - X(ti-1) is N(0, ti - ti-1).
- 4.7. Stochastic integration
  - integral from 0 to t of f(τ)dX(τ), where X is Brownian motion, is
    - lim n→∞ of sum j=1 to n of f(t(j-1))(X(t(j)) - X(t(j-1)))
    - where t(j) = jt/n.
    - i.e. The limit as n→∞ of the weighted average of f evaluated at n
      evenly-spaced time steps, where the weight is the change of Brownian
      motion over that time step.
- 4.8. Stochastic differential equations
  - Write dW = g(t)dt + f(t) dX. This basically means:
    - d Thing = Deterministic dt + Random dX.
- 4.9. Mean square limit
  - ∫ 0→t of (dX)² = t
- 4.10. Functions of stochastic variables and Itô's lemma
  - dF = dF/dX dX + ½ d²F/dX² dt
  - Example: If X: Brownian motion and F = X², then dF ≠ 2XdX; by Itô's, dF = 2XdX + dt.
- 4.11. Interpretation of Itô's lemma
  - A stock is modelled by dS = μSdt + σSdX. An option's value V(S,t) may be
    modelled similarly, as dV = __ dt + __ dX.
- 4.12. Itô and Taylor
  - As a rule of thumb, you can use Taylor series expand F and use dX² = dt.
    This is wrong but works most of the time.
  - Some intuition involving adding N normal variates, then the squares of
    those normal variates.
  - Some generalization:
    - Suppose dS = a(S)dt + b(S)dX.
    - Then, for V(S), we have dV = dV/dS dS + ½ b² d²V/dS² dt.
- 4.13. Itô in higher dimensions
  - Option to buy the more valuable of Nike and Reebok
  - I have no idea what happened here but it seems cool.
- 4.14. Examples
  - 1. Brownian motion with drift: dS = µdt + σdX
  - 2. Lognormal random walk: dS = µSdt + σSdX
    - If you examine F(S) = log S, we get dF = (µ - ½σ²)dt + σdX.
  - 3. Mean-reverting random walk: dS = (ν-μS)dt + σdX
  - 4. Another one: dr = (ν-µr)dt + σr^(1/2)dX
    - Cox, Ingersoll & Ross model for short-term interest rate.
