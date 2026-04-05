# Interactive HTML Concepts

## 1. Allocation Strategy Puzzle
- **Tough concept addressed**: Converting messy, untagged AI spend into defensible chargeback statements.
- **Experience flow**:
  1. Start with a stacked bar chart of raw GPU costs split by provider but lacking attribution. Users input tagging/taxonomy decisions through form fields (model name scheme, owner IDs, environment flags).
  2. As decisions are submitted, a live Sankey diagram re-routes flows from infrastructure lines to business units, exposing imbalances or missing data.
  3. A variance dashboard compares pre- and post-tag allocations, highlighting fairness improvements and governance gaps.
- **Learning punchline**: Tagging strategy decisions immediately influence the narrative seen by finance and product teams.

## 2. Chargeback Impact Analyzer
- **Tough concept addressed**: The downstream effects of allocation drivers on business behavior.
- **Experience flow**:
  1. Users begin with a bland table of monthly GPU expenses. They select allocation models (usage-based, commitment amortization, experiment pools) via toggles.
  2. A dynamic waterfall chart visualizes how each driver moves dollars between teams, while callouts explain behavioral incentives (e.g., experimentation discipline, platform investment).
  3. The module ends with a "What would you recommend?" narrative summary that auto-generates based on user selections, reinforcing strategic communication.
- **Learning punchline**: Allocation mechanics are not bookkeeping choresthey shape product roadmap decisions.
