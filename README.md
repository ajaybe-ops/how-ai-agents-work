# How AI agents work

A 60-second, 1080×1080 brand film about how an AI agent actually operates — built as a single self-contained HTML file with three.js and the Web Audio API. No video files, no stock footage, no narration: every frame and every sound is generated in the browser.

**Watch it:** open `index.html` (or the GitHub Pages link) and it starts playing on its own. Click the frame for sound. Press **● Record** to capture the full 60 seconds and download it as `how-ai-agents-work-1080.mp4`.

## Shot list

| # | Time | Shot | On-screen text |
|---|------|------|----------------|
| 01 | 0.0–5.0 | Title | How AI agents work |
| 02 | 5.0–10.5 | Loop | An agent is a loop. |
| 03 | 10.5–16.5 | Goal | It reads the goal. |
| 04 | 16.5–22.5 | Tool | It picks a tool. |
| 05 | 22.5–28.5 | Data | The tool returns data. |
| 06 | 28.5–34.5 | Check | It checks the result. |
| 07 | 34.5–41.0 | Retry | Wrong? It tries again. |
| 08 | 41.0–47.0 | Ship | Right? It ships. |
| 09 | 47.0–53.0 | Network | Many tools. One loop. |
| 10 | 53.0–60.0 | Outro | Build your own agent. |

## How it's built

- **Visuals** — three.js scene with an orthographic overlay for text. Shots cross-dissolve with a short accent flash; text clears exactly on the cut.
- **Text** — rendered into canvas textures so it is captured by the recorder rather than sitting in the DOM.
- **Audio** — 100 BPM, 25 bars, Am–F–C–G. Pad, bass, arpeggio, kick/hat/clap and one-shot SFX, all synthesised and scheduled with a lookahead cursor. The master bus feeds both the speakers and a `MediaStreamDestination`.
- **Recording** — `canvas.captureStream(30)` plus the audio track, muxed by `MediaRecorder` to MP4 (H.264/AAC) with a WebM fallback.

## Notes

- First load needs a network connection for three.js (jsDelivr, then unpkg fallback) and the Inter webfont.
- Recording runs in real time and the tab must stay visible, otherwise the browser throttles animation.
- Palette: `#070A12` background, `#F3F6FF` ink, `#5B8CFF` accent. Typeface: Inter.
