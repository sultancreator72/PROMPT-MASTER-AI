# PROMPT MASTER AI — AI Virtual Film Director By @jokohudi — V6.0

Android Studio source project for an offline-first cinematic prompt/production planner.

## V6.0 production features
- 10 cinematic categories
- AMAZING MODE
- Affiliate Pro Mode: product photo/screenshot + description input
- Affiliate ad structure: HOOK → SHOWCASE/VALUE → PROOF/DEMO → CTA
- Dynamic on-screen text styles
- Product Master Lock
- Character Studio with 1–3 character slots and reference photos
- Character/Location/Object/Color/Costume/Story locks
- Duration presets + scene extension planning
- Instant replace planning for color/location/object
- Cinematic Motion, Slow Motion/Speed Ramp and Audio Engine
- Fact & Rule Check
- AI Production Studio: storyboard scenes, scene duration, action, camera, transition, approval state
- Only APPROVED scenes are marked production-ready in the master prompt
- Auto-save of the complete structured project
- JSON Backup / Recovery through Android Storage Access Framework
- Android completion notification
- R8 release hardening; no provider API secret in client

## Important architecture rule
The Android app is the client/orchestrator. For real AI/video generation, use:
Android app → secure backend → AI provider/video provider.
Never embed provider API keys in the APK.

## Build
Open the `PromptMasterAI` folder in Android Studio. The project is configured for AGP 9.4.0 / Kotlin 2.3.21 / Java 17 and Compose BOM 2026.08.00. Run Gradle Sync, then Build APK or Generate Signed Bundle/APK.

This environment did not contain a Gradle executable or a downloadable Gradle distribution, so the source could not be compiled here. Android Studio should perform the final dependency resolution and build.

## Security
R8 is enabled for release. This is not a guarantee against piracy. For production API access, combine obfuscation with backend authorization, rate limiting, Play Integrity, server-side secrets, and entitlement checks.

## Product/character consistency principle
“AI boleh kreatif, tetapi tidak boleh mengubah sesuatu yang tidak diperintahkan pengguna.”

References supplied by the user are treated as locked visual anchors. Replacement instructions apply only to the named element and preserve unrelated continuity.


## V6 Production Backend
See `backend/` for the provider-neutral asynchronous job API skeleton and `PRODUCTION_ROADMAP_V6.md` for the secure integration path. Provider API secrets must remain server-side.

## V7 Production Job Pipeline
V7 adds a provider-neutral asynchronous production API. The Android client contains a minimal `ProductionApi` contract client, while provider credentials remain server-side. The included backend uses a safe MockVideoProvider for end-to-end testing; it does not call a paid AI provider.

Recommended production topology:
`Android → HTTPS API → Auth/Quota → Job Queue → Provider Adapter → Private Storage → Status/Webhook → Android notification`
