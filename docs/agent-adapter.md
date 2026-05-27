# Agent Adapter

This repo should treat agent CLIs as interchangeable reasoning backends.

Examples:

- Codex
- Claude Code
- KimiCode
- custom local agent
- remote model runner

## Goal

Provide a thin adapter that normalizes:

- prompt input
- context files
- tool availability
- structured output expectations
- run metadata

The adapter must not own financial domain logic.

## Interface Sketch

```text
AgentRequest:
  task_kind
  instructions
  context_files
  input_payload
  output_schema

AgentResponse:
  text
  structured_output
  citations
  confidence
  missing_facts
  run_metadata
```

## Expected Agent Tasks

- create an Asset Capsule draft
- extract risk factors from documents
- summarize prediction-market settlement rules
- propose candidate hedges
- identify basis risk
- draft a research report

## Non-Agent Tasks

These should be deterministic:

- schema validation
- market data ingestion
- quote and liquidity calculation
- scoring arithmetic
- artifact storage
- audit logs
- execution checks
