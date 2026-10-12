# SoundCanvas ✳

Create real-time audiovisual artwork from your microphone, music or a procedurally generated demo. No API keys, cloud services or backend needed.

## Features
- Three responsive Canvas modes: **Nebula**, **Liquid Ink**, **Pulse**
- Five palettes, four intensity controls, dark/light backgrounds
- Browser-based mic processing and audio-file playback through Web Audio API
- Built-in synthesizer demo (actual generated audio)
- PNG export in 9:16, 1:1 and 16:9
- Personal sound-signature PNG with deterministic signature identifier
- 15-second video recording using MediaRecorder (`WebM` on most supported browsers, format may vary)
- Challenge prompts, randomized styles, native share and copy-link fallback
- Mobile responsive, optional hero Persian-language toggle

## Run locally
Open `index.html` in a recent browser. For microphone permissions, use localhost (recommended):

```bash
python3 -m http.server 8000
```

Visit http://localhost:8000. When opening from file://, browser privacy restrictions may prevent microphone access.

## Deploy to GitHub Pages
1. Create a **public** GitHub repository, e.g. `SoundCanvas`.
2. Upload `index.html`, `styles.css`, `app.js`, `favicon.svg` to the root.
3. Navigate to **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then save.
4. Site will be served from `https://YOUR-USERNAME.github.io/SoundCanvas/`.

## Technical and privacy details
- Audio file data remains in browser memory and is not sent to a remote server.
- Mic works in a secure context (GitHub Pages provides HTTPS) and requires permission.
- Audio is played locally. Microphone is **not** routed to speakers to prevent feedback.
- Video captures the Canvas plus optional file/demo audio. Live microphone audio is intentionally excluded from exported videos for privacy and to prevent recording unexpected conversations; microphone still controls visuals.
- Video recording captures the canvas at its displayed aspect ratio; the aspect ratio selector governs **PNG** exports only. Some browsers (especially Safari) have limited MediaRecorder support.
- The signature identifier is a repeatable creative label based on the entered name and selected style/palette, **not a biometric voice fingerprint**.
- Visual frequency analysis is algorithmic, not a trained ML/AI model. Do not represent it as generative AI.
- Google Fonts is an optional external font resource; system-font fallbacks work without it.

Made with 🧠 by [Mobin Veisy](https://t.me/mobinmind).
