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

## What the eval covers

The suite is organized by the type of game and the equilibrium concept being tested, not by topic. Each group probes a different strategic skill:

- **Repeated games and equilibrium selection** — can the agent sustain cooperation, punish defection, and read what its counterpart is doing over many rounds? Includes matrix games, a sports-style matching-pennies family, and multi-player commons problems.
- **Pricing and competition** — oligopoly pricing under different market structures, with entry, exit, merger, and complementarity.
- **Auctions and bargaining** — bidding under private and common values, and negotiation with incomplete information about the other side.
- **Dynamic optimization** — single-agent problems where the optimum comes from a Bellman equation: capital replacement, inventory and labor, and wage-setting under a policy shock.
- **Dynamic oligopoly and mergers** — investment, innovation, entry, and merger review in multi-period settings.
- **Contracts and information** — incentive design under moral hazard and adverse selection: contracts, monitoring, and insurance menus.
- **Supply chains** — vertical relations: wholesale pricing, ordering under uncertain demand and lead times, and the double-marginalization problem.

The full suite is built and green (531 tests passing, 2 skipped). A two-mode version (solo vs. head-to-head) is built and green too (635 tests passing, 2 skipped) but lives locally for now — see [whats-next.md](whats-next.md).

## Two-mode evaluation (built November 2026, not yet pushed)

Every module now runs in two modes: **solo** (agent vs. scripted environment) and **head-to-head** (LLM vs. LLM). Full suite: 635 tests passing, 2 skipped. This lives locally for now; pushing it is on the roadmap.

## Open design questions

- **Score normalization.** How to normalize scores across scenarios is the one open question blocking the next push.
- **Pricing module.** The design calls around the scoring gate and the head-to-head diagnostic are still open.
- **Scoring caveats, by design.** Some earlier scores are not comparable to current ones after revisions; oracles are strong references, not proven upper bounds.

## Added scope (in progress)

- **Results UI:** a simple visualization of each model's play — how play evolves in each module, how the agent is scoring, and comparisons to optimal.
- **Academic-style paper:** writing NashBench up as a paper (thesis, design, scoring, results).

See [whats-next.md](whats-next.md) for the roadmap.
