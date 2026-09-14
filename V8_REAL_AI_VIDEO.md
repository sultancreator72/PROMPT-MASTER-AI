# PROMPT MASTER AI V8 — REAL AI VIDEO CONNECTION

V8 changes the production path from a mock provider to a real Google Veo 3.1 server adapter.

## What is real in V8
- Android submits a production job to the backend.
- Android can send up to 3 reference images (product + characters) as base64.
- Backend calls Veo 3.1 using a server-only `GEMINI_API_KEY`.
- Backend polls the long-running Veo operation.
- Backend downloads the generated MP4 and exposes a protected media route.
- Android polls job status and shows the completion notification.

## Important production limitation
Veo 3.1 currently generates individual shots of 4, 6, or 8 seconds. A 30-second/1-minute/5-minute film therefore needs a render-worker pipeline that generates multiple approved shots and stitches them, with continuity checks between shots. V8 is the real single-shot foundation for that pipeline; it does not falsely claim to have a full server-side editor.

## Security
The Gemini key must exist only on the backend. Do not put it in Gradle, BuildConfig, source control, or the APK. Before public release add user authentication, per-user authorization, quotas, billing, rate limiting, persistent job storage, object storage/CDN, HTTPS, secret management, and Play Integrity.
