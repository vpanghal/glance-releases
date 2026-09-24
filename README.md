# Glance releases

This repository contains public binary releases of Glance. Atlas source code is
not published here.

## System requirements

- Apple Silicon Mac
- macOS 13 or newer
- Approximately 3 GiB for the application, plus space for updates and optional
  on-device model downloads

Current builds require a Developer ID signature and Apple notarization/stapling.
Do not bypass Gatekeeper for an unexpected signature or notarization failure.

## Install

1. Download the DMG and its `.sha256` file from the selected prerelease.
2. In Terminal, `cd` to the download directory and run `shasum -a 256 -c`
   against the downloaded `.sha256` file.
3. Open the DMG and drag the single `Glance.app` into Applications.

Glance, Lander, the normalizer helper and Code Mode worker are contained in that
one application bundle; terminal hosting runs inside Lander. Nothing is installed
as a separate service or application. Optional models are downloaded only after
your authorization and are not bundled in the application.

Updater-capable installations offer signed in-place updates with explicit
restart consent. The release ZIP contains the entire signed/stapled application,
not a frontend-only patch. `update-manifest.json` and its detached Ed25519
signature authorize the exact ZIP using the public key embedded in your installed
app. `beta-mac.yml` or `latest-mac.yml` accompanies each release for updater
interoperability. Do not replace the trusted key with a downloaded key or install
an expired/tampered update. Older installations without updater support, and
installations affected by a signing-key rotation, require a new DMG install.

## Bundled beta functionality

The Apple-Silicon beta includes the local Lander backend, the browser-accessible
Glance UI, isolated browser surfaces, microphone dictation, embedded terminal hosting,
normalization, and contained Code Mode execution. The Reason-ModernColBERT model is
distributed under CC-BY-NC-4.0; downstream use remains subject to its bundled
license.

For security reporting, see [SECURITY.md](SECURITY.md).
