# Deployment Guide

## Local Container Runtime

```bash
docker compose --env-file .env -f docker-compose.yml up --build
```

## Production Container Runtime

```bash
docker compose --env-file .env -f docker-compose.prod.yml up --build -d
```

## GitHub Setup

1. Add repository variable `GHCR_IMAGE_PREFIX` if using custom image naming.
2. Set Pages source to `GitHub Actions`.
3. Push semantic tags (`vX.Y.Z`) for release pipeline.

## Secrets

1. `GITHUB_TOKEN` (default token) for GHCR push.

## Health Checks

1. `GET /health`
2. `GET /ready`

## Environment Variables

Backend:

1. `APP_ENV`
2. `RAGBENCH_HOST`
3. `RAGBENCH_PORT`
4. `RAGBENCH_ALLOWED_HOSTS`
5. `RAGBENCH_CORS_ORIGINS`
6. `RAGBENCH_ENABLE_HSTS`
7. `RAGBENCH_MAX_PAYLOAD_BYTES`
8. `RAGBENCH_RATE_LIMIT_PER_MINUTE`
9. `RAGBENCH_DB_PATH`
10. `RAGBENCH_API_KEY`

Frontend:

1. `VITE_API_BASE_URL`
