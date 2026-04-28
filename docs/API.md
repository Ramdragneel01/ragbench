# API Reference

## Health

1. `GET /health` -> liveness check.
2. `GET /ready` -> readiness check with database connectivity status.

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
