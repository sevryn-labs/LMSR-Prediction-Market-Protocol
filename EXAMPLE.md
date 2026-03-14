# Example Walkthrough: A Live Prediction Market

This example demonstrates the lifecycle of a prediction market for the question: **"Will it rain in London on June 1st?"**

## 1. Market Creation
An administrator deploys the contract with the following parameters:
- **Outcomes**: 2 ([0] Yes, [1] No)
- **Liquidity ($b$)**: 1000 DUST

### Initial State
- **Shares Outstanding**: $q = [0, 0]$
- **Initial Cost**: $C(0, 0) = 1000 \cdot \ln(1 + 1) \approx 693$ DUST
- **Initial Prices**:
  - Outcome 0 (Yes): $\frac{\exp(0)}{\exp(0)+\exp(0)} = 0.50$ (50%)
  - Outcome 1 (No): $\frac{\exp(0)}{\exp(0)+\exp(0)} = 0.50$ (50%)

## 2. Trader A enters the market
Trader A has weather data suggesting a 75% chance of rain. 
- **Action**: Trader A uses the **Target Price Trade** feature to move the price to **0.75**.
- **Calculation**: To reach $P=0.75$ with $b=1000$, the required shares are:
  $$\Delta q_0 = 1000 \cdot \ln(0.75 / 0.25) \approx 1098 \text{ shares}$$
- **Cost**: $C(1098, 0) - C(0, 0) \approx 1313 - 693 = 620$ DUST.

## 3. Current Market State
- **New Prices**: Yes: 75.0% | No: 25.0%
- **Shares**: $q = [1098, 0]$
- **Volume**: 620 DUST paid.

## 4. Trader B disagrees
Trader B is a skeptic and believes the chance is only 60%.
- **Action**: Trader B buys shares of **Outcome 1 (No)** to drive the Yes price down.
- **Result**: The market moves toward a new equilibrium between 60% and 75%, effectively aggregating both viewpoints.

## 5. Market Settlement
On June 2nd, the market is resolved.
- **Result**: It rained (Outcome 0 wins).
- **Payout**: Holders of outcome 0 shares can redeem their shares for 1 DUST each (the settlement value of a winning share). Holders of outcome 1 shares receive 0.
