# LMSR Market Mechanism

The Logarithmic Market Scoring Rule acts as an automated market maker.

Instead of relying on liquidity providers, the system uses a convex cost function.

## Convex Market Maker

The LMSR cost function is convex.

This ensures:

- prices remain between 0 and 1
- no arbitrage
- bounded loss

## Information Trading

Participants effectively sell information to the market.

If they believe the market is wrong, they trade to correct it.

## Relation to Information Theory

Trading in LMSR markets can be interpreted as minimizing KL divergence between probability distributions.

This makes LMSR a powerful mechanism for collective decision making.
