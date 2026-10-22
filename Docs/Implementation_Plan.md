# AI Campaign Investigator — Implementation Plan

## Goal

Deliver a local Docker Compose MVP for evidence-backed loyalty-campaign investigations using FastAPI, React/Vite, PostgreSQL/pgvector, and provider-neutral OpenAI and Google Gemini integrations.

## Architecture

- FastAPI backend exposes demo authentication, scenarios, investigations, and evaluation APIs.
- PostgreSQL/pgvector stores canonical campaign metrics, synthetic marketing knowledge, investigation traces, and evaluation results.
- The agent uses typed, read-only tools only: campaign metrics, segment changes, exposure/response analysis, and knowledge retrieval.
- A provider interface supports OpenAI and Google Gemini without automatic cross-provider fallback.
- React UI presents demo login, scenario/question input, evidence, trace, analysis, uncertainty, and evaluation results.

## Delivery sequence

1. Create Docker, environment, backend, frontend, and test foundations.
2. Add canonical data model, temporal replay filter, seeded demo corpus, and dunnhumby ingestion entrypoint.
3. Implement controlled analytical tools, RAG-style knowledge retrieval, provider adapters, and auditable orchestration.
4. Expose APIs and focused web UI.
5. Add deterministic, ML/statistical, and agent evaluation paths with metrics and a human rubric.
6. Validate with unit/integration tests, including replay leakage, guardrails, provider failure, and end-to-end flows.

## Acceptance criteria

- `docker compose up --build` launches database, API, and UI.
- A demo user can authenticate, submit a question, and inspect trace, evidence, hypotheses, recommendations, and caveats.
- The agent cannot issue arbitrary SQL or writes and cannot access future replay data.
- OpenAI and Google are independently configurable; provider failures are visible and recorded.
- Evaluation compares deterministic, statistical/ML, and agent approaches for fixed scenarios and records quality, latency, and token/cost metrics.

## Defaults

- Local-only deployment, one configurable demo account, and locally supplied licensed dunnhumby data.
- Curated, fact-validated synthetic documents for initial scenarios.
- Raw datasets, secrets, caches, and generated build outputs are excluded from Git.
