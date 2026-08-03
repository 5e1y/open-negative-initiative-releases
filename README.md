# Open Negative Initiative — releases

Binaries and the Sparkle appcast for **Open Negative Initiative**, a native macOS app that converts
and edits camera-scanned C-41 colour negatives.

**No source code lives here.** This repository holds only `appcast.xml`, the release archives and
this file. The application's source is a separate repository.

## What is served

- `appcast.xml` — the Sparkle feed the app reads at
  `https://5e1y.github.io/open-negative-initiative-releases/appcast.xml`
- `*.zip` — one signed, notarised archive per release, plus Sparkle delta files when they help.

## Two guarantees, and they are deliberate

**A published version never leaves the feed.** The appcast is generated with `--maximum-versions 0`
and old archives are kept. That is the only way back for someone who does not want the newest build.

**Any release that moves an already-recorded rendering says so in the first line of its notes.**
Sparkle shows those notes *before* installing, and the app never installs on its own
(`SUAutomaticallyUpdate` is `false`) — so an unwanted change of rendering can always be declined.

## Verifying an archive

Every archive is signed with a Developer ID, hardened, notarised and stapled, and the appcast entry
carries an EdDSA signature. To check a download by hand:

```sh
codesign --verify --strict --verbose=2 "Open Negative Initiative.app"
spctl --assess --type execute --verbose "Open Negative Initiative.app"
```

The EdDSA **public** key is in the app's `Info.plist`; it is meant to be readable. The private key
never leaves its author's keychain.
