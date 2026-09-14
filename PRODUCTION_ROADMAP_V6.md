# V6 Production Roadmap

## Implemented in project package
- V5 feature set retained.
- Version 6.0.0.
- Character web-search launch uses the system browser; no automatic scraping.
- Backend reference skeleton and API contract added.
- Provider-neutral asynchronous job model.
- Lock Manifest contract: product/characters/location/objects/story + allowed changes.
- Security rule: no provider API key in APK.

## Provider integration next
1. Create provider adapter on backend.
2. Upload/host product references securely.
3. Send approved scenes + lock manifest.
4. Poll job status.
5. Return result URL.
6. Verify output metadata and continuity where supported.
7. Notify Android: “Film/Video Anda sudah jadi, selamat menyaksikan”.

## Core invariant
AI may be creative inside the requested brief, but must not alter locked entities or make unrequested substitutions.

## Important
This package is source code/reference architecture. It is not a compiled APK/AAB and the included backend is not a production deployment.
