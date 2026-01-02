# Tap to Build — Frontend

Data delivery for backend integration:

- Example payload: see [site-config.example.json](site-config.example.json)
- Field sources:
	- Profile: saved in `sessionStorage.userProfile` by [profile_setup.html](profile_setup.html)
	- Palette: saved in `sessionStorage.selectedPalette` by [color_palette.html](color_palette.html)
	- Logo: base64 in `sessionStorage.generatedLogo` or `sessionStorage.uploadedLogo` via [generation.html](generation.html) or [app_setup.html](app_setup.html)
	- App name: `sessionStorage.appName` derived from `websiteName`
	- Optional content/images: `sessionStorage.pageContent` and `sessionStorage.pageImages` from builder pages like [build_preview.html](build_preview.html)
	- Logo controls: `sessionStorage.logoSize`, `sessionStorage.logoBorderRadius`, viewer values `sessionStorage.logoViewerZoom`, `sessionStorage.logoViewerOffsetX`, `sessionStorage.logoViewerOffsetY`

Auth API payloads (server expectations):

- Signup POST /api/signup: `{ "name": string, "email": string, "password": string }`
- Login POST /api/login: `{ "email": string, "password": string }`

Collector utility:

- See [data-collector.js](data-collector.js) which composes a comprehensive payload matching [site-config.schema.json](site-config.schema.json). Use `SiteDataCollector.downloadAsJSON()` or `SiteDataCollector.sendToBackend(url)`.

Comprehensive examples:

- Minimal: [site-config.example.json](site-config.example.json)
- Full: [full-site-data.example.json](full-site-data.example.json)