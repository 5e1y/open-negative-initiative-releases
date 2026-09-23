<p align="center">
  <img src="assets/icon.png" width="160" alt="Open Negative Initiative">
</p>

<h1 align="center">Open Negative Initiative</h1>

<p align="center">
  Convert and edit scanned film on macOS: negatives, positives and black &amp; white.<br>
  Free, native, and floating point from the RAW to the file it writes.
</p>

<p align="center">
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases/latest">
    <img src="https://img.shields.io/github/v/release/5e1y/open-negative-initiative-releases?style=flat-square&color=E26D1F&label=version" alt="Latest version"></a>
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases">
    <img src="https://img.shields.io/github/downloads/5e1y/open-negative-initiative-releases/total?style=flat-square&color=E26D1F&label=downloads" alt="Downloads"></a>
  <a href="https://github.com/5e1y/open-negative-initiative-releases/stargazers">
    <img src="https://img.shields.io/github/stars/5e1y/open-negative-initiative-releases?style=flat-square&color=E26D1F&label=stars" alt="Stars"></a>
  <img src="https://img.shields.io/badge/status-beta-E26D1F?style=flat-square" alt="Beta">
  <img src="https://img.shields.io/badge/macOS-13%2B-E26D1F?style=flat-square" alt="macOS 13 or later">
  <img src="https://img.shields.io/badge/Apple%20Silicon%20%C2%B7%20Intel-universal-E26D1F?style=flat-square" alt="Universal binary">
</p>

<p align="center">
  <!-- Through the website, which counts the click and redirects; the file still comes from this
       repository's latest release. Measured 18 August 2026: `download_count` counts bytes served to
       anything that asks, and could not tell this button apart from a crawler or from Sparkle
       updating an existing copy. `t=readme` names this button; the referring host separates the
       GitHub page from the Pages one, so both surfaces are told apart without a second link. -->
  <a href="https://open-negative-initiative.com/dl?t=readme">
    <strong>↓ Download for macOS</strong></a>
  &nbsp;·&nbsp;
  <a href="https://open-negative-initiative.com/">Website</a>
  &nbsp;·&nbsp;
  <a href="https://open-negative-initiative.com/gallery">Gallery</a>
  &nbsp;·&nbsp;
  <a href="https://open-negative-initiative.com/manual">Manual</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/5e1y/open-negative-initiative-releases/releases">All versions</a>
</p>

<p align="center">
  <img src="assets/screenshot.png" alt="The editor: an aerial frame of a cliff and turquoise sea on the canvas, the Color panel down the left with its histogram, the six automatic balance keys with CLASSIC and AVG lit, the temperature and tint filters and the dye separation row, the film strip down the right, and the Crop and Spectrogram finishing panels floating over it">
</p>

---

## What it does

- **Inverts in density.** The sliders behave linearly in stops, so a correction reads
  like an exposure change instead of a curve fight.
- **Nothing decides on its own.** No automatic white balance, no film-base detection, no preset
  applied on import. The automatic balance places its points on a click, and one ⌘Z takes them back.
- **Camera scans and flatbed scans.** Camera RAW, linear DNG, TIFF, JPEG, PNG and HEIC in, an
  extended linear Rec. 2020 working space throughout, 16-bit TIFF or JPEG out in the colour space
  you pick.
- **Your originals are only read.** Import is by reference, your settings live beside each scan, and
  nothing is written to your disk outside an export you asked for.

## Where it is

**Beta since 0.1.0.** Bugs are still to be expected, and the render is not frozen: some versions
change how a photograph you have already adjusted will render, and the first line of every release
note says whether this is one of them.

macOS 13 Ventura or later, on Apple Silicon or Intel: one universal build for both.

## Features

**Converting**

- **Negative, positive, black &amp; white.** The frame's own nature, set in the top bar, not a preset.
- **Automatic balance, six ways.** Classic, Mids, Highs, Whites, Body and their average. Each wins
  on films the others lose; none is right everywhere, which is why there are six. They read the
  measuring window in square cells, each taken by its median, so dust and specks never set a point.
- **A measuring window of your own.** A cyan frame you place on the photograph, after which the
  balance and the levels histogram read only what it holds. It travels with the framing copy and paste.
- **Source balance.** Per-channel gains, ±3 stops, where a dichroic head would act.
- **Per-channel levels.** Black, shadows, midtone, highlights and white, placed on a density axis
  you can read, with the histogram measured before the handles so it does not move under them.
- **Density ceiling.** How far up the axis is read, to pull separation out of a burnt patch.
- **Dye separation.** A crosstalk matrix that subtracts each dye's spill into the other two
  channels, so colours separate while greys stay where they are. Five families (Kodak C-41,
  Fuji C-41, Generic C-41, ECN-2 and E-6), dosed from 0 to 200 %.
- **Manual curves.** Five channels, drawn by hand, on a natural cubic spline.
- **Flat-field correction.** A mask divided out before anything else, for the lighting of the rig.

**Grading**

- **Exposure in stops.** ±4 EV with the hue held, so a white stays white in both directions and the
  mid-tones carry the stop. Then the two end points, shadows, highlights and midtones.
- **Colour.** Temperature and tint as filters, plus colour density, acting after the conversion.
- **Effects.** Contrast, vignette and film fade. The contrast is a normalised logistic, monotone
  and pinned at both ends, so it cannot clip.
- **Spectrogram finishing.** Eight points on a wheel, one per colour range: the angle is that
  colour's hue, the distance from the centre its saturation, and a second point on the same spoke
  its luminance.
