# NashBench — current progress

**Economics Decision Making Eval for LLMs.**

## Thesis

Firms and managers routinely find optimal outcomes in games and strategic situations without formal economic training. If LLMs are truly strategic — good enough to replace employees and write strategic documents and decisions — they should reach the same optima. NashBench tests that directly, with runnable environments and evaluations of top models, not multiple-choice questions.

## Design

Each module is a seeded, randomized environment with a generator, an ex-post solver, a runner, and a grader.

- **Runnable, not MCQA.** The agent acts, observes, and adapts under randomness in a real-world-like setting — it does not just calculate an answer.
- **Primary score: normalized reward**, `(agent − random) / (optimal − random)` per scenario, averaged. Multiple equilibria make "did you play Nash?" ill-defined as a primary score.
- **Nash / MPE / Bellman-optimal are ex-post diagnostics**, not the gate: exploitability, distance to stage-Nash, collusive gap, punishment classification, Euler errors.
- **Anti-memorization.** All values and scenarios are randomized per seed, and the code generates the Nash / optimal policy ex post for that seed.

## The 14 modules

| # | Module | Status |
|---|--------|--------|
| 1 | Repeated matrix games (2x2 / 3x3 / 4x4) — folk theorem, Green-Porter, Rotemberg-Saloner | Built (V1) |
| 2 | Sports 2x2, penalty-kick family (Chiappori-Levitt-Groseclose; Palacios-Huerta) | Built (V1) |
| 3 | Pricing: Bertrand / Cournot / Hotelling, entry, exit, merger, complements | Built (V1); design calls open (see below) |
| 4 | Auctions / procurement: first- and second-price, private/common values | Built Oct 2026 (V1.1) |
| 5 | Bargaining: Rubinstein + incomplete-values bilateral trade | Built Oct 2026 (V1.1); refinements unpushed |
| 6 | Rust bus-engine DP: capital replacement (Rust 1987) | Built Sep 2026 (V1) |
| 7 | Factory labor / inventory DP: Stokey-Lucas; Arrow-Harris-Marschak | Built Sep 2026 (V1) |
| 8 | Wage-posting + policy shock: monopsony, Card-Krueger, minimum-wage shock | Built (V1) |
| 9 | Moral hazard / incentives: Holmstrom; Shapiro-Stiglitz; Lazear-Rosen | Built Nov 2026 (V1.1) |
| 10 | Igami HDD dynamic oligopoly: innovation, entry, M&A (Igami 2017; Ericson-Pakes) | Built Sep 2026 (V1) |
| 11 | Merger scenario library: 5 scenarios (airline, MillerCoors, price leadership, target sale, DOJ review) | Built Sep 2026 (V1) |
| 12 | Insurance screening: Akerlof; Rothschild-Stiglitz; Einav-Finkelstein | Built (V1) |
| 13 | Commons / public goods, N-player (Samuelson; Hardin; Ostrom) | Built (V1) |
| 14 | Supply chain / double marginalization: Spengler; newsvendor; bullwhip | Built Nov 2026 (V1.1) |

**V1.1 is complete** (November 2026): modules #4, #5, #9, and #14 built on top of the V1 core. Full suite: 531 tests passing, 2 skipped.

## Two-mode evaluation (built November 2026, not yet pushed)

Every module now runs in two modes: **solo** (agent vs. scripted environment) and **head-to-head** (LLM vs. LLM). Full suite: 635 tests passing, 2 skipped. This lives locally for now; pushing it is on the roadmap.

## Open design questions

- **Module #5, normalization floor.** The one open question blocking the #5 push: how to normalize scores — random-vs-threshold plus a diagnostic, or random-vs-Bayesian Monte Carlo.
- **Pricing module (#3).** Two calls open since September 2026: (1) hybrid — scripted ladder stays the scoring gate, with Bertrand-only LLM-vs-LLM as a diagnostic; (2) gate on duopoly V1, plus one N-firm extension.
- **Scoring caveats, by design.** Old scores are not comparable in modules #2, #12, #8, #13-PG, #11, and #1. The #11 oracle is a strong reference, not a proven upper bound. Wage evals run ~3× (3 seeds).
- **Module #9 grading** uses ex-post *expected* profit, not realized profit — deliberate, because realized profit is noise-dominated.

## Added scope (in progress)

- **Results UI:** a simple visualization of each model's play — how play evolves in each module, how the agent is scoring, and comparisons to optimal.
- **Academic-style paper:** writing NashBench up as a paper (thesis, design, scoring, results).

See [whats-next.md](whats-next.md) for the roadmap.
