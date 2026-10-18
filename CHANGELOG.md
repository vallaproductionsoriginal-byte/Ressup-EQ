# Changelog

## 1.20.8 — 2026-10-18

- Disabled bands stay gray, selectable and saved until explicitly deleted.
- Click Q to show or hide its curve projection; the label turns red when enabled.
- Deep Dynamics and Res Sup curves no longer flatten at ±30 dB, including reference curves.
- The standard EQ scale stays fixed at ±30 dB; changing Range leaves the spectrum unchanged.
- Existing settings remain compatible.

## 1.20.4 — 2026-10-17

- Improved Res Sup detection on notes and chords, with a more consistent response across pitches.
- Existing parameter IDs and saved settings remain compatible.

## 1.20.2 — 2026-10-17

- Fixed missing Res Sup corrections in the main and comparison curves at
  very low Res Sup Q values. Broad adaptive voices now remain visible and
  follow the same filter-design limits as the actual audio processing.
- Verified Standard, Dynamics, Res Sup and Dynamics + Res Sup together on
  one combined curve, with every band count from 1 through 24. Added
  3,168 audio configurations, 40,560 response configurations, 48 live mode
  transitions and 840 GUI renders, including minimum-Q bass regressions.
- All six macOS test suites and the combination matrix with AddressSanitizer
  and UndefinedBehaviorSanitizer passed. Parameter IDs and saved settings
  remain compatible.
- Binary distributions: macOS Apple Silicon VST3 and self-contained AU,
  Windows x64 VST3, and Linux x86-64 CLAP. Project sources are not distributed.

## 1.20.1 — 2026-10-17

- Normal EQ bands now run in series in all phase modes. Low Cut + High Cut
  forms the intended passband instead of producing phase cancellation from
  parallel difference signals. Solo retains its difference-signal audition.
- Main and comparison curves follow the same ordered stereo transfer, including
  asymmetric Left/Right and Mid/Side combinations in Linear mode.
- Cut slope 0 dB/oct is neutral; 6 dB/oct uses a normalized one-pole design
  with the correct cutoff. Brickwall uses a 192 dB/oct finite approximation
  instead of duplicating 96 dB/oct.
- Added an audio/curve regression sweep for every ordered shape/slope pair,
  every routing pair, coincident/crossed cutoffs, Mix, Solo and 24 active bands.

## 1.20.0 — 2026-10-16

- Instances now orders External sidechain, Main, then other live instances.
- Selecting a reference with Compare enabled exposes its EQ as a solid
  brick-coloured curve with editable band nodes and a routed parameter panel.
- Drag frequency/gain, wheel Q, add/delete bands and edit band settings directly
  in the reference instance. Main / Reference or a node click retargets editing.
- Remote values reach the target's audio owner through a lock-free queue and
  persist in its state. VST3 reports changes through output parameter queues;
  CLAP sends balanced gesture/value events, including inactive host flushes.
- Switching targets, disabling Compare or losing the reference finishes pending
  gestures and restores local editing. Reference previews update during a drag.
- Updated exchange protocol; all participating instances need 1.20.0.

## 1.19.0 — 2026-10-16

- Added a Compare icon and Instances button beside Valla Productions.
- Competing frequencies appear as orange vertical regions; width follows the
  overlapping frequency range and strength increases their width and opacity.
- Compare the local Post signal with external sidechain or another instance's
  Post signal. The reference spectrum and dashed applied EQ response are shown.
- A scrollable Instances window previews live spectra and applied EQ curves,
  including Dynamics, Res Sup, mix, routing and bypass. Instances can be named.
- Per-user, versioned shared memory exchanges spectra across plug-in formats
  and host processes, including instances whose editors are closed. A background
  worker performs FFT and exchange; audio uses only a lock-free FIFO and atomics.
- Closed instances are removed; stopped audio clears its spectrum, and crashed
  publishers expire. Unavailable references never switch to sidechain silently.
- Comparison enable uses the existing Trace Clash parameter and is saved by
  the host. Names and source choices persist while the engine is loaded.

## 1.18.0 — 2026-10-16

- Replaced LU MATCH and BYPASS text buttons with icons and added a settings gear.
- Analyzer FFT resolution 1024–65536 samples, minimum 0–120 dB (default 100),
  and five speeds controlling both rise and fall. Outside clicks close settings.
- Dynamics and Res Sup can run together on a band, Dynamics first. The Edit
  selector exposes each stage's independent Threshold and Density.
- Extended Res Sup Q to 0.01–4x; state version 13 preserves older physical Q
  values and mode behaviour. Parameter IDs and serialized order remain stable.
- macOS Apple Silicon VST3 and self-contained AU, Windows x64 VST3,
  and Linux x86-64 CLAP with the custom editor.

## 1.17.4 — 2026-10-15

- The spectrum uses a fixed 0 to -120 dBFS scale, including saved sessions,
  with labels every 20 dB on the right axis.
- Removed the header depth selector. The EQ gain axis always shows the full
  +/-30 dB band gain range.
- Increased the display FFT from 4096 to 16384 samples for finer frequency
  detail. Shape-preserving cubic curves smooth both live and Freeze traces
  while retaining narrow peaks between pixels.
- Available as macOS Apple Silicon VST3 and self-contained Audio Unit v2,
  Windows x64 VST3, and Linux x86-64 CLAP with the custom editor.

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
