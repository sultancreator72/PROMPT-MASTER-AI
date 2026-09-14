# V11 — Demo Video on Dashboard

PROMPT MASTER AI V11 adds a bundled demo video directly to the first Dashboard/Director screen.

## Demo behavior
- Embedded local MP4 asset: `app/src/main/res/raw/demo_prompt_master_ai.mp4`
- VideoView with Android MediaController playback controls
- Looping preview when prepared
- No network is required to preview the demo
- Demo is only an onboarding/example video; it is not a generated user film

## Why bundled locally?
The demo should work immediately after installation, even before a backend is configured.

## Production note
For a production app, the bundled demo can later be replaced by:
1. A remote CDN/streaming demo with caching, or
2. A user-selectable demo library.
