# Semantic Hedge Fund

Semantic Hedge Fund is an AI-native research system for using prediction markets as hedging instruments.

The core idea is not to ask an AI to predict prices. The system should use AI language understanding to understand assets, decompose their exposures, identify what needs hedging, and search diverse prediction-market contracts for instruments that may pay when the portfolio loses money.

## Thesis

Prediction markets such as Polymarket can be treated as semantic hedging instruments: condition assets whose payoff is tied to real-world events, policies, rulings, failures, launches, elections, conflicts, protocol incidents, or other states of the world.

Traditional hedges often cover broad price factors: index beta, rates, FX, commodities, credit, or volatility. Prediction markets can potentially hedge event risk that is hard to express with standard financial instruments.

## Workflow

1. Understand the asset.
2. Decompose its wanted and unwanted exposures.
3. Search for candidate hedges across prediction markets and traditional instruments.
4. Evaluate basis risk, settlement-rule mismatch, cost, liquidity, and timing.
5. Verify whether the hedge would plausibly pay in the scenarios where the portfolio loses money.
6. Record the reasoning, facts, assumptions, and invalidation conditions.

## First Principles

- Exposure first, instrument second.
- A hedge is useful only if it pays in the bad states it is meant to cover.
- Textual similarity is not enough; settlement rules and causal linkage matter.
- AI proposes and explains candidate mappings; deterministic checkers score facts, rules, liquidity, and execution constraints.
- Agent CLI backends are implementation details behind a thin adapter.

## Repo Map

- [CONTEXT.md](CONTEXT.md): bounded-context glossary and core domain language.
- [docs/architecture.md](docs/architecture.md): system architecture and module boundaries.
- [docs/asset-capsule.md](docs/asset-capsule.md): standard representation for understanding an asset.
- [docs/hedge-fit.md](docs/hedge-fit.md): criteria for judging whether a prediction-market contract is a good hedge.
- [docs/agent-adapter.md](docs/agent-adapter.md): thin adapter model for Codex, Claude Code, KimiCode, or other agent CLIs.
- [docs/research-agenda.md](docs/research-agenda.md): empirical research questions.
- [schemas/asset-capsule.schema.json](schemas/asset-capsule.schema.json): initial machine-readable capsule schema.
- [schemas/hedge-candidate.schema.json](schemas/hedge-candidate.schema.json): initial machine-readable hedge schema.
- [examples/ai-sector-asset-capsule.md](examples/ai-sector-asset-capsule.md): example for an AI-sector portfolio.

## Non-Goals For The First Version

- Do not build an autonomous trading fund.
- Do not let an LLM directly trade from free-form reasoning.
- Do not optimize for a specific agent CLI.
- Do not treat prediction markets as generic alpha signals before validating hedge fit.

## MVP

The first MVP should produce a research report, not trades:

```text
Input:
- Portfolio or asset thesis
- Available prediction-market contracts
- Optional traditional hedge instruments

Output:
- Asset Capsule
- Unwanted exposure list
- Candidate hedge contracts
- Hedge-fit scorecard
- Basis-risk notes
- Missing facts and follow-up research tasks
```
