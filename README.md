# ragbench

RAG pipeline benchmarking toolkit with measurable retrieval quality, answer quality, and latency reporting.

## What It Does

1. Runs benchmark suites against RAG outputs.
2. Scores retrieval quality with MRR and Recall@k.
3. Scores answer quality with deterministic lexical judge baseline.
4. Produces run summaries and leaderboard-style history.
5. Ships a React dashboard for run configuration and report review.

## Stack

- Backend: Python + Flask API
- Frontend: React + Vite + TypeScript
- Persistence: SQLite (default), extensible for Postgres
- Deployment: Docker, Docker Compose, GitHub Actions, GitHub Pages

## Quick Start

```bash
cp .env.example .env
cd backend
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
pytest -q
python -m app.main
```

In a second terminal:

```bash
cd frontend
npm install
npm run build
npm run dev
```

## API and Ops Docs

- docs/API.md
- docs/DEPLOYMENT.md
- docs/OPERATIONS.md
- docs/FUTURE-CLARIFICATIONS.md

## Production Status

- Baseline API, metrics, and dashboard implemented
- Containerized backend and frontend
- CI and release workflows included
