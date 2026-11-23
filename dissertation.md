# Dissertation: *Essays on the Economics of Search Algorithms*

**Kyle Monk, PhD Economics, Georgetown University, April 2024.**
Advisor: John Rust. Committee: Nathan Miller, Marius Schwartz.

The dissertation studies the economics of search algorithms deployed by platforms. It is competition-policy research: it builds measurement infrastructure for assessing algorithmic market power, tests it on real platform data, and evaluates regulatory remedies with quantified trade-offs.

## Full text (in this repo)

- [Full thesis (158 pp)](dissertation/Monk-Essays-on-the-Economics-of-Search-Algorithms.pdf)
- [Chapter 1 — A Framework for Measuring Algorithmic Search Power (28 pp, includes Appendix A)](dissertation/chapter-1-framework-for-measuring-algorithmic-search-power.pdf)
- [Chapter 2 — Effects of Algorithmic Search Power for JD.com (70 pp, includes Appendix B)](dissertation/chapter-2-algorithmic-search-power-jd-com.pdf)
- [Chapter 3 — Effects of User Data Sharing in Ecommerce (38 pp)](dissertation/chapter-3-data-sharing-in-ecommerce.pdf)

Each chapter file includes its appendix; the combined bibliography is in the full thesis. Also on file at the Georgetown repository (offline as of November 2026; the record link should resolve when it relaunches): https://repository.digital.georgetown.edu/handle/10822/1088607 — and on WorldCat, OCLC 1554737862: https://search.worldcat.org/title/1554737862
- Index words: Digital Economics, Industrial Organization, Market Power, Algorithms, Self-Preferencing, Personalized Pricing.

## Chapter 1 — A Framework for Measuring Algorithmic Search Power

**Question.** How can market power be measured for a platform whose product is a ranking algorithm — where there is no price to mark up — so that competition claims against platforms can be assessed empirically?

**Approach.** A theoretical model of search as competition over algorithms. The platform endogenously chooses how much its algorithm favors consumer preferences versus its own profitability-per-consumer, modeled as setting a distance between realized, consumer-optimal, and platform-optimal search outcomes. The key result: estimating this choice is equivalent to estimating a Nash bargaining problem between user and platform, and the bargaining parameter is a relative measure of market power, directly comparable to a price markup. A general framework is presented for applying the model across platform types (search engines, social-media feeds, ecommerce search).

**Policy orientation.** The chapter opens on live enforcement — the FTC and DOJ lawsuits against Amazon and Google, accused of leveraging market power to manipulate ranking algorithms — and fills an explicit enforcement gap: traditional market-power assessment relies on price markups, and ranking algorithms lack tangible prices. The framework is pitched as auditable with data "easily accessible to any government that's auditing a platform," and applicable to merger review. It also reframes algorithmic quality as a competition outcome: with more competition, the algorithm improves from the consumer's perspective, so a longitudinal study can reveal whether a platform's quality has degraded over time.

## Chapter 2 — Effects of Algorithmic Search Power for JD.com

**Question.** How much search market power does a dominant ecommerce platform actually exercise, and what would happen to consumers, sellers, and the platform under policies that limit self-preferencing?

**Approach.** The Chapter 1 model applied to JD.com — China's largest B2C ecommerce platform — on click and purchase records for over 2.5 million shoppers (March 2018). Two-stage structural estimation: a discrete-choice model of purchase decisions given search outcomes, then the structural search model. Counterfactual simulations of alternative power levels and of specific policies.

**Findings.** Over 97% of click outcomes in the JD data were driven by the platform's preferences and only 3% by consumer preferences. Fully realigning platform incentives with consumers would raise consumer utility per shopper 24% and, once platform participation effects are included, raise aggregate consumer surplus by 130% and seller revenue by 81%, while cutting platform profits 75% (more than doubling aggregate consumer surplus and almost doubling seller revenue — about 600 million and 90 million RMB per year).

**Policy counterfactuals, quantified.**

- **Banning first-party participation** (treating all products as third-party): +5% consumer utility, −3% seller revenue per consumer, −35% platform profit per consumer. Consumers recover about a fifth of the gain from full realignment.
- **Separating the distribution / shipping business** from ecommerce: +4% consumer utility, +2% seller revenue, −16% platform profit.
- **Banning first-party products outright:** minimal consumer gain, but >25% seller and >50% platform losses — the blunt ban is worse than the targeted participation ban.
- **Social-commerce partnerships** (e.g. Amazon's partnerships with major social platforms): no additional competitive concern from the partnerships on market-power grounds.

The chapter also notes two readings of the 97% result — genuine market power, or a suboptimal algorithm chosen via online experiments that miss the effect on total platform demand — which is itself a governance-relevant point about how platforms evaluate their own algorithms.

## Chapter 3 — Effects of User Data Sharing in Ecommerce

**Question.** When a platform has predictive data about a user, how does data sharing change welfare — and through which channel: personalized pricing, personalized steering (recommendations), or increased market power?

**Approach.** A three-stage structural model of consumer search (awareness → consideration → purchase) in which the platform's beliefs about the consumer may be wrong. The platform's ranking weights on user preferences vs. expected profits are estimated separately for users JD can identify from data vs. users it cannot, via simulated method of moments. Outcomes for identified shoppers are then simulated as if the platform had no data, and the total effect is decomposed into price discrimination, personalized steering, and market power. Same JD.com data (App vs. WeChat social-commerce channel).

**Findings.** Data sharing can benefit both consumers and the platform in aggregate, but the platform is the main beneficiary: for every data-sharing user who sees an improvement, another sees a roughly equivalent loss — while the platform sees less than a 1 percentage point decrease in sales when users withhold their data, but a greater than 30% reduction in profits. Decomposition (App): if identified users withheld data, aggregate utility would fall just 0.76%, while platform profit would fall 34.03%, seller revenue 16.67%, and market concentration (HHI) would fall 42.38%. Of the three mechanisms, **market power is the largest driver** (removing it alone: utility +1.38%, profit −20.14%); steering is net positive for consumers but mostly negated by the market-power shift; **personalized pricing alone has almost no effect** (utility +0.09%, profit −0.24%). Data sharing increases market concentration: the platform steers users toward high-margin products owned by few brands. Platforms also have a much stronger incentive to obtain data than users have to withhold it — for many demographic groups, over 70% of users achieve the exact same outcome whether they share their data or not.

**Policy orientation.** Framed against real policies — Apple's App Tracking Transparency (2021), the EU Digital Markets Act and Digital Services Act — and the finding that emphasizing commission rates in ranking is about as harmful to consumers as sharply raising the profit weight, which supports the EU's initiatives to ban self-preferencing. The core contribution reframes the policy debate: the welfare cost of data sharing runs mainly through market power, not through personalized pricing. It also makes a competition-policy argument that data accumulation itself is an entry barrier: the market for unidentified consumers can be entered by all potential entrants, but the market for identified consumers is only accessible to platforms that possess vast amounts of data.
