![Tap to Build](images/website_logo.png)

# Tap to Build

<img src="assets/output.gif" width="600">

Tap to Build is a browser-based experience for assembling small business landing pages. Users move through signup/login, profile capture, branding (palette + logo), content editing, real-time preview, and final export. The backend is a lightweight Express API that stores users and submitted site configurations as JSON.

## Final Result
<img src="assets/output2.gif" width="600">

## Features
- Multi-step builder: profile setup, app setup, palette selection, logo creation/upload, content editing, live build preview, final preview
- Local auth API with bcrypt hashing plus hosted auth calls in the UI for quick demos
- Session-backed state collection composed into a single site-config payload
- Schema validation via Ajv with ready-to-run sample payloads
- Admin-focused pages for reviewing saved sites and evaluations

## Repo Layout
- Frontend flows: [sign_up.html](sign_up.html), [login.html](login.html), [profile_setup.html](profile_setup.html), [app_setup.html](app_setup.html), [color_palette.html](color_palette.html), [generation.html](generation.html), [build_preview.html](build_preview.html), [final_preview.html](final_preview.html), [home_page.html](home_page.html)
- Admin pages: [admin_login.html](admin_login.html), [admin_dashboard.html](admin_dashboard.html), [saved_websites.html](saved_websites.html), [saved_evaluations.html](saved_evaluations.html)
- Backend API: [server.js](server.js) (Express static hosting + JSON-backed endpoints)
- Data utilities: [data-collector.js](data-collector.js) (session aggregation) and [validate-config.js](validate-config.js) (schema check)
- Schema and samples: [site-config.schema.json](site-config.schema.json), [site-config.example.json](site-config.example.json), [full-site-data.example.json](full-site-data.example.json)
- Architecture notes: [ARCHITECTURE.md](ARCHITECTURE.md)

## Quick Start
Requirements: Node.js 18+.

```bash
npm install
npm start  # serves all static files at http://localhost:3000
```

- The root [index.html](index.html) redirects to [build_preview.html](build_preview.html) for the builder experience.
- Static files are served from the repo root; images live in [images/](images).

## API (local Express)
- POST /api/signup → `{ name, email, password }` creates a user in users.json (email normalized, password hashed)
- POST /api/login → `{ email, password }` validates credentials
- POST /api/site-config → full site payload validated against [site-config.schema.json](site-config.schema.json) then appended to site-configs.json

### Using the collector
The builder pages write user inputs to `sessionStorage`. [data-collector.js](data-collector.js) normalizes everything into a single object:

```js
const data = SiteDataCollector.collectAllData();
await SiteDataCollector.sendToBackend('/api/site-config');
// or download
SiteDataCollector.downloadAsJSON();
```

Key storage keys: `userProfile`, `selectedPalette`, `generatedLogo` or `uploadedLogo`, `appName`, `selectedCatalog`, `selectedProductPage`, `pageContent`, `pageImages`, `logoSize`, `logoBorderRadius`, `logoViewerZoom`, `logoViewerOffsetX`, `logoViewerOffsetY`, `adminEvaluationRequested`.

## Validation & Samples
- Run schema validation against bundled examples:

```bash
npm run validate
```

- Minimal payload: [site-config.example.json](site-config.example.json)
- Full payload: [full-site-data.example.json](full-site-data.example.json)

## Deployment Notes
- Static hosting works on any CDN or object storage (S3, Netlify, Vercel).
- API can stay as the bundled Express server or be ported to serverless; see [ARCHITECTURE.md](ARCHITECTURE.md) for migration ideas.

## Troubleshooting
- CORS is open for development in [server.js](server.js); tighten origins before production.
- If remote auth endpoints in [login.html](login.html) or [sign_up.html](sign_up.html) fail, switch to the local `/api/login` and `/api/signup` endpoints exposed by the Express server.