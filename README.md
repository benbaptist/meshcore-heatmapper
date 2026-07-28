# MeshCore Heatmapper

A Progressive Web App for BLE range testing and signal strength heatmap visualization with [MeshCore](https://meshcore.co/) devices.

<img src="icon-192.png" width="96" alt="MeshCore Heatmapper icon">

## Features

- **BLE Connection** — Connect to a MeshCore node via Web Bluetooth and pull contact lists directly from the device.
- **Ping Sessions** — Run automated ping tests against a contact, recording RTT (round-trip time) and SNR (signal-to-noise ratio) for each attempt.
- **GPS Tracking** — Optionally log device GPS coordinates alongside each ping for geospatial analysis.
- **Heatmap Visualization** — View session data on an interactive canvas map. Compare two sessions side-by-side (SNR or RTT overlays).
- **Session Management** — Rename, export (JSON), import, or delete sessions. Bulk export all data from Settings.
- **Offline PWA** — Installable on mobile/desktop. Works fully offline via Service Worker caching.

## How It Works

1. Open the app on a Bluetooth-capable device (Chrome/Edge on desktop or Android).
2. Tap **Connect** and pair with your MeshCore node.
3. Contacts are loaded from the node. Tap a contact to open a session.
4. Press **Start** to begin pinging. Each ping sends a raw data packet and waits for a response.
5. Data is saved per session in local storage. Switch to the **Heatmap** tab to visualize.
6. Enable **GPS** to attach location data to each ping.

## Hosting on GitHub Pages

This is a fully static site with no build step — just HTML, CSS, JS, and JSON.

### 1. Push to GitHub

```bash
cd meshcore-heatmapper
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<your-username>/meshcore-heatmapper.git
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages**.
2. Under **Branch**, select `main` and `/ (root)`, then click **Save**.
3. Wait ~30 seconds. Your site will be live at:

```
https://<your-username>.github.io/meshcore-heatmapper/
```

That's it — no CI, no build, no config needed.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app (HTML, CSS, JS bundled in one file) |
| `manifest.json` | PWA manifest for install prompts + icons |
| `sw.js` | Service Worker for offline caching |
| `icon-192.png` / `icon-512.png` | PWA icons (you'll need to provide these) |

## Requirements

- A browser with Web Bluetooth support (Chrome/Edge on desktop, Chrome on Android).
- A [MeshCore](https://meshcore.co/) node within BLE range.

## License

MIT
