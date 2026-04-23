# APIMatic GitHub App Validator — No Settings Test Repo

This repo is used by the APIMatic GitHub App validator automation agent to test **auto-detection mode** (no `.apimaticsettings.json`).

## Specs

| File | Type | Expected check result |
|------|------|-----------------------|
| `specs/unified.yaml` | Valid, self-contained | APIMatic runs validation |
| `specs/invalid.yaml` | Deliberately invalid | `failure` — validation errors |
| `specs/split/main.yaml` | Valid, split (multi-file) | APIMatic runs validation |

## How tests work

The automation agent creates a branch, modifies a trigger file, opens a PR, waits for the `APIMatic OpenAPI Linter` check run to complete, and asserts the outcome.
Non-OpenAPI file changes (e.g. `README.md`) should produce a `neutral` conclusion.

<!-- agent-trigger: 2026-04-23T05:42:23.307Z -->
