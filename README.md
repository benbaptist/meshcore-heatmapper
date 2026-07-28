# MeshCore Heatmapper

A single-page PWA that connects to a [MeshCore](https://meshcore.co/) node over BLE, runs range tests against repeaters, and builds signal strength heatmaps — great for testing antennas and doing quick wardrives, then comparing results side-by-side.

## What it does

1. **Connect** — pairs with a MeshCore node via Web Bluetooth and pulls the contacts list.
2. **Session** — pick any repeater from your contacts to start a range test. The app rapidly pings the repeater (default 1 s interval, waiting for each ping to finish before firing the next) until you stop it.
3. **Live feedback** — a visual banner shows current state (waiting, pinging, received, timeout) along with cumulative stats and a scrollable ping log.
4. **GPS tracking** — optionally attaches precise device GPS coordinates to each ping for geospatial heatmapping.
5. **Heatmap** — renders each session as a colour-coded map (SNR or RTT) on an interactive canvas. Pan and zoom around your data.
6. **A/B comparison** — select two sessions to overlay and compare them — perfect for A/B testing different antennas on repeaters or companion devices.
7. **On-device storage** — all sessions stored locally. Sessions are timestamped, manually nameable, exportable as JSON, and re-importable.
8. **Minimal settings** — ping interval, timeout, and payload size (1/2/3 bytes).

## Use cases

- **Antenna testing** — swap antennas on a repeater or companion, run a session on each, then compare heatmaps side-by-side.
- **Wardriving** — drive around with GPS enabled and a repeater in range to map real-world coverage.
- **Node placement** — walk a site while pinging to find dead zones and optimal placement.

## How it's built

- Single `index.html` with all HTML, CSS, and JS inline — no framework, no build step.
- PWA via `manifest.json` + Service Worker (`sw.js`) for offline use and installability.
- Mobile-first responsive design with a dark UI.
- Web Bluetooth API for BLE communication with MeshCore nodes.
- Canvas 2D for heatmap rendering.
- IndexedDB for local session storage.

## Requirements

- Chrome or Edge (desktop or Android) — Web Bluetooth is required, Safari/Firefox do not support it.
- A [MeshCore](https://meshcore.co/) node within BLE range.

## License

MIT
