# PROMPT MASTER AI — V10 Production Grade

V10 hardens the V9 production pipeline for a multi-user deployment.

## Added
- Persistent job metadata in `backend/data/jobs.json` (configurable with `STATE_FILE`).
- Bounded film queue with `MAX_CONCURRENT_FILMS` to prevent uncontrolled provider/FFmpeg concurrency.
- `/health` now reports active and queued film counts.
- State is persisted on creation, progress milestones, completion/failure and cancellation.
- Android version 10.0.0.

## Important production notes
The JSON persistence is a lightweight starter, not a substitute for PostgreSQL/Redis/object storage in a high-scale deployment. For production, migrate job state to a database, use Redis/BullMQ (or equivalent) for durable queues, and store videos in private object storage with signed URLs.

## Recommended production topology
Android → HTTPS API → Auth/Quota → Durable Queue → Worker → Veo provider → Object Storage → signed result URL → Android notification/player.

Never place provider secrets in the APK. Add TLS, user authentication, per-user quota/credits, request idempotency, audit logs, rate limits, malware/content validation, and deletion/retention policies before public launch.
