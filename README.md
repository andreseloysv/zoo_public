# Your Zoo — public site and content bundles

Public companion to the private app repository. Two jobs:

1. **Website** (GitHub Pages, served from the root of `main`):
   - Privacy policy: `privacy.html` (DE) · `privacy.en.html` · `privacy.es.html`
   - Support: `support.html` · `support.en.html` · `support.es.html`
   - Attribution (OpenStreetMap, image credits, fonts): `attribution.html` (+ `.en`, `.es`)
   - Landing: `index.html` (+ `.en`, `.es`)
2. **Content bundles** the app downloads as updates (`ZooBundles/<zoo>/manifest.json` + files, `ZooBundles/zoos.json`).
   The app reads them from `https://raw.githubusercontent.com/andreseloysv/zoo_public/main/ZooBundles`.

To publish new content: run `python3 tools/build_bundle.py` in the app repository, then copy `ZooBundles/` here and push.
Map data © OpenStreetMap contributors (ODbL). Images from Wikimedia Commons under the licences listed in `attribution.html`.
