# Golfman ⛳

A mobile-first progressive web app (PWA) for tracking Stableford scores on the golf course. Works offline once installed.

**Live app:** https://garrenbellew.github.io/golfman/

---

## Features

- **Find your course** — uses GPS to show nearby courses, or search by town/area name
- **Live course data** — fetches real golf courses from OpenStreetMap when online
- **Edit hole data** — correct par and stroke index per hole, saved permanently to your device
- **Stableford scoring** — enter shots per hole, get a hole-by-hole points breakdown
- **Slope/handicap adjustment** — optional slope rating adjusts your playing handicap automatically
- **Fully offline** — once installed, no internet needed on the course
- **Share course corrections** — submit corrected hole data back via GitHub Issues to help other users

---

## Installing on your phone

### Android (Chrome)
1. Open https://garrenbellew.github.io/golfman/ in Chrome
2. Tap the three-dot menu → **Add to Home screen**
3. The app installs as a standalone icon and works offline

### iPhone (Safari)
1. Open https://garrenbellew.github.io/golfman/ in Safari
2. Tap the Share button → **Add to Home Screen**
3. The app installs as a standalone icon and works offline

---

## How to use

1. **Find your course** — allow location access for automatic nearby results, or type a town/area name (e.g. "Los Alcazares, Murcia") and tap Go
2. **Fix hole data** — if par or stroke index is wrong, tap **Edit Par / Stroke Index** and enter the correct values. These are saved to your device permanently
3. **Start your round** — enter your handicap (and slope rating if known)
4. **Enter scores** — tap each hole and enter the number of shots taken
5. **Calculate** — tap Calculate Stableford for a full hole-by-hole breakdown

---

## Contributing course data

Course hole data (par and stroke index) from OpenStreetMap is often missing or incorrect. If you play a course and correct it in the app:

1. Go to **Edit Par / Stroke Index** for your course
2. Enter the correct values and tap **Save**
3. Tap **Share to help other golfers** — this opens a pre-filled GitHub Issue
4. Submit the issue and the correct data will be added to the app for all users

---

## Technical notes

- Single HTML file — no build step, no dependencies
- Course search uses [Nominatim](https://nominatim.openstreetmap.org/) (OpenStreetMap geocoding) and [Overpass API](https://overpass-api.de/) for live course data
- Hole edits are stored in `localStorage` on your device
- Service worker caches the app shell for offline use, with network-first updates so you always get the latest version
- 20 well-known courses are embedded for fully offline use; all other courses are fetched live when online
