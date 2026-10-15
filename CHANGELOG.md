# Changelog

## 1.17.3 — 2026-10-15

- The EQ display now shows a single combined response. Removed the individual
  band curves and the selected band's Res Sup preview envelope; band nodes
  remain editable. Live Dynamics and Res Sup corrections remain visible in
  the combined response.
- Input and Output level trims no longer shift the EQ curve up or down.
  The display represents the EQ and Mix settings independently of both trims.
- Updated Input and Output tooltips, README and interface screenshot.
- Available for macOS Apple Silicon as VST3 and self-contained Audio Unit v2,
  and for Windows x64 as VST3. Plug-in identities, parameter IDs and saved
  settings remain compatible.
- Added the Linux x86-64 CLAP package, version 1.17.3-clap.1, with the full
  graphical editor, automation, sidechain and shared audio engine. Requires
  glibc 2.35+ (Ubuntu 22.04+) and X11/XWayland hosting.
- The Linux CLAP passes audio, graphical and official CLAP validator checks,
  and a REAPER 7.82 Linux load/editor/render test in an Ubuntu 22.04 x86-64
  userspace under Rosetta. The archive includes a verification manifest.

## 1.17.2 — 2026-10-15

Changes since the previous published release, 1.16.2. This release includes
the improvements introduced in the local macOS builds 1.17.0 and 1.17.1.

### Dynamics

- Density is now available in Dynamics: negative values attenuate, zero is
  neutral, and positive values boost the band when the signal exceeds Threshold.
- Density ranges from -100% to +100% and scales the available action within
  the Range and Threshold limits. Attack and Release also apply to boosts.
- Dynamics and Res Sup retain separate Density settings when switching modes.
  Dynamics defaults to -100% to preserve the sound of existing projects;
  Res Sup continues to default to neutral 0%.
- The response curve, band movement indicator and gain meter show dynamic
  boosts as well as cuts. Adaptive boosts also work with shapes without a
  static Gain control.
- Existing plug-in identities, parameter IDs and saved project values remain
  compatible. Older projects retain their original downward Dynamics action.

### Interface and spectrum

- Cursor frequency appears at the top of the analyzer, clear of the band
  parameter panel. Freeze peak frequency uses the same top placement.
- Frequency labels stay inside the analyzer at its left and right edges.
- Removed the "PARAMETRIC EQUALIZER" subtitle.
- Moved Mix between the dB display selector and Input, on the main header row.
- The compact header gives the analyzer 22 additional pixels of vertical space.

### Downloads and validation

- macOS Apple Silicon: VST3 and self-contained Audio Unit v2, macOS 14 or later.
- Windows x64: VST3, Windows 10/11.
- macOS GUI, native editor bridge and DSP regression tests pass. The macOS
  VST3 passes the Steinberg validator and the AU passes strict Apple auval.
- The Windows x64 build is cross-compiled and checked for binary architecture,
  version metadata and runtime imports. Testing in a Windows DAW remains pending.
- All bundles include the proprietary license and third-party notices.
  SHA-256 checksums accompany the downloads. Mac bundles are ad-hoc signed
  and are not Apple notarized.

## 1.16.2 — 2026-10-15

- Included the updated Proprietary Software License and third-party notices
  in macOS Apple Silicon VST3 / AU and Windows x64 VST3 packages.
