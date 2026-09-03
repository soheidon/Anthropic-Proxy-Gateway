# Anthro Bridge — Release Notes

## v0.21.2 — 2026-09-04

### Anthro-Review

- Clarified that local test execution during `/anthro-review` evidence collection is not subject to the exactly-once rule.
- Targeted tests, regression tests, full suites, package validation, reproducibility checks, RNG/deterministic-seed tests, statistical-invariance checks, and serial/parallel equivalence checks may be run iteratively as needed before review.
- The exactly-once rule continues to apply only to a successful usable `anthro-bridge/review` tool call.
- The existing single recovery retry for failed or unusable review calls remains unchanged.

## v0.21.1 — 2026-09-04

### Fixes

- Fixed the empty reasoning mode selector for Google Gemini 3.8 Flash in OpenRouter profiles.
- Added Gemini 3.8 Flash to the frontend OpenRouter model capability registry and test fixtures.
- Fixed the GUI version label so it matches the installed application version.
- Added regression coverage for Gemini 3.8 Flash reasoning options and version display consistency.

## v0.21.0 — 2026-09-03

### Anthro-Review

- **New MCP tool: `anthro-bridge/review`** — A post-implementation review gate that compares a completed implementation against the approved Anthro-Plan before commit.
- **Three-tier verdict**: `Approved`, `Approved with recommendations`, or `Not approved`, with a structured rationale for each finding.
- **Global Antigravity command: `/anthro-review`** — Installed alongside `/anthro-plan` and `/anthro-revise` as a third global skill, completing the plan → implement → review → commit workflow.
- **Coverage checklist**: The reviewer evaluates scope adherence, correctness, test coverage, edge cases, and whether any unintended files were modified.
- **Standalone MCP tool**: No Antigravity subscription capacity is consumed during the review step — the review is performed by the configured external planner model.

### OpenRouter: Gemini 3.8 Flash

- **New model: `google/gemini-3.8-flash`** — Added to the OpenRouter provider with 1,048,576-token context window.
- **Reasoning-effort support**: `low`, `medium`, and `high` levels mapped through the existing generic Gemini reasoning path.
- **Pricing**: Input $0.75 / 1M · Output $3.75 / 1M · Cache read $0.075 / 1M.
- **Built-in preset updated**: The **OpenRouter: Gemini** preset now maps Opus 5 → Gemini 3.8 Flash / High, Sonnet 5 → Gemini 3.8 Flash / Medium, Haiku 4.5 → Gemini 3.8 Flash / Low.
- **Exact-match migration safety**: The automatic migration from prior built-in Gemini defaults now uses exact-match comparison (route count, key set, `upstream_model`, `reasoning_effort`, `thinking_mode`) — custom profiles with any deviation from the historical defaults are left untouched.
- **Supported models (full list)**: `google/gemini-3.8-flash`, `google/gemini-3.7-flash`, `google/gemini-3.5-flash-lite`, `google/gemini-3.1-pro-preview`.

---

## Previous Releases

- **v0.20.0** — DeepSeek V4 Flash Vision Exp support and Weekend Off-Peak pricing (2026-08-23)
- **v0.19.0** — Antigravity MCP integration, settings sub-navigation, `/anthro-plan` and `/anthro-revise` global skills (2026-08-19)
