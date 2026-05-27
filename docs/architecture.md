# Architecture

## High-Level Pipeline

```text
Portfolio / Asset Thesis
        |
        v
Asset Understanding
        |
        v
Exposure Decomposition
        |
        v
Hedge Discovery
        |
        v
Hedge-Fit Verification
        |
        v
Research Report / Human Review
```

## Modules

### Asset Understanding

Inputs:

- Asset name or portfolio description
- Position size and time horizon
- Financial data
- On-chain data
- News, filings, docs, governance posts, protocol docs

Output:

- Asset Capsule

### Exposure Decomposition

Separates:

- wanted exposures
- unwanted exposures
- unknown exposures
- missing facts

The key output is a list of risks that may need hedging.

### Market Ingestion

Collects prediction-market contracts and metadata.

For Polymarket-like markets, the system should preserve:

- market question
- outcome tokens
- resolution source
- settlement rule
- category and tags
- expiry or resolution time
- bid/ask/mid
- liquidity and spread
- order book depth when available

### Hedge Discovery

Uses semantic search and agent reasoning to map unwanted exposures to candidate instruments.

Examples:

- AI regulation exposure -> AI regulation event contracts
- Taiwan supply-chain exposure -> Taiwan conflict or semiconductor disruption contracts
- Stablecoin exposure -> depeg or issuer-risk contracts
- Protocol exposure -> hack, outage, governance, TVL, or launch-failure contracts

### Hedge-Fit Verification

Scores candidates using:

- causal relevance
- settlement-rule match
- timing match
- payoff direction
- liquidity
- cost
- basis risk
- scenario coverage
- explainability

### Report Generation

Produces a human-readable report with:

- portfolio thesis
- asset capsule
- exposure map
- candidate hedges
- rejected hedges and why
- missing facts
- invalidation conditions
- next research actions

## Agent Boundary

Agent CLIs are replaceable backends. They should not define the domain model.

The domain system should call an agent for tasks such as:

- extract asset risks from documents
- summarize settlement rules
- propose causal links
- explain basis risk
- draft a research report

The deterministic system should own:

- schema validation
- market data storage
- scoring rubrics
- price/liquidity checks
- audit logs
- report manifests
