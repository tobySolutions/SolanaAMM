# Axis A/B PR Validation Report

- Generated At: 1778869599s-since-epoch
- Run ID: ab-pr-validation-1778869512
- Base Seed: 20260408-1778869512
- Repeats/Scenario: 50

## Fairness Rules

- Token universe candidates: ["wSOL", "USDC", "USDT", "JUP", "JTO", "mSOL", "bSOL"]
- Initial liquidity: ETF A/B use equal initial reserve value per active token under each scenario.
- Fee rule: ETF A/B use the same fee_bps sampled per scenario.
- Swap rule: ETF A/B use the same swap ratio and swap amount per run.
- Note: Cold-start CU is separated from steady-state CU.
- Note: Gate evaluation is environment-local and never mixed across layers.
- Note: Sampler auto-runs additional attempts (up to AB_MAX_ATTEMPT_MULT=4x) to hit target comparable N per scenario.

## Environment: LiteSVM

- Status: completed
- Note: Fast iteration environment; conclusions stay within LiteSVM layer.
- Note: A/B gate uses grouped comparison: PFDA-3 executes 3-token batch path while G3M executes 2-token path on the same active swap pair.

### Multi-Metric Gate

- Baseline: G3M
- Candidate: PFDA-3
- Gate Result: **PASS**

| Gate | Pass | Detail |
|---|---|---|
| P95 CU Gate | YES | samples_ok=true (4 scenarios >=30 comparable runs), candidate(pfda3) p95_total_cu=45270.00 vs baseline(g3m) 40699.10 (limit <= +30%) |
| P95 Latency Gate | YES | candidate(pfda3) p95 slots=11.00 (limit <= 30; ≈ batch window + buffer); reference success rates pfda/g3m = 100.00% / 100.00% |
| Quality Gate | YES | p50 slippage candidate(pfda3)/baseline(g3m) = 75.97 / 136.57 bps; compensation_via_cu=NO |
| Reliability Gate | YES | candidate(pfda3) critical invariant violations=0 (must be 0); reference: g3m violations=0, candidate tx-success=100.00% (informational — strict-mode oracle rejections by design) |
| Significance Gate | YES | N=200 comparable, sample_rule=true (4 / 4 scenarios >=30 comparable runs) | total_cu p=0.00000000029958102665261777 ci=Some([2508.599249999995, 4601.095874999996]) | slippage p=0 ci=Some([50.569779995147954, 59.25560415744336]) |

### Scenario: scenario-01

- Description: reserve=10000000 | swap_ratio=50bps | drift_ratio=800bps | fee=100bps | sampled_tokens=4
- Scenario seed: 20260408-1778869512-scenario-01
- Token sample: ["USDT", "JUP", "mSOL", "wSOL"]
- Comparison tokens: ["USDT", "JUP", "mSOL"]
- Comparable for gate: true
- Target repeats: 50
- Attempts: 50
- Comparable runs: 50

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|---|---:|---:|
| Total CU p50/p95 | 31770.00 / 43770.00 | 36194.00 / 40695.20 |
| Slippage bps p50/p95 | 100.09 / 100.17 | 149.19 / 150.08 |
| Slots-to-finality p50/p95 | 11.00 / 11.00 | 1.00 / 1.00 |
| Success rate | 100.00% | 100.00% |

Significance checks:

| Metric | Δ mean (candidate - baseline) | 95% bootstrap CI | Mann-Whitney p |
|---|---:|---|---:|
| total_cu | 3766.5600 | [1817.4640, 5565.8260] | 0.000753 |
| slippage_bps | 48.8786 | [48.6407, 49.1220] | 0.000000 |

### Scenario: scenario-02

- Description: reserve=1000000000 | swap_ratio=75bps | drift_ratio=1200bps | fee=50bps | sampled_tokens=3
- Scenario seed: 20260408-1778869512-scenario-02
- Token sample: ["wSOL", "USDC", "JUP"]
- Comparison tokens: ["wSOL", "USDC", "JUP"]
- Comparable for gate: true
- Target repeats: 50
- Attempts: 50
- Comparable runs: 50

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|---|---:|---:|
| Total CU p50/p95 | 31772.00 / 43772.55 | 35443.50 / 40705.30 |
| Slippage bps p50/p95 | 50.00 / 50.00 | 123.68 / 125.29 |
| Slots-to-finality p50/p95 | 11.00 / 11.00 | 1.00 / 1.00 |
| Success rate | 100.00% | 100.00% |

Significance checks:

| Metric | Δ mean (candidate - baseline) | 95% bootstrap CI | Mann-Whitney p |
|---|---:|---|---:|
| total_cu | 4066.6000 | [2114.9845, 5929.1205] | 0.001150 |
| slippage_bps | 73.6186 | [73.2709, 73.9670] | 0.000000 |

### Scenario: scenario-03

- Description: reserve=1000000 | swap_ratio=50bps | drift_ratio=1200bps | fee=50bps | sampled_tokens=5
- Scenario seed: 20260408-1778869512-scenario-03
- Token sample: ["JUP", "USDT", "USDC", "wSOL", "mSOL"]
- Comparison tokens: ["JUP", "USDT", "USDC"]
- Comparable for gate: true
- Target repeats: 50
- Attempts: 50
- Comparable runs: 50

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|---|---:|---:|
| Total CU p50/p95 | 31769.00 / 46769.00 | 34705.50 / 39209.65 |
| Slippage bps p50/p95 | 51.02 / 51.71 | 99.10 / 101.08 |
| Slots-to-finality p50/p95 | 11.00 / 11.00 | 1.00 / 1.00 |
| Success rate | 100.00% | 100.00% |

Significance checks:

| Metric | Δ mean (candidate - baseline) | 95% bootstrap CI | Mann-Whitney p |
|---|---:|---|---:|
| total_cu | 2630.5200 | [290.0800, 4730.5555] | 0.005615 |
| slippage_bps | 48.2154 | [47.8873, 48.5631] | 0.000000 |

### Scenario: scenario-04

- Description: reserve=10000000 | swap_ratio=50bps | drift_ratio=800bps | fee=100bps | sampled_tokens=3
- Scenario seed: 20260408-1778869512-scenario-04
- Token sample: ["USDT", "JTO", "USDC"]
- Comparison tokens: ["USDT", "JTO", "USDC"]
- Comparable for gate: true
- Target repeats: 50
- Attempts: 50
- Comparable runs: 50

| Metric | ETF A (PFDA-3) | ETF B (G3M) |
|---|---:|---:|
| Total CU p50/p95 | 31770.00 / 44595.00 | 36194.50 / 40697.65 |
| Slippage bps p50/p95 | 100.09 / 100.19 | 148.69 / 149.98 |
| Slots-to-finality p50/p95 | 11.00 / 11.00 | 1.00 / 1.00 |
| Success rate | 100.00% | 100.00% |

Significance checks:

| Metric | Δ mean (candidate - baseline) | 95% bootstrap CI | Mann-Whitney p |
|---|---:|---|---:|
| total_cu | 3949.1000 | [1789.8555, 5988.4885] | 0.002018 |
| slippage_bps | 48.5505 | [48.3145, 48.7754] | 0.000000 |

## Environment: local-validator

- Status: not_run
- Note: Run local-validator transaction-behavior benchmark separately and publish as an isolated layer.
- Note: Do not mix this layer with LiteSVM conclusions.

## Environment: devnet/mainnet-fork

- Status: not_run
- Note: Run real routing / fork validation separately and publish as an isolated layer.
- Note: Do not mix this layer with LiteSVM or local-validator conclusions.

