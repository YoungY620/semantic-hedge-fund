# Hedge Fit

Hedge Fit measures whether a candidate instrument is a good hedge for a specific exposure.

The main test:

```text
Does this instrument pay when the portfolio loses money for the reason we are trying to hedge?
```

## Scorecard

### 1. Exposure Match

Does the candidate map to the unwanted exposure directly, or only to a nearby theme?

### 2. Causal Link

Is there a plausible causal path from the event to portfolio loss?

### 3. Payoff Direction

Does the candidate position make money in the bad state?

### 4. Settlement Match

Does the contract's exact settlement rule cover the risk being hedged?

### 5. Timing Match

Will the contract resolve or become liquid before, during, or after the portfolio drawdown?

### 6. Liquidity

Can the hedge be sized enough to matter?

### 7. Cost

Is the hedge premium acceptable relative to the protected loss?

### 8. Basis Risk

What are the ways the portfolio can lose while the hedge does not pay?

### 9. Scenario Coverage

Which downside scenarios are covered, partially covered, or uncovered?

### 10. Monitoring

What data tells us the hedge is becoming more or less relevant?

## Rating

Use a simple first-pass rating:

```text
Excellent: direct causal and settlement match, sufficient liquidity, clear payoff.
Good: strong causal match, manageable basis risk.
Weak: related theme, but settlement or timing mismatch.
Reject: does not pay in the relevant bad state.
```
