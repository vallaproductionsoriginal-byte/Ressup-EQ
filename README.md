# Ressup-EQ

**Hear where tracks compete. Make room for both.**

Ressup-EQ combines a 24-band equalizer, dynamic EQ and **Res Sup 2.0** resonance
control. Shape the tone, tame ringing notes and harsh peaks, and compare tracks
from one window while listening to your mix.

Made by **Francesco Valla · Valla Productions**.

**Version 1.27.2** · macOS Apple Silicon: VST3 / AU · Windows x64: VST3 · Linux x86-64: CLAP

**[Download Ressup-EQ 1.27.2](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/tag/v1.27.2)**

## Important: older projects

**Compatibility with projects saved in older versions is not guaranteed.**
Res Sup 2.0 changes how resonance processing behaves and replaces the previous
Legacy detector. Older settings, presets and automation may not recall the same
result, and an existing mix may sound different after updating. Keep a backup of
your sessions and the previous plug-in version before opening older projects.

![Ressup-EQ with the Res Sup 2.0 controls, including Soft detection, Peak Limit, Selectivity, Delta and realtime/offline quality](images/ressup-eq.png)

## What's new: Res Sup 2.0

Res Sup follows resonant peaks as the sound changes. Use it to soften a ringing
vocal, reduce guitar harshness, control synth resonances or bring out selected
harmonics with positive Amount.

- **Soft / Hard detection.** Soft is the starting point for finding peaks that
  stand out from the surrounding sound. Hard responds to their level, useful
  when you want a clearer threshold for stronger moments.
- **Selectivity.** Raise it to concentrate on the most obvious resonances; lower
  it to include subtler peaks. Processing has been improved for lower settings.
- **Detector Tilt.** Shift attention toward the low or high end without using
  the detector control as a tonal EQ.
- **Delta listening.** Hear what Res Sup changes, so you can judge whether you
  are removing harshness or taking away useful character. Turn Delta off to
  return to the full processed sound.
- **Focused Bell processing.** Frequency and the main Q define the central area
  where Res Sup works. Corrections stay focused there, including when Res Sup Q
  is broad, helping preserve material outside the chosen area.
- **Realtime and Offline quality.** Choose how closely processing follows the
  changing sound during playback and export. Start with Normal and increase
  quality when the session has room for it.

Detector, Selectivity, Tilt, Delta and quality choices sit beside Attack and
Release in the main Res Sup panel. Range, Auto timing and sidechain options stay
in the Details drawer above it.

## Start with what you hear

| What the track needs | Reach for | Try it on |
| --- | --- | --- |
| A lasting change in tone | **EQ** | Low-mid cleanup, bass weight, vocal presence or a brighter top end |
| Control when a frequency gets too loud | **Dynamics** | Boomy bass notes, louder vocal phrases or a synth that gets harsh |
| Control over individual resonant peaks | **Res Sup** | Ringing vocals, guitars, sustained synths and narrow peaks in a busy sound |

Each band has its own frequency, gain, Q, shape and channel controls. Use
Dynamics or Res Sup on its own, or enable both for **Dynamics → Res Sup** inside
the band. Your regular EQ gain remains available alongside them.

### Get a band working

1. Double-click empty spectrum space to add a band, then drag its node to find
   the area you want to treat. Scroll to adjust the selected band's main Q.
2. Choose a shape from **Shape** or right-click the node. Bell is a useful
   starting point for a focused resonance problem.
3. Enable Res Sup and lower **Amount** below zero to hear suppression. Amount
   starts at 0%, which is neutral; positive values boost the detected peaks.
4. Open Details and choose a modest **Range**, such as −6 dB. Adjust Threshold
   and Selectivity while listening to the affected phrase or note.
5. Use **Delta** briefly to hear the correction, then turn it off. Use
   **Loudness Match** and Bypass to compare at a similar listening level.

Hold **Shift** for finer adjustments. Numeric fields accept typed values;
double-click a control to reset it. **Delete / Backspace** removes the selected
band. Disabled bands keep their settings until deleted. New instances open with
an empty EQ, ready for you to add bands.

### The Res Sup controls by ear

| Control | What it changes |
| --- | --- |
| **Threshold** | When peaks qualify for treatment. Set it together with Soft or Hard and the material you are playing. |
| **Amount** | Direction and strength: negative cuts, zero is neutral, positive boosts. |
| **Range** | The maximum correction available to the band. Start gently and increase as needed. |
| **Peak Limit** | How many qualifying peaks can be treated. Lower it for a few dominant resonances; raise it for denser material. |
| **Main Q** | The selected EQ shape's width; for Bell, it also defines the central Res Sup working area. |
| **Res Sup Q** | Width of the individual corrections: lower is broader, higher is narrower. Bell processing still stays focused within the main Q region. |
| **Attack / Release** | How quickly the correction enters and recovers. Auto timing adapts to the resonance frequency. |

Res Sup can follow up to **512 resonance points per band**, depending on how many
Res Sup bands are active and how well the peaks can be distinguished. With
**All Pass**, resonance detection covers the full spectrum. Shelf, cut, Notch,
Band Pass and Tilt shapes guide treatment according to their selected region.

