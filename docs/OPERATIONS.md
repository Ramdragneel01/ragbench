# Operations Guide

## Service Checks

1. API liveness: `/health`
2. API readiness: `/ready`
3. API liveness alias: `/healthz`
4. API readiness alias: `/readyz`
5. Frontend availability: root route `/`

## Routine Commands

```bash
cd backend
pytest -q
python -m app.main

cd ../frontend
npm install
npm run build
```

## Incident Triage

1. If run creation fails, inspect API logs for payload validation errors.
2. If readiness fails, verify database path permissions.
3. If frontend cannot fetch API, verify `VITE_API_BASE_URL` and CORS origin.
4. If `429` responses spike, verify client retry/backoff behavior and rate-limit settings.

## Recovery

1. Restart API container.
2. Restore SQLite from backup if corruption is detected.
3. Re-run a known benchmark payload to confirm service health.
