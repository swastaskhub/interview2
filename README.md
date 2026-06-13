# Business Hub — Interview Simulator

A single-page, Zoom-style mock interview simulator for practicing the **Email Reply Agent** role at Business Hub. Runs entirely in the browser — camera/mic preview, a "speaking" interviewer avatar with text-to-speech, a per-question timer, a chat log, and a downloadable transcript at the end.

No build step, no backend, no dependencies — just `index.html`.

## Deploy to GitHub Pages

1. Create a new GitHub repository (e.g. `business-hub-interview-sim`).
2. Upload `index.html` (and this `README.md`) to the repo root.
3. Go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
5. Save. After a minute or two your site will be live at:
   `https://<your-username>.github.io/<repo-name>/`

## Customizing

- **Questions**: edit the `QUESTIONS` array near the top of the `<script>` block in `index.html`. Each entry has a `cat` (category label) and `text` (the question).
- **Timing**: default per-question time is selectable in the lobby (60s / 90s / 120s / no limit).
- **Voice**: the interviewer reads questions aloud using the browser's built-in Speech Synthesis API — no API key needed. Users can toggle this off in the lobby.
- **Privacy**: camera/microphone streams are local-only (never uploaded) and are stopped when the interview ends.

## Browser support notes

- Camera/mic preview requires `getUserMedia` (works in all modern browsers, requires HTTPS — GitHub Pages serves over HTTPS by default).
- Text-to-speech requires `SpeechSynthesis` support (available in Chrome, Edge, Safari; voice quality varies by OS).
- If permissions are denied, the simulator still works fully — it just shows initials avatars instead of live video.
