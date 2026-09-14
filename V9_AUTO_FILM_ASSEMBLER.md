# PROMPT MASTER AI V9 — AUTO FILM ASSEMBLER

V9 upgrades production from a single Veo shot to a multi-scene film pipeline.

## Pipeline
Android → /v1/films → approved scene jobs → Veo 3.1 → per-scene MP4 → FFmpeg assembly → final MP4 → Android notification.

## Continuity
Every scene receives the same lock manifest and an explicit continuity contract. The backend rejects unapproved scenes and validates Veo-compatible durations (4/6/8 seconds).

## Assembly
FFmpeg concatenates completed scene files and re-encodes to H.264/AAC with faststart for broad playback compatibility.

## Production notes
The current backend keeps jobs in memory. For public deployment, add a persistent queue/database, object storage/CDN, user authentication, quotas/billing, retries, cleanup policies, monitoring, and HTTPS.

## Important
This is a real multi-shot assembler when a server has FFmpeg and a valid GEMINI_API_KEY. Provider usage can incur charges.
