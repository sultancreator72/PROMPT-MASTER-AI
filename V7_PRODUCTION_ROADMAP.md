# PROMPT MASTER AI V7 — Production Roadmap

## Implemented
- Async production job API
- Provider adapter abstraction
- Mock provider for safe end-to-end testing
- Job polling/cancellation
- Optional bearer authentication
- Android INTERNET permission and backend URL BuildConfig
- Provider secrets remain server-side

## Next production gates
1. Replace MockVideoProvider with the selected video provider adapter.
2. Add real user authentication and per-user project ownership.
3. Store jobs/projects in PostgreSQL or equivalent durable DB.
4. Store uploaded product/character assets in private object storage with signed URLs.
5. Add rate limits, quotas, billing/entitlements and abuse controls.
6. Add webhook signature verification or provider polling worker.
7. Add Play Integrity + backend authorization for premium actions.
8. Add scene-level regeneration and final video delivery.
9. Add automated continuity/fact/rule validation before provider submission.
10. Run instrumented tests on physical Android devices before release.

## Non-negotiable consistency rule
AI may add creative detail, but it must never alter a locked product, character identity, location, object, color, costume or story element unless the user explicitly requests that change.
