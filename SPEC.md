# Protocol Specification

This document formally defines the LMSR prediction market.

## State Variables

- `b` : Liquidity parameter
- `q_i` : Number of outstanding shares for outcome i
- `totalCost` : Total funds paid into the system

## Cost Function

```
C(q) = b ln( Σ exp(q_i / b) )
```

## Price Function

```
P_i = exp(q_i / b) / Σ exp(q_j / b)
```

## Trade Function

```
buy(outcome, shares)
```

Steps:

1. compute old cost
2. update share vector
3. compute new cost
4. charge difference

```
payment = C(q_new) − C(q_old)
```

## Settlement

If outcome `k` occurs:
```
payout = shares_k × 1 token
```
