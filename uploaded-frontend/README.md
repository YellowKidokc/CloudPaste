# Uploaded Frontend (Clipboard-Revival)

This folder contains your uploaded React frontend from `Clipboard-Revival.zip`, adapted to run **without Express** and deploy on **Cloudflare Pages/Workers static assets**.

## What was changed

- Kept your uploaded UI source under `client/`.
- Added standalone Vite config for client-only build.
- Added PWA support (`vite-plugin-pwa`) so it can be installed on desktop and Android.
- Added Cloudflare `wrangler.toml` for static deployment.

- Replaced binary image assets with SVG equivalents so the project can be handled in environments that do not support binary files.

## Run locally

```bash
cd uploaded-frontend
npm install
npm run dev
```

## Build

```bash
npm run build
```

## Deploy to Cloudflare Pages

Build command:

```bash
npm run build
```

Build output directory:

```text
dist
```

## PWA install

- **Desktop (Chrome/Edge):** open deployed URL and click install icon.
- **Android (Chrome):** open URL → menu → **Add to Home screen**.

## Connect to your Cloudflare backend

Your current uploaded UI is mostly local/mock state.
To connect fully with your Cloudflare backend + AI gateway, wire API calls in:

- `client/src/pages/clipboard.tsx`
- `client/src/components/settings-page.tsx`

Use your Cloudflare Worker base URL for requests.
