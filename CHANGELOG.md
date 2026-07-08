# Changelog — Mamut2026 TDVRPTW BKS

All notable changes to the `Mamut2026` TDVRPTW instances and best-known solutions (BKS) are recorded here. Objective: **Duration** (duration minimization — the depot departure time of each route is a decision variable). Costs are the authoritative output of the canonical checker (`mamut_routing_lib.td.check_td_solution`): exact IEEE-754 double arithmetic, no epsilon thresholds, routes in canonical order (sorted by first customer), total summed in that order — so any strict improvement is real.

## 2026-07-08 — family created

- 360 instances published: 5 cities (Lyon, Paris, San-Francisco, Hong-Kong, Tokyo) × 6 sizes (n ∈ {10, 25, 50, 100, 500, 1000}) × 2 traffic models (`bpr`, `wave`) × 3 intensities (light, moderate, heavy) × 2 customer-sampling methods (`poi`, `hyb`).
- Generated with `mamut-routing-lib` 0.5.0 (`road-graph` td model, materialization tolerance 1.0 s for n ≤ 100, 2.0 s for n ≥ 500). Every instance was sha-verified at build time (`graph_sha256` + `atf_sha256` full-load check), and byte-identical regeneration was confirmed on a sample of cells rebuilt on a second, independent machine.
- No best-known solutions yet; `.bks.Duration.json` sidecars will follow in a dedicated seeding campaign.

## 2026-07-08 — initial n=10 BKS seed

- First `Duration` BKS published for all 60 n=10 instances: kayros 0.4.0 TD-ILS (seed 42, 30 s), costs validated by the canonical TD checker. Larger sizes remain without BKS until the dedicated seeding campaign.
