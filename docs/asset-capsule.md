# Asset Capsule

An Asset Capsule is the project's standard for saying "we understand this asset well enough to reason about hedging."

## Definition

```text
Asset Understanding =
Rights
+ Payoff Function
+ Risk Factors
+ Fact Dependencies
+ Information Sources
+ Hedge Map
+ Invalidation Conditions
+ Execution Constraints
```

## Required Sections

### Identity

- What is the asset?
- What type of claim is it?
- What rights does it grant?
- Does it have cash-flow, governance, redemption, collateral, settlement, or utility rights?

### Core Thesis

- What do we believe?
- What may the market be mispricing?
- What is the time horizon?

### Payoff Function

- What states make the asset gain value?
- What states make it lose value?
- Is the payoff linear, convex, capped, levered, path-dependent, or liquidation-sensitive?

### Risk Factors

Classify every meaningful exposure:

- wanted exposure
- unwanted exposure
- unknown exposure

### Fact Dependencies

List facts that must remain true for the thesis to hold.

Good dependency statements are observable:

```text
Cloud AI capex continues growing faster than depreciation drag.
```

Weak dependency statements are vague:

```text
AI has a bright future.
```

### Information Requirements

Map each exposure to information sources:

- filings
- financial statements
- protocol docs
- on-chain metrics
- governance posts
- prediction markets
- news
- expert reports
- order books

### Hedge Map

For each unwanted exposure:

- candidate hedge
- hedge direction
- expected bad state
- expected hedge payoff
- liquidity
- cost
- basis risk

### Invalidation

State what would prove the thesis wrong.

### Execution Constraints

Include:

- instrument availability
- size
- liquidity
- spread
- fees
- settlement timing
- exit condition

## Evaluation Standard

A strong Asset Capsule can answer:

```text
What do we own?
Why should it make money?
What can make it lose money?
Which risks do we want?
Which risks should we hedge?
What facts must we monitor?
What would prove us wrong?
Which hedges actually pay in our bad states?
```
