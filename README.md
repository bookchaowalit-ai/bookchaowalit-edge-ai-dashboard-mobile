# bookchaowalit-edge-ai-dashboard-mobile

Planned mobile dashboard for **edge AI**: AI that runs on the device (or on
small local hardware) instead of in the cloud.

## Status

**Empty / planning.** This repository has no app code yet, and the exact
product is not decided. The name and the sibling repositories suggest two
candidate directions (see below); pick one before scaffolding.

## Candidate directions

1. **On-device inference bench.** Run a few small bundled models on the
   phone (for example an image classifier and a text model) and show
   latency, throughput, memory use and whether the NPU/GPU delegate was
   used. Everything stays on the device.
2. **Local AI usage dashboard.** A phone view of the self-hosted
   [`ai-usage-display`](https://github.com/bookchaowalit-ai/ai-usage-display)
   backend (`GET /api/ai-usage`, device-token auth), which today drives an
   ESP32 screen on the local network.

Either way: no provider API keys on the phone, no prompts or personal data
collected, and "unavailable" shown honestly when a metric cannot be read.

## Related repositories

| Repository | Role |
|---|---|
| `ai-usage-display` | Local AI-usage aggregator + ESP32 display (direction 2) |
| `bookchaowalit-sentiment-analyzer-mobile` | Planned on-device text app in the same org |

## Next step

See [`docs/UPGRADE-PLAN.md`](docs/UPGRADE-PLAN.md).
