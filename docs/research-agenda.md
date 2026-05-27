# Research Agenda

## Core Question

Can AI language understanding and diverse prediction-market contracts be combined into a practical hedging system?

## Research Questions

### 1. Asset Understanding

Can an agent reliably decompose an asset into rights, payoff drivers, risk factors, fact dependencies, and unwanted exposures?

### 2. Hedge Discovery

Can semantic search and agent reasoning find prediction-market contracts that map to those unwanted exposures?

### 3. Hedge Fit

Can the system reject superficially related markets whose settlement rules do not actually hedge the risk?

### 4. Basis Risk

Can basis risk be made explicit enough for human review?

### 5. Empirical Validation

For historical portfolios and resolved markets:

- Did candidate hedges pay in relevant bad states?
- Did they resolve too late?
- Were they liquid enough to matter?
- Did spreads and fees destroy usefulness?
- Did settlement rules create unexpected mismatch?

### 6. Practical Use

Can the system help a human portfolio manager answer:

```text
What risks do I unintentionally own, and what can I buy that pays if those risks materialize?
```

## First Case Studies

- AI-sector portfolio hedged with AI regulation, export control, Taiwan risk, power-grid, and model-commoditization markets.
- ETH/DeFi portfolio hedged with protocol, stablecoin, regulation, hack, and L2 outage markets.
- BTC/miner portfolio hedged with energy, regulation, ETF flow, and mining-policy markets.