### Shapes and stereo control

Choose Bell, Low Shelf, Low Cut, High Shelf, High Cut, Notch, Band Pass, Tilt
Shelf, Flat Tilt or All Pass. Cut slopes range from gentle filtering to
Brickwall. Right-click a node for quick access to the curve choices.

Use **Stereo, Left, Right, Mid, Side or Mid/Side** to choose where a band works.
The bar below Gain balances its correction between L/R or Mid/Side without
changing the original stereo balance of the track.

## Make room for two tracks

Put Ressup-EQ on both tracks, open **Instances** in the header and name the
instances after their tracks. Select the other track and enable Compare to
show both spectra. Orange highlights point out frequency regions where the two
Post signals compete. Listen before cutting: some overlap belongs in the mix.

Use the **MAIN / named-instance** selector to adjust either track from the same
window. Editing a reference changes that track's actual EQ and is saved with
its instance. Try this for kick and bass, lead vocal and guitars, or layered
synths. The display itself does not apply automatic cuts.

A band's **sidechain source** separately chooses what drives Dynamics and
Res Sup: its own input, the DAW's external sidechain, or another live Ressup-EQ
instance. Sidechain filters focus what the detector hears. Use matching plug-in
versions when working with multiple connected instances.

## See the sound and compare fairly

**Pre / Post** show the input and output spectra. **Side** shows the stereo
side content. **Freeze** holds spectral peaks so you can inspect a frequency and
click to add a band there. Click the **Q** label to show the selected band's width.

The gear menu adjusts analyzer Resolution, Minimum and Speed. These are display
choices and do not add audio latency. **Save as default** remembers your preferred
view for new instances; **Reset default** returns it to the factory view.

**Mix** blends processed and original audio. Input and Output trims help you
manage level; **Loudness Match** helps you judge the tonal change at a similar
loudness. Leave headroom when boosting. Fold the parameter panel with its lower
arrow when you want more room for the spectrum.

## Choose the processing quality

| Mode | When to try it |
| --- | --- |
| **Zero latency** | Recording, playing instruments and responsive mixing. Start at Detail 0. |
| **Natural** | An alternative oversampled sound for tonal shaping. Compare it by ear. |
| **Linear** | Linear-phase processing when that behaviour suits the source or mix. |

**Detail 0–5** changes audio precision. Higher settings can separate closer peaks
and refine narrow corrections, but use more CPU and can add latency. It is
independent of the analyzer display's Resolution. Realtime and Offline choices
let you set the detector quality for playback and export separately. If Offline
is set to Realtime, export follows your playback choice.

## Presets

The folder icon before Pre opens **20 factory presets**, your saved presets,
Open, Save and Show preset folder. Factory presets cover vocals, drums, bass,
guitars, piano, synths, strings, speech and mix/master starting points. Adjust
Amount, Range and Threshold to your recording rather than relying on a preset
unchanged. The older-project compatibility warning above also applies to older
presets.

## Download and install

Choose your format, extract the ZIP and copy the plug-in to the folder below.
Close the DAW before replacing a version, then reopen it and rescan if needed.
Copy the **entire VST3 or AU bundle**; on Linux, copy **Ressup-EQ.clap**.
The AU works without a separate VST3 installation.

