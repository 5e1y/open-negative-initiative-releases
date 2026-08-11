<p align="center">
  <img src="assets/icon.png" width="160" alt="Open Negative Initiative">
</p>

<h1 align="center">Open Negative Initiative</h1>

<p align="center">
  Convert and edit scanned film — negatives and positives — on macOS.<br>
  Free, native, and floating point from the RAW to the file it writes.
</p>

<p align="center">
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases/latest">
    <img src="https://img.shields.io/github/v/release/5e1y/open-negative-initiative-releases?style=flat-square&color=E26D1F&label=version" alt="Latest version"></a>
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases">
    <img src="https://img.shields.io/github/downloads/5e1y/open-negative-initiative-releases/total?style=flat-square&color=E26D1F&label=downloads" alt="Downloads"></a>
  <a href="https://github.com/5e1y/open-negative-initiative-releases/stargazers">
    <img src="https://img.shields.io/github/stars/5e1y/open-negative-initiative-releases?style=flat-square&color=E26D1F&label=stars" alt="Stars"></a>
  <img src="https://img.shields.io/badge/macOS-13%2B-E26D1F?style=flat-square" alt="macOS 13 or later">
  <img src="https://img.shields.io/badge/Apple%20Silicon%20%C2%B7%20Intel-universal-E26D1F?style=flat-square" alt="Universal binary">
</p>

<p align="center">
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases/latest/download/OpenNegative.dmg">
    <strong>↓ Download for macOS</strong></a>
  &nbsp;·&nbsp;
  <a href="https://open-negative-initiative.com/">Website</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases">All versions</a>
</p>

<!-- SCREENSHOT GOES HERE -->

---

## What it does

- **Inverts in density, not `1−x`.** The sliders behave linearly in stops, so a correction reads
  like an exposure change instead of a curve fight.
- **Nothing decides on its own.** No film-base detection, no preset applied on import. The
  automatic balance runs on a click, draws what it proposes on hover, and ⌘Z undoes it.
- **Camera scans and flatbed scans.** RAW, DNG and TIFF in, a linear Rec. 2020 working space
  throughout, 16-bit TIFF or JPEG out in the colour space you pick.

## Installing

Open the DMG and drag the app onto the Applications folder beside it. If macOS says it cannot
verify the app, open **System Settings → Privacy & Security**, scroll to the bottom and click
**Open Anyway** — right-click → Open no longer does this on recent macOS.

The app looks for updates on its own and never installs one without asking. Release notes are shown
before you accept, and their first line always says whether a version changes how a photograph you
have already adjusted will render.

## Reporting something

Open an [issue](https://github.com/5e1y/open-negative-initiative-releases/issues). Two things make a
report usable: **the version**, which the About window reads on its own, and **the RAW file** if it
is a colour or decoding problem — a screenshot shows the symptom, the file reproduces it.

A picture that opens flat or nearly white is worth reporting even though nothing crashed.

## Source code

**Not in this repository** — this one holds the builds and the update feed. The app is licensed
**GPL-3.0** and its source will be published when it leaves beta: the constants that decide how a
negative renders are still being calibrated against real film, and forks of a moving render would
scatter versions that disagree about what a photograph should look like.
