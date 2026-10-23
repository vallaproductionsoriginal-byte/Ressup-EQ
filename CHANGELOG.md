# Changelog

## 1.26.5 — 2026-10-23

- Keep the selected band's parameter panel open during editing and analyzer updates.
- Include Details, its handle and the spaces between controls in the editing area.
- Preserve the selected band when the comparison exchange is temporarily busy.
- Keep an unavailable reference band's panel visible with editing disabled;
  restore editing when the source returns.

## 1.26.4 — 2026-10-22

- Fixed the broken Windows x64 VST3 that crashed the DAW when opening the editor.

## 1.26.3 — 2026-10-22

- Preserve each sample's LU Match switch during Natural oversampling, so a
  later automation event cannot affect earlier audio in the processing chunk.

## 1.26.2 — 2026-10-21

- Res Sup detection now follows the selected curve rather than a fixed Bell
  mask. All Pass has uniform sensitivity across the spectrum.
- Shelf, cut, Notch, Band Pass and both Tilt types use their appropriate
  frequency envelopes; cut slope and Tilt Gain direction are respected.
- Discard stale fine candidates when switching curve or cut slope.
- Add detector and rendered-audio regressions for every shape.

## 1.26.1 — 2026-10-21

- Keep all ten band curves and cut slopes selectable with Res Sup active, alone
  or together with Dynamics; use the chosen curve in audio and every preview.
- Include adaptive resonance capacity: 512 / 384 / 256 / 128 / 64 points per
  band for 1 / 2–3 / 4–6 / 7–12 / 13–24 enabled Res Sup bands.
- Verify node curve selection, gain/slope availability and audio across all
  shape/slope variants in Zero Latency, Natural and Linear modes.

## 1.26.0 — 2026-10-21

- New instances open with all band slots empty and the parameter panel hidden.
- Settings now has Save as default and Reset default for analyzer resolution,
  minimum, speed and curve suggestion. New instances share saved preferences
  across formats; restored projects retain their own settings.
- Replaced the header Instances label with an accessible icon.
- Added a folder icon before Pre with 20 factory presets, user presets, Open,
  Save as and Show preset folder. Presets use `.rseq`; legacy `.rsp` remains
  readable. User directories follow macOS, Windows and Linux conventions.
- Preset writes are atomic and retain full numeric precision and Unicode paths.

## 1.25.0 — 2026-10-21

- Res Sup now tracks up to 64 simultaneous resonances in each band. Density
  selects one through 64 peaks; Amount, Threshold and Q retain their roles.
- Dense fine-resolution peaks remain eligible when their coarse FFT spectrum
  merges into a plateau, with current short-window energy gating.
- Process only active/releasing filters; reuse preallocated Range-limiter
  geometry and identical gain calculations without changing its ceiling.
- Extend local, finite Linear and cross-instance curves beyond the eighth voice.
  Shared comparison data uses a separate v6 exchange.
- State format 17 and preset format 14 preserve older one-to-eight Density
  budgets. Existing IDs and parameter positions are retained. Old DAW Density
  automation percentages need rescaling to preserve their previous budgets.

## 1.24.0 — 2026-10-20

- Save instance names, stable identities, comparison selections and every band's
  instance sidechain source in the project. Chains reconnect automatically when
  source instances load later or in a different order.
- Added the MAIN / named-instance selector beside Instances and removed the
  duplicate Main / Reference buttons above the band parameters.
- Replaced each band's External SC button with a source menu: External SC for
  the DAW input, MAIN for internal detection, and the other live instances.
- Added stereo Post audio exchange between instances and host processes for
  both Dynamics and Res Sup, including sample-rate conversion and silent release
  when a source stops or closes.
- Fixed VST3 mono sidechain negotiation while retaining stereo sidechain support.
- Instance metadata is appended in state format 16; existing parameter IDs,
  automation values and older parameter-only states remain compatible. Older
  projects need names and instance sources assigned once, then saved again.

## 1.23.0 — 2026-10-20

- Added a per-band Res Sup Density knob from 0 to 100%, selecting the dominant
  resonance through up to eight simultaneous peaks. Secondary peaks enter
  gradually and leave through the existing Release timing.
- Relabeled the signed Res Sup intensity control Amount in the editor. Its
  existing host parameter name, automation ID and stored values remain intact.
- Appended 24 peak-density parameters in state format 15. Older projects default
  to 100% Density and retain all previous parameter positions and corrections.
- Expanded parameter storage and versioned the inter-instance exchange for
  the new layout; comparison/editing connects instances using this layout.

## 1.22.1 — 2026-10-20

- Scrolling anywhere in the editor adjusts the selected band's Q, including
  over controls or another band's node. Shift retains fine adjustment, and
  scrolling keeps the current main/reference selection.
- Clicking empty spectrum space deselects the band and fully hides its
  parameter panel. Clicking a band node selects it and restores the controls.
- Scroll routing preserves other control values and balanced host gestures.

## 1.22.0 — 2026-10-20

- Added a continuous per-band L/R or Mid/Side processing balance below Gain.
  Both components retain the full effect at the centre; moving toward one
  reduces the other component’s processed contribution without panning dry audio.
- Added the saved Curve suggetion preference for frequency-based initial
  High Pass, Low Shelf, Bell, High Shelf or Low Pass insertion.
- Right-clicking a band node opens a compact curve menu with all ten icons.
  Curve icons remain in selection menus; spectrum nodes stay numbered.
- Expanded the analyzer to the left and added logarithmic frequency
  subdivisions. The right-hand dBFS spectrum scale remains independent of
  the EQ response; the left gain scale is hidden.
- Preserved all existing channel automation choices and parameter IDs.
  Appended the new preference and per-band balances in state format 14;
  older states retain their previous channel routing.
- Rewrote the README as one current feature guide and replaced its screenshot.

## 1.21.0 — 2026-10-19

- Fixed VST3 automation timing: all queued points and piecewise linear segments
  are consumed at their sample positions, with callback-independent de-clicking.
- Added 5 ms trim, Mix and Bypass ramps, smoothed band controls and crossfades
  for filter topology changes, including rapid reversals. Preserve filled dry
  history during Phase/Detail reconfiguration and bridge new-path warm-up.
- Replaced the short, tapered Linear design with a full symmetric 16k/32k FIR
  grid. Main and instance curves include the actual finite response, including
  off-grid bass approximation. Updated reported host latency.
- Natural uses symmetric FIR resampling and an original delayed dry Mix path,
  removing dispersive resampling phase from neutral parallel processing.
- Output loudness meters include the actual bypass crossfade and delayed dry.
- Guarded LU MATCH transient compensation against a reference peak envelope
  with 3 dB headroom; the ordinary EQ path has no added limiter or clipper.
- Fine Res Sup peaks can create separate voices; fast-frame strength and gating
  preserve transient tracking. Retained existing parameter IDs and state format.
- Added measured-audio and real-VST3 automation regression targets, and updated
  physical latency/FIR reference checks for the corrected implementation.
- Instance name/source UI commands retry short background exchange contention.


## 1.20.9 — 2026-10-18

- Mix now matches Input and Output in size; Compare and Instances move to the header.
- Fixed the rising analyzer floor at the -120 dB minimum. Silence stays flat and real weak signals retain the display tilt.

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
  Windows x64 VST3, and Linux x86-64 CLAP.

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
