# Browser Audio Separator

A browser-first audio separation tool. Audio files should be processed locally on the visitor's device; this project must not upload user audio to a third-party separation API.

## Current status

- [x] Public repository created
- [x] Confirmed the selected upstream project and inspected its current source
- [ ] Integrate a verified client-side inference engine
- [ ] Verify model-weight and training-data licensing for commercial use
- [ ] Test on Android Chrome (memory, processing time, downloads)
- [ ] Deploy with GitHub Pages
- [ ] Validate demand before adding monetization

## Important upstream finding

The current `joverval/sdemux` application source uses a remote API at `https://sdemux.joverval.cl/api`. It is **not** safe to copy that current application as a zero-cost, client-only implementation. Its repository also contains a browser-side Demucs loader, which needs separate integration and testing.

Upstream reference: https://github.com/joverval/sdemux

## Product constraints

1. Static hosting; no paid backend.
2. Audio remains on-device; no upload endpoint.
3. Model is downloaded on demand and cached locally where possible.
4. Clear limits and memory warnings for mobile devices.
5. No claim of commercial readiness until model and dataset rights are checked.
6. Never display a successful result unless real inference completed.

## Development

The initial page is a static upload and preview shell. Separation must remain unavailable until the client-side model integration is complete and tested.

No analytics, tracking scripts, external audio APIs, or server-side processing are included.