- **Finishing balance.** Five zones per channel, black to white, where a middle band is held
  against the end points rather than allowed to overtake them.
- **Zone saturation.** Saturation split on luminance, shadows to highlights.

**Detail**

- **Chroma denoise.** Colour noise only; the luma comes out bit-identical, so grain survives.
- **Sharpening and texture.** Dosed in full-resolution pixels, with a loupe that renders at 1:1
  because no fitted preview can show what the exported file will get.
- **The canvas renders in your display's own colour space**, so saturated colours that would clip on
  a wide-gamut screen show. View → Canvas Colour Space puts it back; exports are unchanged either way.

**Correction**

- **Dust and scratches.** A round brush, and nothing scans the photograph looking for defects: your
  stroke is the only detector. A classical search on the GPU then finds a matching patch elsewhere
  in the same frame and copies it pixel for pixel. No neural network. Each correction is numbered
  and listed, so you can take one back without taking back the rest.

**Framing**

- **Crop, straighten, quarter turns, two mirrors.** At 3:2, 4:3, 1:1, 6:7, 5:4 or free. The whole
  photograph stays visible under an angle, and a locked ratio is reapplied on every quarter turn.
- **Copy and paste a framing** over a whole selection, which is what a copy stand wants.

**Archive**

- **Sidecars are the truth.** One JSON beside each original; the index is a cache you can throw
  away without losing an adjustment, and it rebuilds itself from the sidecars.
- **Rolls.** Group frames with ⇧⌘G and name it; the gallery cuts on rolls, not days. A roll carries
  its own film stock, shot date and camera body.
- **Boxes.** Virtual containers that nest above rolls, and never folders on disk.
- **Projects.** Frames pulled across rolls, each photograph sitting in one project.
- **Medals.** Bronze, Silver and Gold, set on a photograph or a whole selection, with a filter in
  the top bar that shows one tier and no other.
- **Drag and drop.** Move a photograph into any roll or day by dropping it there, and import by
  dragging files or a whole folder from the Finder anywhere in the window.
- **A grid of six or twelve columns.** Six because a strip of film is cut into six frames, twelve
  for sorting a roll rather than judging one frame.
- **The library is read off the main thread**, so the gallery stays usable while the originals are
  read, and the index pass shows on the status bar with its counter.
- **A moved or unplugged original is found again by its fingerprint**, not by its file name.
- **Contact sheets.** A selection laid six to a row in one scene-linear TIFF, imported and edited
  as one photograph. The balance reads each frame through its own window rather than the sheet as
  one picture, and the gaps export black.
- **Presets.** One file each, shared by sending it. Five film presets ship with the app: Azure,
  Cinestill 800T, Gold 200, Portra 400 and Redscale.
- **Copy and paste settings.** Row by row, over a whole selection. A copy carries only what the
  source photograph actually moved.

**Exporting**

- **A screen of its own.** One row per photograph, their settings in a panel beside them, the size
  each file will weigh estimated from its preview, and a batch you can stop between two files.
- **16-bit TIFF or JPEG**, in sRGB, Display P3 or Adobe RGB. Exports never enlarge: a size above the
  original is brought back to the original.
- **Three presets.** Instagram, Display and Print set every row at once and lock nothing.
- **An HDR gain map** on JPEG exports. It changes no pixel: an HDR screen shows the picture up to
  two stops above the white of the page, and every other reader sees exactly the same picture.
- **Seven EXIF fields per image.** Camera, lens, film picked from a catalogue of 41 stocks, ISO,
  date, artist and copyright. The line opens on the scanner's own EXIF so you can see whose facts those are and
  replace them, and nothing of the scanner is written unless you leave it there.

## Installing

Open the DMG and drag the app onto the Applications folder beside it. If macOS says it cannot
verify the app, open **System Settings → Privacy & Security**, scroll to the bottom and click
**Open Anyway**. Right-click then Open no longer does this on recent macOS.

The app looks for updates on its own and never installs one without asking. Release notes are shown
before you accept, and their first line always says whether a version changes how a photograph you
have already adjusted will render.

## Reporting something

Open an [issue](https://github.com/5e1y/open-negative-initiative-releases/issues). Two things make a
report usable: **the version**, which the About window reads on its own, and **the RAW file** if it
is a colour or decoding problem: a screenshot shows the symptom, the file reproduces it.

A picture that opens flat or nearly white is worth reporting even though nothing crashed.

## Source code

**Not in this repository.** This one holds the builds and the update feed. The app is licensed
**GPL-3.0**, and **every release carries its own source archive**, attached to that release as
`OpenNegative-<version>-source.zip`. The versions published before the archive existed have been
given one too, so there is no build you can install and not read.

**Take the file with `-source` in its name**, not the "Source code (zip)" GitHub attaches on its
own: that one archives *this* repository, binaries and an update feed, and holds no Swift at all.

Each archive is built in the same pass as the binary it ships with, so what you read is the tree
that produced the build you are running and not whatever it became afterwards. Inside: the Swift
sources, the Metal kernels, the resources, the package manifest and the Makefile, and none of the
tooling that is specific to my own machine.

**One piece is missing, and it is worth knowing before you start.** The keycap button component
lives in a separate private repository, so the archive does not compile as it stands: drop the
`Keycap` dependency from `Package.swift` and put plain SwiftUI buttons in its place first. That is
about an hour of work, and everything else builds with `make app`.
