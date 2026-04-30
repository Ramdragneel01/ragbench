# API Reference

## Health

1. `GET /health` -> liveness check.
2. `GET /ready` -> readiness check with database connectivity status.
3. `GET /healthz` -> compatibility alias for liveness checks.
4. `GET /readyz` -> compatibility alias for readiness checks.

## Benchmark Runs

1. `POST /api/v1/benchmarks/run`
   - Accepts benchmark configuration and dataset cases.
   - Returns run summary with metrics.
2. `GET /api/v1/benchmarks/runs`
   - Returns recent run summaries.
3. `GET /api/v1/benchmarks/runs/{run_id}`
   - Returns single run details.

## Run Payload Shape

```json
{
  "name": "baseline-faiss-gpt4o",
  "retriever": "faiss",
  "generator": "gpt-4o-mini",
  "k": 5,
  "cases": [
    {
      "question": "What is the SLA?",
      "reference_answer": "The SLA is 99.9% uptime.",
      "retrieved_ids": ["doc-1", "doc-2"],
      "relevant_ids": ["doc-1"],
      "generated_answer": "SLA is 99.9% uptime.",
      "retrieval_latency_ms": 28,
      "generation_latency_ms": 410
    }
  ]
}
```

## Error Contract

All API errors return a normalized payload:

```json
{
  "error": {
    "code": "rate_limited",
    "message": "rate_limited",
    "request_id": "f6aafcd2-25f2-4f5e-b0f6-c7446199758f"
  }
}
```

Common status codes:

1. `400` bad request and validation failures.
2. `401` unauthorized when API key is configured and missing/invalid.
3. `413` payload too large.
4. `429` rate limited (includes `Retry-After: 60`).
