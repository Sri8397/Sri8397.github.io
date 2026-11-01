# Suvidha site (GitHub Pages)

Static files for invite links and usernames. Publish them at the root of a repo named `Sri8397.github.io`
so they are served from `https://sri8397.github.io/`. `.nojekyll` makes GitHub serve the `.well-known` folder.

| File | Purpose |
|---|---|
| `invite/index.html` | Landing page for `https://sri8397.github.io/invite/?id=...&name=...`. People without the app go to the Play Store, with the invite passed as the install referrer. |
| `.well-known/assetlinks.json` | Lets Android open invite links in the production app. Contains the SHA-256 signing certificate reported by Android for the installed Play Store build (`com.just_sri.suvidhaapp`). Update from Play Console > Setup > App signing if the signing key changes. |
| `.well-known/nostr.json` | Username list. Add `"sri": "<64-character public ID>"` inside `names` to give someone `sri@sri8397.github.io`. |

Names are lowercase letters, digits, `.`, `_`, `-`. Each public ID should have one name. Commit and push to publish.

The “I already have the app” button uses `suvidha://invite` so it can open the app even before Android has verified the HTTPS domain. Local debug builds can use this button too; their certificate is intentionally not registered for production App Links. The Play Store button preserves the invite ID and name in the install referrer.
