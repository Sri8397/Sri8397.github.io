# Suvidha site (GitHub Pages)

Static files for invite links and usernames. Publish them at the root of a repo named `Sri8397.github.io`
so they are served from `https://sri8397.github.io/`. `.nojekyll` makes GitHub serve the `.well-known` folder.

| File | Purpose |
|---|---|
| `invite/index.html` | Landing page for `https://sri8397.github.io/invite/?id=...&name=...`. People without the app go to the Play Store, with the invite passed as the install referrer. |
| `.well-known/assetlinks.json` | Lets Android open invite links in the app. Replace `REPLACE_WITH_PLAY_APP_SIGNING_SHA256` with the app signing certificate SHA-256 from Play Console > Setup > App signing. |
| `.well-known/nostr.json` | Username list. Add `"sri": "<64-character public ID>"` inside `names` to give someone `sri@sri8397.github.io`. |

Names are lowercase letters, digits, `.`, `_`, `-`. Each public ID should have one name. Commit and push to publish.
