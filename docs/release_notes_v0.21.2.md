# Anthro Bridge v0.21.2

## Anthro-Review: Iterative Test Evidence Collection

This patch clarifies the `/anthro-review` workflow for projects that require repeated validation during review.

Local test execution is now explicitly documented as repeatable and independent from the exactly-once review-call rule.

Review evidence may include iterative:

- targeted and regression tests
- full test suites
- package/build validation
- reproducibility and deterministic-seed checks
- statistical-invariance checks
- serial/parallel equivalence checks

The exactly-once rule still applies to the final usable `anthro-bridge/review` call. A failed or unusable review call still permits at most one recovery retry.

No MCP protocol, review schema, provider behavior, or Gateway behavior has changed.
