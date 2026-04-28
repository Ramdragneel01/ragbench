# Future Clarifications

## 2026-04-28

1. Lexical overlap answer judge is a deterministic baseline and intentionally not model-based for reproducibility.
2. SQLite is default for local and low-volume workloads; Postgres adapter is planned for larger teams.
3. Case payload stores raw snapshots to support later reproducibility audits.

## Follow-up Backlog

1. Add optional LLM-as-judge adapters with provider abstraction.
2. Add percentile breakdowns by scenario tag.
3. Add benchmark artifact export to JSON and markdown report cards.
