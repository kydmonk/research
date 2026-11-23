# What's next

A working draft — roadmap for NashBench and for the dissertation papers. Expect this to move.

## NashBench

**Near term**

- **Push the two-mode eval.** Solo + head-to-head evaluation for the whole suite is built and green (635 tests passing, 2 skipped) but still local-only. Push it to the repo.
- **Resolve the normalization question.** The sole blocker on the next push: how scores are normalized across scenarios. Then push the remaining module refinements.
- **Settle the pricing-module design calls.** Around the scoring gate and the head-to-head diagnostic.

**Then**

- **Results UI vs. academic paper.** Both are scoped; the sequencing is the open call. The UI visualizes each model's play — the evolution of play in each module, how the agent is scoring, comparisons to optimal. The paper writes NashBench up as an academic-style piece (thesis, design, scoring, results).
- **Post-training plan** (`TRAINING.md` in the repo, not started): train on the generator, hold out seeds / regions / modules.
- **Score-stakes.** One module's score is display-only today; it needs payoff-relevant stakes or an explicit decision to accept it as display.
- **Speed objective.** After the normalization question: keep gains as the gate, or add a speed-weighted secondary metric.

## Dissertation papers — future edits

Each dissertation chapter is a standalone paper in waiting. The edits below are drawn from the chapters' own discussion sections and open threads — drafts, not decisions.

**Paper 1 — A Framework for Measuring Algorithmic Search Power**

- Connect the search-power parameter to demand elasticity, which would enable analysis of mergers and entry-exit decisions with the framework.
- Longitudinal application: track the parameter over time for a single platform to test whether algorithmic quality has degraded — the parameter reads as a dimension of algorithmic quality for consumers.
- Generalize the estimation beyond ecommerce search (search engines, social-media feeds) — the framework is built for that, the applications are not yet written.

**Paper 2 — Effects of Algorithmic Search Power for JD.com**

- Dig into the mechanisms affecting the elasticity of platform participation — that is what determines how far the model extends to other settings, including proposed mergers.
- Separate the two readings of the headline result (tremendous market power vs. a suboptimal ranking algorithm chosen by online experiments that miss total-demand effects) — the governance implication differs.
- The policy counterfactuals are the paper's core: the first-party-participation ban (+5% consumer utility) vs. the blunt product ban vs. distribution separation. Sharpen the comparison into the paper's central policy argument.

**Paper 3 — Effects of User Data Sharing in Ecommerce**

- Extend the decomposition beyond JD.com's App vs. WeChat channels: does the market-power channel dominate on other platforms and in other data regimes, or is it specific to this setting?
- The data-as-entry-barrier argument is stated but not fully developed — build it out as the paper's competition-policy contribution.
- Connect explicitly to the EU self-preferencing bans and to data-access rules: the finding that commission-weighted ranking is about as harmful as a sharply higher profit weight is the evidence base, and it deserves a sharper statement.

**Across all three**

- Unify the framing: the three papers are one argument — platforms' ranking and data choices are measurable exercises of market power, and the measurement exists to be used by regulators. The dissertation's general framework (Paper 1) plus two empirical demonstrations (Papers 2 and 3) should read as a single research program, not three separate exercises.
