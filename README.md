# Your Zoo — public site and content bundles

Public companion to the private app repository. Two jobs:

1. **Website** (GitHub Pages, served from the root of `main`):
   - Privacy policy: `privacy.html` (DE) · `privacy.en.html` · `privacy.es.html`
   - Support: `support.html` · `support.en.html` · `support.es.html`
   - Attribution (OpenStreetMap, image credits, fonts): `attribution.html` (+ `.en`, `.es`)
   - Landing: `index.html` (+ `.en`, `.es`)
2. **Content bundles** the app downloads as updates (`<zoo>/manifest.json` + files and `zoos.json`), in two channels:
   - `ZooBundles-v2/`: all 20 zoos, with recorded narration (`<zoo>/audio/`, streamed on demand). Read by app build 10
     on: `https://raw.githubusercontent.com/andreseloysv/zoo_public/main/ZooBundles-v2`.
   - `ZooBundles/`: Zoo Frankfurt only. Read by the App Store build 9 (version 1.2). Leave it as it is: that build's
     engine does not score disabled enclosures as silent competitors, so it must not receive the other zoos, whose
     automatic guide is on only next to such enclosures.

To publish new content: run `python3 tools/build_bundle.py` in the app repository, then copy its `ZooBundles/` into
`ZooBundles-v2/` here (`rsync -a --delete --exclude='*.tmp' --exclude='*.copy' --exclude='*.lock' --exclude='.DS_Store'`)
and push. Raise a zoo's `version` in `tools/content/<zoo>/zoo.json` for installed apps to pick up the change.

Map data © OpenStreetMap contributors (ODbL). Images from Wikimedia Commons under the licences listed in `attribution.html`.
