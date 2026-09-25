# AgentLens

AgentLens is a planned observability workspace for understanding AI-agent runs: what an agent attempted, which tools it used, how long each step took, and where failures occurred.

## Product goals

- Capture structured traces for agent and tool activity.
- Make latency, errors, and token usage easy to inspect.
- Compare runs without exposing prompts, credentials, or private tool output.
- Provide a small local-first development setup before adding hosted infrastructure.

## Initial milestone

The first implementation milestone is a minimal trace model plus an ingestion API and a searchable run list. Every stored event should have a run identifier, timestamp, event type, duration, status, and explicitly redacted metadata.

## Safety boundary

AgentLens must treat prompts and tool results as sensitive by default. Raw secrets, authorization headers, environment variables, and unredacted personal data must never be persisted. New collectors should ship with tests for redaction before being enabled.

## Proposed stack

- TypeScript for shared trace models
- Node.js API for ingestion and queries
- React-based web interface
- SQLite for local development
- Automated tests and GitHub Actions

## Status

Repository initialized with a product scope and security-first implementation plan.
