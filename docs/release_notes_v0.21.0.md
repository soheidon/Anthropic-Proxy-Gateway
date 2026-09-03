# Anthro Bridge v0.21.0

## Anthro-Review and Gemini 3.8 Flash Support

### What's New

#### Anthro-Review — Post-Implementation Review Gate

A new MCP tool and global Antigravity command that closes the plan → implement → **review** → commit loop.

- **`anthro-bridge/review`** MCP tool: Compares a completed implementation against the previously approved Anthro-Plan and returns a structured verdict before you commit.
- **Three-tier verdict system**: `Approved`, `Approved with recommendations`, or `Not approved` — each with a detailed rationale covering scope adherence, correctness, test coverage, edge cases, and unintended changes.
- **`/anthro-review` global command**: Install the review gate as a global Antigravity skill alongside the existing `/anthro-plan` and `/anthro-revise` commands.
- **No extra subscription cost**: The review runs through the configured external planner model, not Antigravity's subscription capacity.

**Recommended workflow:**
```
/anthro-plan → Implementation & Tests → /anthro-review → Commit
```

#### OpenRouter: Gemini 3.8 Flash

Google Gemini 3.8 Flash is now available via OpenRouter as the new default model for the built-in Gemini preset.

- **Model**: `google/gemini-3.8-flash` — 1,048,576-token context window, released 2026-09-02.
- **Pricing**: Input \$0.75 / 1M · Output \$3.75 / 1M · Cache read \$0.075 / 1M.
- **Reasoning effort**: `low`, `medium`, and `high` via the existing OpenRouter reasoning parameter.
- **Input types**: text, image, video, PDF/files, audio.
- **Updated built-in preset**: The **OpenRouter: Gemini** preset now routes:
  - Opus 5 → `google/gemini-3.8-flash` / High reasoning
  - Sonnet 5 → `google/gemini-3.8-flash` / Medium reasoning
  - Haiku 4.5 → `google/gemini-3.8-flash` / Low reasoning
- **Migration safety**: Existing custom Gemini profiles are preserved — the automatic preset migration uses exact-match comparison and will not touch profiles that have been customized.
- **Full model list via OpenRouter**: `google/gemini-3.8-flash`, `google/gemini-3.7-flash`, `google/gemini-3.5-flash-lite`, `google/gemini-3.1-pro-preview`.

---

### Installation

Download and run `Anthro Bridge_0.21.0_x64-setup.exe` from the [Releases](https://github.com/soheidon/anthro-bridge/releases/tag/v0.21.0) page.

The installer supports 8 languages (English, Japanese, Simplified Chinese, Traditional Chinese, Korean, French, German, Spanish) and preserves existing user settings during upgrades.
