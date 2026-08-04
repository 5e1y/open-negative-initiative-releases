# Open Negative Initiative

A native macOS app that converts and edits **scanned colour negatives and colour positives**. It processes RAW, TIFF & DNG files
you get from scanning film whatever your method.

It inverts in density, gives you per-channel gains, levels, curves and a finishing balance, and
exports 16-bit TIFF or JPEG. Everything stays in floating point from the RAW to the file written.

**Requirements:** macOS 13 or later, Apple Silicon or Intel (universal).

---

## Download

**[OpenNegative-0.1.0.dmg](./OpenNegative-0.1.0.dmg)** — open it, then drag the app onto the
Applications folder sitting beside it.

### If macOS refuses to open it the first time

Two different messages, and they call for two different answers.

- **"Apple could not verify…"** — that build was not notarised. Open **System Settings → Privacy &
  Security**, scroll to the bottom, and click **Open Anyway** next to the app's name.
  ⚠️ Right-click → Open does **not** do this any more on recent macOS; the item is gone.
- **It simply opens** — that build was notarised and stapled, which is the normal case.

---

## This is an ALPHA

Said plainly, because two consequences follow.

**The rendering can change between versions.** That is deliberate: the app exists to be calibrated
against real film, and a badly-chosen constant only ever shows up on somebody else's negatives. The
promise is not that the picture never moves — it is that **it never moves without telling you**. Any
release that shifts an already-recorded conversion says so in the first line of its notes, and the
app never installs an update on its own: it shows you the notes and waits.

**Your edits live next to your RAW files.** Each converted frame gets a small sidecar file beside the
original. The RAW itself is never touched or moved — the app only ever reads it. Removing a photo
from the library deletes its sidecar and its thumbnails and leaves the original exactly where it was.

---

## Updates

The app looks for updates on its own and **never installs one by itself**. When one is waiting, the
Export button at the right of the top bar becomes an **Update** button naming the new version.
Export stays available on ⌘E and in the File menu.

A published version never leaves the feed and its file is kept, so going back to an earlier build is
always possible.

---

## Reporting something

Open an issue here. Two things make a report usable:

- **the version** — the About window reads it on its own, no need to hunt for it;
- **the RAW file**, if it is a decoding or a colour problem. A screenshot shows the symptom; the file
  is what reproduces it.

If the app opened your file but the picture came out flat or nearly white, that is worth reporting
even though nothing crashed — the app has a specific check for it and says so in its own diagnostics.

---

## What is in this repository

Only the built app and the Sparkle update feed: `appcast.xml`, the release archives, and this file.
**No source code lives here** — the application's source is a separate, private repository.