| Download | Requirements | Installation folder |
| --- | --- | --- |
| [Mac VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.27.2/Ressup-EQ-1.27.2-macOS-AppleSilicon-VST3.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/VST3/` |
| [Mac AU](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.27.2/Ressup-EQ-1.27.2-macOS-AppleSilicon-AU.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/Components/` |
| [Windows VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.27.2/Ressup-EQ-1.27.2-Windows-x64-VST3.zip) | Windows 10/11, x64 | `C:\Program Files\Common Files\VST3\` |
| [Linux CLAP](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.27.2/Ressup-EQ-1.27.2-clap.1-Linux-x86_64-CLAP.zip) | Linux x86-64, glibc 2.35+ (Ubuntu 22.04+), X11/XWayland | `~/.clap/` |

On Linux, create `~/.clap/` if needed and use a CLAP-compatible DAW. Standard
fontconfig, FreeType and X11 desktop libraries are required. On Wayland, the
DAW must host the editor through X11/XWayland.

### macOS: step-by-step installation

You do **not** need to be a developer, install Xcode or have an Apple Developer
account to use Ressup-EQ. You need **macOS 14 or later** and a Mac with an
**Apple Silicon chip (M series)**. These downloads do not support Intel Macs.
Check your Mac in **Apple menu > About This Mac**.

#### 1. Download and copy the plug-in

1. Quit your DAW completely before installing or updating.
2. Download **Mac AU** from the table above for **Logic Pro or GarageBand**.
   For **Ableton Live, REAPER or another VST3 host**, choose **Mac VST3**.
   The AU works on its own; installing both formats is optional.
3. Double-click the downloaded ZIP in Finder to extract it. Keep the entire
   `Ressup-EQ.component` or `Ressup-EQ.vst3` item together; do not open its
   contents or copy only the files inside it. It is a plug-in loaded by your
   DAW, so double-clicking it does not launch an app.
4. In Finder, press **Shift + Command + G** (**Go > Go to Folder**), paste the
   destination for your format and press Return:

   | Format | Copy this item | Destination |
   | --- | --- | --- |
   | AU | `Ressup-EQ.component` | `~/Library/Audio/Plug-Ins/Components/` |
   | VST3 | `Ressup-EQ.vst3` | `~/Library/Audio/Plug-Ins/VST3/` |

   Keep the `~` at the start: it selects your own user Library. If the folder
   does not exist, go to `~/Library/` and create the missing `Audio`, `Plug-Ins`
   and `Components` or `VST3` folders with **File > New Folder**.
5. Drag the extracted plug-in into that folder. If updating, replace the old
   item. Use the same installation location as before to avoid duplicate copies.

#### 2. If macOS blocks the plug-in

**These builds are not signed with an Apple Developer ID certificate and are
not notarized by Apple.** They have an **ad-hoc (local) signature**, which does
not certify the developer's identity. macOS may therefore block the downloaded
plug-in or say that the developer cannot be verified. This is separate from
whether the plug-in passes audio validation.

Use the following steps only for a download from the
[official Ressup-EQ releases](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases)
that you choose to trust.

First, open your DAW and let it scan the plug-in. If macOS displays a security
warning, dismiss it and open **System Settings > Privacy & Security**. If an
**Open Anyway** button appears for Ressup-EQ, click it, authenticate if asked,
and confirm. Reopen the DAW and rescan. Apple explains this option in
[Safely open apps on your Mac](https://support.apple.com/en-us/102445).

If there is no **Open Anyway** option for the plug-in, you can remove its
download quarantine flag with Terminal:

1. Quit the DAW again. Make sure you have already copied the plug-in to the
   user Library folder in step 1.
2. Press **Command + Space**, type **Terminal**, and press Return.
3. Copy and paste the command for the format you installed, then press Return.
   If you installed both formats, run each command separately.

**For AU:**

```sh
xattr -dr com.apple.quarantine "$HOME/Library/Audio/Plug-Ins/Components/Ressup-EQ.component"
```

**For VST3:**

```sh
xattr -dr com.apple.quarantine "$HOME/Library/Audio/Plug-Ins/VST3/Ressup-EQ.vst3"
```

These commands target only the named Ressup-EQ plug-in and its contents. They
remove the download quarantine flag; they do not add an Apple signature or
notarization. No administrator password or developer tools are required for
these user Library paths. Do not disable Gatekeeper for the whole Mac.

Terminal normally returns to the prompt without a success message. If it says
**No such file**, check that the plug-in is in the exact folder shown above.
If it reports that `com.apple.quarantine` is not present, that flag is already
absent. If an error persists, download and extract a fresh copy from the official
release and check your Mac's compatibility before trying again.

#### 3. Find Ressup-EQ in your DAW

Reopen the DAW and rescan its plug-ins if needed. Look for **Ressup-EQ** under
**Valla Productions**.

- **Logic Pro:** open **Logic Pro > Settings > Plug-in Manager**, select
  Ressup-EQ and click **Reset & Rescan Selection**. See
  [Apple's Plug-in Manager guide](https://support.apple.com/guide/logicpro/lgcp9e26ef17/mac).
- **GarageBand:** reopen it after installing the AU. If the new AU is still
  missing, restart the Mac and check the Audio Units menu again.
- **Ableton Live:** in **Settings/Preferences > Plug-Ins**, enable **Use VST3
  Plug-In System Folders** for VST3, or **Use Audio Units** for AU, then rescan.
  See [Ableton's macOS plug-in guide](https://help.ableton.com/hc/en-us/articles/209068929-Using-AU-and-VST-plug-ins-on-macOS).
- **Other VST3 hosts:** enable VST3 scanning and rescan the installation folder.
  Run an Apple Silicon version of the host natively for this arm64 VST3 build.

If the AU still does not appear, restart your Mac once and repeat the scan.
If macOS reports the plug-in as damaged, try a fresh official download first;
that message alone does not establish that quarantine is the cause.

### Validation and checksums

Mac VST3 and AU pass their format validators and audio/editor tests. Windows x64
is checked for the correct architecture and dependencies, with editor regression
tests under Wine. Linux CLAP is checked with audio/editor tests, the CLAP
validator and a REAPER load/render test in an Ubuntu 22.04 x86-64 environment.
Native Windows DAW testing and performance on physical Windows/Linux systems
remain separate from these checks.

File checksums are in [SHA256SUMS.txt](SHA256SUMS.txt). Keep the accompanying
licenses with the plug-in package.

## Credits and license

Created by **Francesco Valla · Valla Productions**.
Original Ressup-EQ software and documentation are [proprietary](LICENSE).
© 2026 Francesco Valla. All Rights Reserved. Use requires express authorization
under this license or a separate written agreement. Third-party components
retain their own licenses; see [Third-Party Notices](THIRD_PARTY_NOTICES.md).
