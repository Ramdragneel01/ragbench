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
