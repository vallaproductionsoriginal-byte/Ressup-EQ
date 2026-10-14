# Ressup-EQ 1.16.1

Created by **Francesco Valla**. Manufacturer: **Valla Productions**.
Original Ressup-EQ code and documentation: **MIT License**, © 2026 Francesco Valla.
Third-party components retain their own licenses; see `THIRD_PARTY_NOTICES.md`.

This private repository contains **compiled plug-ins and license documents only**.
No source code, build files, debug symbols or SDK headers are included.

## Downloads

- **macOS Apple Silicon VST3** — macOS 14+, arm64.
- **macOS Apple Silicon Audio Unit v2** — macOS 14+, arm64.
- **Windows VST3** — Windows 10/11, x64.

Extract the matching ZIP archive and copy the entire plug-in bundle:

| Format | Installation directory |
| --- | --- |
| macOS VST3 | `~/Library/Audio/Plug-Ins/VST3/` |
| macOS AU | `~/Library/Audio/Plug-Ins/Components/` |
| Windows x64 VST3 | `C:\Program Files\Common Files\VST3\` |

Close the DAW before replacing a plug-in, then reopen it and rescan plug-ins.
The AU includes its own VST3 engine; a separate VST3 installation is not required.
The macOS bundles are ad-hoc signed and are not Developer ID notarized.

## Features and changes

- 24-band parametric EQ, dynamic EQ and adaptive resonance suppression.
- Zero latency, Natural and Linear phase; processing Detail 0–5.
- Live Pre, Post and stereo Side spectrum; Freeze peak memory and peak selection.
- Momentary loudness matching, per-band Solo and external side-chain detection.
- Compact parameter panel and Details drawer; Shift for fine adjustments.
- Res Sup correction follows Range at each frequency, without splitting the
  available depth between separate resonances. At Threshold 100% and Density
  -100%, Range -30 dB allows up to -30 dB; Threshold 50% allows up to -15 dB.
- English interface, menus, tooltips and status messages.
- **Dynamic range defaults to -32 dB** for new bands and double-click reset.
- Res Sup density defaults to 0%. Existing sessions preserve their saved values.

## Verification

The macOS VST3 passes 609 DSP checks, 251 GUI checks, 33 native-view bridge
checks and all 47 VST3 SDK tests. The Audio Unit passes Apple auval strict
validation, including mono/stereo rendering at multiple sample rates.
The Windows x64 binary is cross-compiled with LLVM/MSVC SDK libraries and its
PE architecture, exports and imports are checked. It has not yet been run in
a Windows DAW. SHA-256 checksums are provided in `SHA256SUMS.txt`.

The MIT license for original code does not relicense JUCE, Apple's AudioUnitSDK,
Steinberg's SDK or other dependencies. The author uses JUCE Starter.
