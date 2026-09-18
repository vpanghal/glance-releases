# Glance releases

This repository contains public binary releases of Glance. Atlas source code is
not published here.

## System requirements

- Apple Silicon Mac
- macOS 13 or newer
- Approximately 3 GiB of free disk space for the application and its bundled
  local models

The beta is ad-hoc signed but does not have a Developer ID signature and is not
notarized. macOS may display a Gatekeeper warning after download. If you trust
the checksum and this release repository, open Finder, Control-click Glance,
choose **Open**, and confirm the prompt.

## Install

1. Download the DMG and its `.sha256` file from the selected prerelease.
2. In Terminal, `cd` to the download directory and run `shasum -a 256 -c`
   against the downloaded `.sha256` file.
3. Open the DMG and drag the single `Glance.app` into Applications.

Glance, Lander, the terminal and OCR helpers, Code Mode worker, and local models
are all contained in that one application bundle. Nothing is installed as a
separate service or application. Updates are installed manually from this
repository.

## Bundled beta functionality

The Apple-Silicon beta includes the local Lander backend, the browser-accessible
Glance UI, isolated browser surfaces, microphone dictation, terminal and OCR
helpers, and contained Code Mode execution. The Reason-ModernColBERT model is
distributed under CC-BY-NC-4.0; downstream use remains subject to its bundled
license.

For security reporting, see [SECURITY.md](SECURITY.md).
