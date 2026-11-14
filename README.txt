KHWAAB AI — version 2 (PWA prototype)

Files:
- index.html: mobile-first chat interface
- manifest.webmanifest: installable PWA metadata
- sw.js: offline shell cache with network-first page refresh
- icon-192.png / icon-512.png: original sparkle app icon
- START_HERE_URDU_HINDI.txt: mobile publishing guide

Changes in this build:
- Chat history updates the same chat record instead of adding a duplicate record after every reply.
- The last 16 text turns are sent as conversation context to the AI.
- Uploaded photos are resized to JPEG for the API; only a small thumbnail is stored in local chat history.
- A storage-full fallback trims older chat turns and removes old thumbnails.
- Service worker cache versioning and navigation refresh behavior are improved.

Checks completed:
- JavaScript syntax check passed (Node.js).
- Service worker JavaScript syntax check passed.
- PWA manifest JSON parsed successfully.
- All static JavaScript element-ID references exist in the HTML.
- A full browser/device and live Gemini API test has not yet been completed.

Important limits:
- Gemini API key is stored locally in the browser and sent directly to Google. This is for private testing only; do not expose the key in a public app. A secure backend with a server-side secret is required before public launch.
- Voice depends on HTTPS, microphone permission, and Android Chrome speech-recognition support. It is turn-by-turn, not full-duplex live voice.
- Browser speech output depends on installed system voices.
- Chat history and profile are local to one browser/device; there is no cloud login or sync.
- Play Store publication is intentionally deferred until the web app works and the user has the resources for Android packaging and publishing.
