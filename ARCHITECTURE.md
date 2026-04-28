# ragbench Architecture

## Overview

ragbench evaluates RAG quality with reproducible run inputs and explicit metrics.

## Runtime Topology

1. Backend API service
   - Accepts benchmark run payloads
   - Computes retrieval and answer metrics
   - Persists run summaries and raw payload snapshots
2. Frontend dashboard
   - Submits benchmark payloads
   - Displays latest run summary and history table
3. SQLite storage
   - Stores benchmark runs for local and small-team deployment

## Data Flow

1. Client submits benchmark payload with run config and dataset cases.
2. Service validates payload shape and computes per-case metrics.
3. Service aggregates metrics into run-level summary.
4. Run summary and payload are persisted in SQLite.
5. API returns run response; UI renders report and leaderboard.

## Security Controls

1. Host allowlist enforcement.
2. Request payload size guard.
3. Optional HSTS response header in production.
4. Input validation and safe default thresholds.

## Scalability Path

1. Replace SQLite with Postgres by abstracting store methods.
2. Add background worker queue for large benchmark suites.
3. Add object storage for detailed case-level artifacts.
