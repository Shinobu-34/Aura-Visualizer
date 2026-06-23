# AuraCanvas - Immersive 3D Audio Visualizer & Music Player

AuraCanvas is a stunning, highly dynamic 3D audio visualizer and web-based music player. This project leverages the native Web Audio API and HTML5 Canvas to create real-time, audio-reactive visual effects that sync perfectly with your music. With a sleek glassmorphic UI, dynamic color themes, and a powerful custom backend, it offers a premium, uninterrupted listening experience.

---

## ✨ Comprehensive Feature List

### 1. Visual Render Engines (60 FPS Procedural Canvas)
Experience your music through 9 distinct, physics-based, and mathematically procedural rendering engines:
- **Mandala**: Pulsing, geometric audio-reactive rings that scale with bass and extrude with high frequencies.
- **Particle Swarm**: Chaotic particles driven by physics; bass multiplies velocity, and high transients reset particles with vibrant chaotic hues.
- **Oscilloscope Wave**: A real-time time-domain audio wave visualizer.
- **Neon Spectrum Bars**: A classic frequency-domain bar visualizer with dynamic glow.
- **Warp Drive**: A 3D starfield tunnel that accelerates with the beat (bass-driven).
- **Synthwave Grid**: A 3D retro landscape featuring a glowing horizon, sun, and an audio-distorted grid floor.
- **Audio Plexus**: An interconnected geometric node network where connection opacity and node bouncing are driven by audio energy.
- **Fractal Echo**: Rotating, recursive geometric tunnels with audio-reactive line thickness and gap pulsing.
- **Liquid Nebula**: A fluid, liquid-like particle cloud.

### 2. Studio-Grade Audio Controls
- **5-Band Graphic Equalizer**: Fully functional custom EQ (60Hz, 230Hz, 910Hz, 3.6kHz, 14kHz) with ranges from -12dB to +12dB.
- **Built-in EQ Presets**: Includes Flat, Bass Boost, Treble Boost, Acoustic, Electronic/Dance, Hip-Hop, Rock, Pop, Classical, and Spoken Word/Podcast.
- **Playback Modifiers**: Master volume, mute toggle, and extreme playback speed controls (0.1x to 8.0x).
- **Queue Management**: Loop (Single/Playlist) and true Shuffle functionality.

### 3. Dynamic Theming & Glassmorphism UI
- **Time-of-Day Adaptive Themes**: The UI's CSS variables automatically shift based on the hour (Morning Sunrise, Daylight Cyan, Sunset Pink, Night Sky Blue).
- **Custom Color Overrides**: Built-in color picker to override the time-sync and set a custom UI color scheme.
- **Glassmorphism Design**: Frosted glass effects, CSS backdrop-filters, and drop-shadows across all panels, sidebars, and control decks.
- **3D Hero Landing Page**: Features floating hyper-diamonds and asteroids rendered using CSS `preserve-3d` and custom CSS keyframes.

### 4. Input & Media Support
- **Local Audio**: Native support for dragging/dropping or uploading local `.mp3`, `.wav`, and `.ogg` files or entire folders.
- **Custom Backgrounds**: Users can upload custom images or video backgrounds (`.mp4`) to replace the default canvas background.
- **YouTube Streams**: Paste YouTube links to instantly stream audio without downloading.
- **YouTube Playlists**: Paste playlist URLs to instantly extract track titles and queue up massive playlists.
- **Predictive Pre-fetching**: The frontend intelligently 'warms up' the backend proxy before a song finishes to ensure gapless playback.

---

## 🛠️ Tech Stack

- **Frontend**: HTML5, Vanilla CSS (Custom properties, 3D transforms, Animations), Vanilla JavaScript.
- **APIs Used**: Web Audio API (AnalyserNode, BiquadFilterNode), Canvas 2D API (`requestAnimationFrame`).
- **Backend Proxy**: Node.js, Express, CORS.
- **Extraction Engine**: `youtube-dl-exec` wrapper for the `yt-dlp` binary.

---

## 🚀 Setup Instructions

To run this project locally, you need to start both the frontend interface and the backend proxy server.

### 1. Backend Proxy (For YouTube Streaming)
The backend uses `yt-dlp` to fetch audio streams. It requires Node.js.

1. Open a terminal and navigate to the `server` directory:
   ```bash
   cd server
   ```
2. Install the dependencies:
   ```bash
   npm install
   ```
3. **Important for YouTube Auth**: To prevent `403 Forbidden` errors from YouTube, export your YouTube cookies from your browser and save the file as `cookies.txt` inside the `server/` directory.
4. Start the proxy server:
   ```bash
   node server.js
   ```
   *The server will run on `http://localhost:3001`.*

### 2. Frontend Application
Because of CORS and module restrictions with the Web Audio API, it's best to serve the frontend via a local web server (like VS Code's Live Server extension).

1. Open the root directory (`Music_web`) in your code editor.
2. Serve `index.html` on a local port (e.g., `http://127.0.0.1:5500`).
3. Click "Launch Visualizer" and enjoy!

---

## 🆘 Help Needed / Known Issues

**The 'Upload Link' (YouTube Streaming) isn't working properly.**

Currently, the application attempts to use the local Node.js proxy (`server.js`) to fetch streams and metadata via `yt-dlp`. However, the 'Upload Link' feature is facing reliability issues, timeouts, and occasional fetching failures when attempting to pipe the streams to the frontend Web Audio API. 

If you are experienced with `yt-dlp`, Node.js streaming buffers, or Web Audio CORS handling, **pull requests and help are greatly appreciated to get the link uploading stable!**

---

# AuraCanvas - Immersive 3D Audio Visualizer & Music Player

**[🚀 Live Demo](https://musicappspeed1.netlify.app/)**

AuraCanvas is a stunning, highly dynamic 3D audio visualizer and web-based music player...
---

&copy; 2026 Shinobu-34. All Rights Reserved
