# Context

This document is the source of truth for the repo's domain language.

## Mission

Build a system that uses AI to understand assets and portfolios, identify their risk exposures, and find prediction-market contracts or other instruments that can act as hedges.

The central question is:

```text
Will this instrument make money in the states where my portfolio loses money?
```

## Core Terms

### Asset

Any position or instrument that creates economic exposure. Examples: stocks, tokens, LP positions, vault shares, bonds, options, prediction-market shares, protocol revenue claims, or structured baskets.

### Asset Capsule

A structured representation of what an asset is, what rights it grants, how it pays off, what facts it depends on, what risks it carries, and what would prove the thesis wrong.

### Exposure

A risk factor or state variable that affects the asset's value. Exposures can be wanted, unwanted, or unknown.

### Wanted Exposure

The risk the portfolio intentionally wants to own because it expresses the investment thesis.

### Unwanted Exposure

A risk that comes bundled with the asset but is not part of the desired thesis. These are candidates for hedging.

### Semantic Hedge

A hedge whose payoff is tied to the meaning of an event or real-world state, not merely a broad price correlation.

### Condition Asset

A prediction-market position or similar instrument that pays conditional on a defined event outcome.

### Hedge Fit

The degree to which a candidate hedge pays in the specific bad states that harm the portfolio.

### Basis Risk

The mismatch between the risk being hedged and the instrument used to hedge it. For prediction markets, basis risk often comes from narrow settlement rules, ambiguous event definitions, poor timing, or weak causal linkage.

### Settlement Rule

The exact rule used to determine whether a prediction-market contract resolves YES or NO. Settlement rules are part of the hedge instrument itself, not metadata.

### Agent Adapter

A thin wrapper around an agent CLI such as Codex, Claude Code, KimiCode, or another local/remote agent runtime. The adapter should normalize requests and outputs without owning domain logic.

## System Principle

AI is used for semantic understanding, hypothesis generation, and explanation. Verification, scoring, schema validation, liquidity checks, and execution constraints should be deterministic whenever possible.
