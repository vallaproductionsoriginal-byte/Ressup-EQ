# Ressup-EQ

**Shape your tone. Tame resonances. Stay focused on the music.**

Ressup-EQ by **Valla Productions** brings a 24-band equalizer, dynamic EQ and
resonance suppression into one visual workspace. Use it to smooth a sharp vocal,
control ringing synths, tighten a bass part or bring balance to a bus.

![Ressup-EQ interface with spectrum analysis, a single combined EQ response and the selected band's controls](images/ressup-eq.png)

**Version 1.17.3** · macOS Apple Silicon: VST3 / AU · Windows x64: VST3 · Linux x86-64: CLAP

## New in 1.17.3

The EQ display now shows one combined response with editable band nodes.
Changing Input or Output level no longer shifts the curve up or down: it
stays aligned with the EQ settings, including live Dynamics and Res Sup corrections.
See the full [changelog](CHANGELOG.md).

Now also available for **Linux x86-64 as CLAP**, with the full graphical editor.
The Linux package is version **1.17.3-clap.1** and is included in the same release.

## Three ways to shape your sound

- **EQ:** make a lasting tonal change. Add weight, clear some low mids or shape
  the top end with up to 24 bands.
- **Dynamics:** let a band react to the input level. Useful when a frequency
  builds up only on louder notes or phrases. Attack and Release shape how
  quickly the cut or boost engages and recovers. Negative Density cuts; positive
  Density boosts; 0% is neutral. Dynamics starts at -100% to preserve existing sessions.
- **Res Sup:** follow several resonant peaks within the area you select. Use
  negative Density to reduce ringing and harshness, or positive Density to
  bring out resonant character. Density starts at **0%**; move it below zero
  to hear suppression.

Switch between Dynamics and Res Sup with the band's mode buttons. You can
still adjust its regular EQ gain while either mode is working.

## Get started in a few moves

1. **Find the area.** Double-click the spectrum to add a band. Drag its point
   to adjust frequency and gain; use the mouse wheel to change Q.
2. **Choose the response.** Use EQ for tone shaping, Dynamics for level-dependent
   control or Res Sup to work on resonant peaks inside the band.
3. **Dial in the amount.** Choose a negative Density to cut or a positive Density
   to boost in Dynamics or Res Sup. Set a modest Range in the Details drawer,
   then raise Threshold while listening.
4. **Compare by ear.** Turn on **LU MATCH** beside Output to bring the output
   toward the input's momentary loudness, then use Bypass to compare.

Click any band point to select it; use the lower panel’s arrow to show or hide
its controls. Hold **Shift** for finer edits; double-click a control to restore
its default.

## Make the controls work for your mix

**Range and Threshold work together.** Range sets the maximum available cut
or boost at 100% Threshold and full Density. At full negative Density,
Range **−30 dB** and Threshold
**50%** allow up to **15 dB** of reduction; at **100%**, up to **30 dB**.
Raising Threshold also makes quieter peaks eligible for processing. Actual
reduction depends on the signal and the band's sensitivity. New bands start
with Range at **−32 dB**.

Dynamics and Res Sup store their Density settings independently. At positive
Density the same limits apply to boosts.

**Q decides where to focus.** The main Q steers the area covered by the band.
**Res Sup Q** separately widens or narrows the corrections around individual
resonances. Use Attack and Release to match the movement to the performance,
or leave Auto timing enabled.

**A stable EQ reference.** One curve shows the combined EQ and Mix response,
including live Dynamics and Res Sup corrections. Input and Output trims
change the audio level without shifting this curve. Drag the band nodes to
change the EQ settings.

**See what you are hearing.** Pre and Post compare the input and output
spectra; Side shows the stereo difference signal. Freeze remembers Post peaks
while the analyzer stays live. Hover near a peak and click to add a band there.
Cursor and Freeze peak frequencies appear at the top of the analyzer, clear of
the parameter panel. Mix sits between the dB selector and Input in the compact
header, leaving more vertical space for the spectrum. Use Solo to audition
a band's contribution. Choose the **±30 dB** display scale
when you want to see cuts deeper than the default ±12 dB view.

**Choose phase and detail for the session.** Zero latency keeps playback
responsive when recording or playing instruments. Natural is an oversampled
alternative; Linear offers linear-phase EQ with added delay. Detail starts
at **0**. Higher settings improve frequency resolution and use more CPU;
they can also add latency. Very narrow corrections in Linear mode may need
higher Detail.

## Download and install

**[Download Ressup-EQ 1.17.3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/tag/v1.17.3)** — includes the single combined EQ curve, independent of Input and Output level trims.

Choose the ZIP for your system and extract it. Copy the entire plug-in bundle
(macOS/Windows) or the single `Ressup-EQ.clap` file (Linux) to the matching
folder below. Close your DAW before replacing an existing
version, then reopen it and rescan plug-ins if needed.

| Download | Requirements | Installation folder |
| --- | --- | --- |
| [Mac VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.17.3/Ressup-EQ-1.17.3-macOS-AppleSilicon-VST3.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/VST3/` |
| [Mac AU](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.17.3/Ressup-EQ-1.17.3-macOS-AppleSilicon-AU.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/Components/` |
| [Windows VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.17.3/Ressup-EQ-1.17.3-Windows-x64-VST3.zip) | Windows 10/11, x64 | `C:\Program Files\Common Files\VST3\` |
| [Linux CLAP](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.17.3/Ressup-EQ-1.17.3-clap.1-Linux-x86_64-CLAP.zip) | Linux x86-64, glibc 2.35+ (Ubuntu 22.04+), X11/XWayland | `~/.clap/` |

On Linux, create `~/.clap/` if needed and use a DAW with CLAP support. The
editor uses X11; on Wayland, the DAW must host it through X11/XWayland.
Standard desktop libraries (fontconfig, FreeType and X11) are required.
Installation does not require Wine or developer SDKs. This package is for
x86-64; it does not include an ARM64 binary or native Wayland embedding.

The Mac VST3 and AU have been validated on macOS. The Windows build has
**not yet been tested in a Windows DAW**. Mac downloads are not Apple notarized.
File checksums are available in [SHA256SUMS.txt](SHA256SUMS.txt).

The Linux CLAP passes 30 audio integration checks, 13 graphical checks and
all 35 applicable checks in the CLAP validator. It has also been loaded in
REAPER 7.82 for Linux, with its custom editor open and an audio render checked
against the expected gain. These checks ran in an Ubuntu 22.04 x86-64
userspace under Rosetta in an isolated Linux VM on Apple Silicon. The archive
includes the verification manifest, installation instructions and licenses.

## Credits and license

Created by **Francesco Valla** · **Valla Productions**.
Original Ressup-EQ software and documentation are [proprietary](LICENSE).
© 2026 Francesco Valla. All Rights Reserved. Use requires express authorization
under this license or a separate written agreement. Third-party components
retain their own licenses;
see [Third-Party Notices](THIRD_PARTY_NOTICES.md).


