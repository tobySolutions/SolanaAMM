# Axis A/B Test Report

- Generated: 1778869510s-since-epoch
- Environment: LiteSVM (local, multi-scenario)

## Scenario 1: Small pool, tiny swap

Reserve: 1000000, Swap: 10000, Drift trigger: 200000

- Swap amount: 10000
- Initial reserves: [1000000, 1000000]

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|--------|---------------:|------------:|
| Init CU | 0 | 15747 |
| Swap/Request CU | 6276 | 11148 |
| Clear/Rebalance CU | 10332 | 8837 |
| Claim CU | 6161 | N/A |
| **Total CU** | **22769** | **36900** |
| Tokens received | 9970 | 9803 |
| Execution slots | 11 | 1 |

## Scenario 2: Medium pool, 1% swap

Reserve: 100000000, Swap: 1000000, Drift trigger: 20000000

- Swap amount: 1000000
- Initial reserves: [100000000, 100000000]

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|--------|---------------:|------------:|
| Init CU | 0 | 11255 |
| Swap/Request CU | 16776 | 11140 |
| Clear/Rebalance CU | 20834 | 8828 |
| Claim CU | 9161 | N/A |
| **Total CU** | **46771** | **32391** |
| Tokens received | 997000 | 980296 |
| Execution slots | 11 | 1 |

## Scenario 3: Large pool, 0.5% swap

Reserve: 1000000000, Swap: 5000000, Drift trigger: 200000000

- Swap amount: 5000000
- Initial reserves: [1000000000, 1000000000]

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|--------|---------------:|------------:|
| Init CU | 0 | 15753 |
| Swap/Request CU | 12276 | 11135 |
| Clear/Rebalance CU | 14833 | 8830 |
| Claim CU | 9161 | N/A |
| **Total CU** | **36270** | **36886** |
| Tokens received | 4985000 | 4925619 |
| Execution slots | 11 | 1 |

## Scenario 4: Large pool, 1% swap

Reserve: 1000000000, Swap: 10000000, Drift trigger: 200000000

- Swap amount: 10000000
- Initial reserves: [1000000000, 1000000000]

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|--------|---------------:|------------:|
| Init CU | 0 | 12753 |
| Swap/Request CU | 9276 | 11146 |
| Clear/Rebalance CU | 14835 | 8831 |
| Claim CU | 6161 | N/A |
| **Total CU** | **30272** | **33898** |
| Tokens received | 9970000 | 9802951 |
| Execution slots | 11 | 1 |

## Summary

- Average total CU: ETF A = 34020, ETF B = 35018
- CU efficiency: ETF B uses 103% of ETF A's compute
