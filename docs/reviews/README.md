# Dated review and evidence records

Evidence directories and dated reviews from development. The directories below hold scripts and receipts that
hard-code their own location (`docs/reviews/<dir>`, repository root as `parents[3]`), so they stay here. They
describe the retired pre-D2 pipeline and the D2 collection; they are records, not current documentation.

| Item | What it is |
|---|---|
| `d2-gap-review-2026-10-21/` | Gap review of the first D2 draft (mock/fallback diagnostics; historical only, see its README) |
| `deepseek-judge-2026-10-22/` | Judge-run receipts, retry policy and verification scripts |
| `native-benchmark-2026-10-22/` | First native collection: receipts, blind-export packets (manifest hashes verified 2026-11-28), team status |
| `native-integrity-revision-2026-10-22/` | MCP transport check used by `tests/test_real_system.py` |
| `web-ui-smoke-2026-10-22/` | Web UI smoke run |
| `embeddinggemma2_retrieval_report_2026-10-25.md` | Retrieval comparison report, linked from the root README (current) |

Review notes that were moved to `docs/historical/reviews/` (code comments and config headers still cite them under
the old `docs/reviews/` path; those files were not edited so that no run is marked stale):
`v3_failure_analysis_2026-10-24.md`, `metrics_review_2026-10-23.md`, `benchmark_quality_2026-10-23.md`,
`benchmark_human_review_2026-10-23.md`, `d2_requirements_gap_2026-10-23.md`, `public_vn_legal_benchmarks_2026-10-23.md`.
