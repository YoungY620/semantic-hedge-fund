# Semantic Hedge Fund

An agent skill for semantic hedging research with prediction markets.

The core question is:

```text
Will this market or instrument make money in the states where my portfolio loses money?
```

## What It Does

This skill helps an agent turn an investment thesis into a compact hedge research report:

- interpret the user's thesis as economic exposures
- separate wanted exposure from unwanted exposure
- search for concrete assets, Polymarket markets, or Kalshi markets that may express or hedge those exposures
- score hedge fit, basis risk, settlement-rule match, timing, liquidity, and cost
- explain the sizing logic for portfolio weights
- end with a concrete holdings table

It is designed for research and decision support. It does not place trades, prepare executable orders, or integrate with a broker.

## Output Style

Reports are table-first and information dense. A portfolio-style answer should include:

| Section | Purpose |
|---|---|
| Process trace | Shows how the user thesis became exposures, scores, and weights |
| Exposure map | Separates wanted and unwanted exposures |
| Instrument selection | Explains why each asset or market was included |
| Weight calculation | Shows the sizing method and constraints |
| Candidate hedges | Lists Polymarket or Kalshi markets with direction and basis risk |
| Final concrete holdings | Gives the actual proposed holdings, target weights, and links |

## Required Final Table

Every portfolio-style report must end with a concrete holdings table:

| Holding | Type | Platform / venue | Direction token or side | Target weight | Current status | Why this instrument | Thesis linkage | Source |
|---|---|---|---|---:|---|---|---|---|
| Example asset or market | token / equity / cash / prediction market | Polymarket / Kalshi / exchange | long / short / YES / NO / cash | 0% | active / unverified / unknown | Brief reason | Link to thesis exposure | Source link |

Prediction-market rows should name the exact market question and direction token (`YES` or `NO`). If current market status, price, or liquidity has not been verified in the turn, mark it as `unverified` or `unknown`.

## Installation

Install the skill directory into your agent's skills folder:

```bash
cp -R skills/semantic-hedge-fund ~/.codex/skills/
```

For Kimi Code, the current user skills directory is typically:

```bash
cp -R skills/semantic-hedge-fund ~/.kimi-code/skills/
```

Restart the agent session after installing or updating the skill.

## Repository Layout

```text
skills/semantic-hedge-fund/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── templates.md
```

## Boundary

This skill is not financial advice and does not execute trades. It is a structured research workflow for matching portfolio bad states to assets or prediction-market payoffs.
