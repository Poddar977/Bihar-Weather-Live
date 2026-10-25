# Bihar Weather Live — web + Android-installable PWA

## Features
- District selector for all 38 Bihar districts
- Live current conditions and seven-day forecast
- Forecast-threshold alerts for rain, thunderstorms, heat, wind and UV
- Optional device location
- Responsive design and installable Progressive Web App (PWA)

## Live weather API
Uses Open-Meteo's forecast API without an API key. Forecast alerts are simple app-generated threshold notices, not official IMD alerts. Consult IMD / Bihar authorities for safety-critical warnings.

## Run locally
Browsers restrict service workers on `file://`, so run a local HTTP server:
1. Install Python 3 if needed.
2. In this folder, run: `python -m http.server 8000`
3. Open `http://localhost:8000` in your browser.

The weather API needs internet access.

## Publish the web app
Upload `index.html`, `manifest.json`, and `sw.js` to a static HTTPS host such as GitHub Pages, Netlify, or Cloudflare Pages. Keep the files in the same folder. HTTPS is needed for installation and location permissions.

## Install on Android
1. Open the deployed HTTPS URL in Chrome on Android.
2. Open Chrome's menu (⋮), then choose **Install app** or **Add to Home screen**.
3. Confirm. It opens like an app. Some Android browsers may label it differently.

## Native Android APK (optional)
This is a PWA, not a compiled APK. To package it as an Android app, use Bubblewrap (Trusted Web Activity) after publishing it on HTTPS:
1. Install Node.js and Java/Android SDK.
2. Install Bubblewrap: `npm i -g @bubblewrap/cli`
3. Run `bubblewrap init --manifest https://YOUR_DOMAIN/manifest.json`
4. Follow prompts and build with `bubblewrap build`.
You need your own domain and Digital Asset Links setup for a full-screen trusted web app.

## Notes
- Forecast values are model estimates and can change.
- Geolocation requires user permission and a secure context.
- The app does not claim to receive official government alert feeds.
