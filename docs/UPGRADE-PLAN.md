# Upgrade plan

## Current state

**Score: 1/10.** Initial commit: README, `.gitignore`, this plan. No code,
no CI (there is nothing to check yet).

## Proposed scaffold (decision needed)

First choose the product direction from the README. Then:

- **Direction 1 (on-device bench):** Flutter or native Kotlin are the
  better fit, because on-device runtimes (TensorFlow Lite / LiteRT, ONNX
  Runtime Mobile) have first-class Android/iOS bindings there.
- **Direction 2 (ai-usage-display client):** Expo (React Native) +
  TypeScript; it only needs an HTTP client, secure token storage and charts,
  and can share response types with the `ai-usage-display` backend.

```
app/ or lib/          # screens: overview, detail, settings
src/ or lib/logic/    # pure logic (parsing, formatting) with unit tests
tests/
.github/workflows/ci.yml  # lint, typecheck/analyze, test, build
```

## Backlog

### P0
- Decide direction 1 or 2 and record it here with the stack.
- Scaffold with CI (lint, typecheck/analyze, tests, build) from day one.

### P1
- Direction 1: benchmark harness with warm-up runs and a median over N
  runs; record device model and OS version with each result.
- Direction 2: store the device token in the platform keystore
  (`expo-secure-store` or equivalent), never in plain storage or logs.

### P2
- Accessibility: charts need text equivalents; no colour-only status.

## Done in this pass (2026-09-30)
- Initial commit with an honest README (planning only), `.gitignore`, and
  this plan.
