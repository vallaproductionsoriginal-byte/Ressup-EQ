# Ressup-EQ

**Hear where tracks compete. Make room for both.**

Kick and bass fill the same low end. A vocal gets buried when the guitars come
in. A synth turns sharp as the filter opens. Ressup-EQ helps you shape the tone,
control the moments that jump out, and see how two tracks fit together.

Use **EQ**, **Dynamics** and **Res Sup** across up to **24 bands**. Bring another
track into the analyzer, see where their frequencies overlap, and adjust either
instance's EQ from the same window while listening to the mix.

Made by **Francesco Valla · Valla Productions**.

**Version 1.26.2** · macOS Apple Silicon: VST3 / AU · Windows x64: VST3 · Linux x86-64: CLAP

**[Download Ressup-EQ](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/tag/v1.26.2)**

**Installing on Mac?** Follow the [step-by-step Mac guide](#macos-step-by-step-installation),
including help with macOS security warnings.

![Ressup-EQ with Pre and Post spectra, the combined EQ response, numbered band nodes and the channel balance bar below Gain](images/ressup-eq.png)

*One window for tone, dynamic control and resonance suppression, with more room
for the spectrum and the selected band's controls close at hand.*

## Start with what you hear

| What the track needs | Reach for | Try it on |
| --- | --- | --- |
| A lasting change in tone | **EQ** | Low-mid cleanup, bass weight, vocal presence or a brighter top end |
| Control when a frequency gets too loud | **Dynamics** | Boomy bass notes, louder vocal phrases or a synth that gets harsh as it opens up |
| Control over individual resonant peaks | **Res Sup** | Ringing vocals, sustained synths or narrow peaks inside a busy sound |

Each band has its own frequency, gain, Q, curve, slope and channel controls.
Use either adaptive stage on its own, or enable both with **Dynamics → Res Sup**
processing inside the band. Your regular EQ gain stays available alongside them.

Normal bands process in series, in band-number order. A Low Cut followed by a
High Cut keeps the frequencies between the cutoffs. Solo lets you hear the
selected band's contribution while finding the area you want to change.

## Get a band working in a few moves

1. **Find the area.** Double-click empty spectrum space to add a band. Drag its
   node for frequency and gain. With a band selected, scroll anywhere in the
   plug-in to adjust its Q; the pointer can be away from its node.
2. **Choose the curve.** Right-click the node to open the compact curve menu,
   or use **Shape** in the parameter panel. The menus show an icon beside each
   curve; the spectrum keeps simple numbered nodes.
3. **Choose how it reacts.** Leave the band as regular EQ, enable Dynamics,
   enable Res Sup, or turn both on.
4. **Set the direction.** Negative **Res Sup Amount** cuts; positive Amount
   boosts. Amount starts at **0%**, so move it below zero to hear suppression.
   Dynamics uses its own signed **Density**, starting at **−100%**.
5. **Set a useful limit.** Open Details and choose a modest Range, such as
   **−6 dB**. Raise Threshold while listening, then adjust Amount for Res Sup
   or Density for Dynamics. In Res Sup, lower the new **Density** knob to
   concentrate on fewer dominant resonances.
6. **Compare at a similar level.** Use Loudness Match beside Output, then Bypass
   to compare the processed and original signal.

Hold **Shift** for finer dragging and wheel moves. Numeric fields accept typed
values, including frequencies in kHz. Double-click a control to reset it.
Click a node to select its band and show its controls. Click empty spectrum
space to deselect and hide the parameter panel. Use **Delete / Backspace** or
the bin icon to remove the selected band. Disabled bands stay gray and selectable, retain their settings and
reserve their slots until you delete them.

New instances open with an empty EQ: no bands, no selected parameter panel,
unity Input/Output and 100% Mix. Opening a saved project restores its own state.

The **folder icon before Pre** opens the preset menu. **Factory (20 presets)**
contains Init and starting points for vocals, drums, bass, guitars, piano,
synths, strings, spoken voice and mix/master processing. **Open preset...**
loads `.rseq` files (and legacy `.rsp` files); **Save preset as...** saves the
current local instance as `.rseq`. **Show preset folder** opens the directory.
Saving or loading a preset uses the local instance, even while a reference is
selected for editing. Loading replaces the EQ, including clearing unused bands.

Factory files are created in the `Factory` subfolder when the menu is first
opened. Existing files are preserved. User presets saved directly in the preset
folder also appear in the menu.

| System | User preset folder |
| --- | --- |
| macOS | `~/Library/Audio/Presets/Valla Productions/Ressup-EQ/` |
| Windows | `%APPDATA%\Valla Productions\Ressup-EQ\Presets\` |
| Linux | `$XDG_DATA_HOME/valla-productions/ressup-eq/presets/`, default `~/.local/share/valla-productions/ressup-eq/presets/` |

The lower arrow folds the parameter panel to its band number, Enable, Solo and
Delete controls. The upper handle opens **Details** for Range, sidechain filters,
Auto timing and External SC. Folding the panel keeps the sound and node positions
in place, and selecting another band keeps your chosen panel layout.

## Choose the shape that fits

**Bell, Low Shelf, Low Cut, High Shelf, High Cut, Notch, Band Pass, Tilt Shelf,
Flat Tilt and All Pass** cover broad tone changes, narrow cleanup and phase work.
Frequency runs from **10 Hz to 30 kHz**, band Gain from **−30 to +30 dB**, and
main Q from **0.05 to 40**.

Cut slopes include **0, 6, 12, 24, 48 and 96 dB/oct**, plus **Brickwall**.
0 dB/oct is neutral; Brickwall is a finite **192 dB/oct** approximation.
Linear mode uses a finite FIR, so higher Detail can resolve sharp transitions
and narrow corrections more closely.

Turn on **Curve suggetion** in the gear menu to choose an initial curve from the
insertion frequency:

| Where you add the band | Initial curve |
| --- | --- |
| Below **50 Hz** | **Low Cut** / high-pass |
| **50–250 Hz** | **Low Shelf** |
| Above **250 Hz**, through **12.5 kHz** | **Bell** |
| Above **12.5 kHz**, through **17.5 kHz** | **High Shelf** |
| Above **17.5 kHz** | **High Cut** / low-pass |

The option starts off and is saved with the instance. It applies when inserting
a band, including from a Freeze peak. You can choose another curve afterward;
moving an existing band leaves its curve in place.

## Decide where the band works

Choose **Stereo, Left, Right, Mid or Side** in Channel. Use Mid for the centre
of a stereo sound, or Side for its wider part. **Mid/Side** gives you a paired
balance between those two components.

The small bar below **Gain** distributes that band's processing continuously
between **L/R** or **Mid/Side**. At the centre, both receive the full effect.
Move toward one end to reduce the correction on the other component; at an end,
only the chosen component is processed. The percentages describe the relative
share: **25% L / 75% R** gives the left one third of the right's processed
contribution, with the stronger side kept at full strength. This changes the
band's correction while leaving the original signal's stereo balance in place.
Double-click the bar to return to the centre.

## Let Dynamics and Res Sup work together

On a vocal, use Dynamics to contain an upper-mid build-up on louder words,
then let Res Sup work on individual ringing peaks within that area. The internal
Res Sup detector accounts for the change made by Dynamics. External sidechain
uses its routed source instead.

When both stages are active, **Edit: Dynamics / Edit: Res Sup** chooses which
stage's controls you are adjusting: **Threshold, Amount and Density** for Res Sup,
or **Threshold and Density** for Dynamics. Each stage remembers its own values.
**Range, Attack, Release and Auto timing are shared** within the band.

**Range sets the available depth.** It runs from **0 to −72 dB**, with new bands
starting at **−32 dB**. Start closer to zero and increase the depth as you listen.

**Threshold sets when and how much.** Higher percentages let quieter material
trigger the processing and increase the available action. At full negative
Amount (or Dynamics Density), **Range −6 dB + Threshold 50%** allows up to
**3 dB of cut**. The amount you hear also depends on the signal and the band's
sensitivity. Positive Amount uses the same limit for boosts. Dynamics spans trigger levels from 0 to −60 dBFS;
Res Sup spans 0 to −75 dBFS.

**Res Sup Amount decides direction and strength.** It runs from **−100% to
+100%**: negative attenuates, zero is neutral, and positive boosts. Dynamics
retains its signed Density control. Overlapping adaptive corrections stay within
the band's limit. The existing Res Sup automation parameter keeps its original
name, **Res Sup Density**, and its original values.

**Res Sup Density selects how many resonances are treated.** The rotary control
runs from **0–100%**. At 0% it treats the strongest qualifying peak; raising it
includes more peaks up to the current per-band capacity. That capacity adapts
to the number of enabled bands with Res Sup switched on:

| Active Res Sup bands | Control points per band at Density 100% |
| --- | --- |
| 1 | **512** |
| 2–3 | **384** |
| 4–6 | **256** |
| 7–12 | **128** |
| 13–24 | **64** |

Disabled bands are excluded. An enabled band with Res Sup switched on still
counts when Amount is 0%. The capacity is a maximum; the signal and Threshold
determine how many resonances qualify. New bands default to **100%** Density;
each band saves its own setting. Projects saved with state version 16 or earlier
and `.rsp` presets up to format 13 retain the established Density conversion
(old 100% becomes approximately 11.11%). Parameter IDs and state positions stay
unchanged. Existing Density automation keeps its saved percentages; rescale it
if you need the older selection budget at the new capacity.

**The selected curve shapes Res Sup sensitivity.** Shape remains available
with Res Sup enabled. **All Pass** gives uniform sensitivity across the full
frequency range. **Bell** focuses around the chosen frequency. **Low Shelf**
and **High Shelf** focus toward their respective sides; **Low Cut, High Cut,
Notch and Band Pass** follow their filter passbands, including the cut slope.
**Tilt Shelf** and **Flat Tilt** follow the tilt direction set by Gain; zero Gain
gives uniform sensitivity. Res Sup still corrects the resonances it detects.

**Attack and Release set the movement.** Attack runs from **1–500 ms** and
Release from **10–2000 ms**. Leave Auto timing on as a starting point; editing
either control switches to manual timing. **(A)** beside a timing label means
automatic timing is active.

**Main Q and Res Sup Q do different jobs.** Main Q controls the selected
curve, including its transition or focus around the chosen frequency.
**Res Sup Q**, from **0.01x to 4x**,
sets the width of individual adaptive corrections: lower values are broader,
higher values narrower. Its default is **1x**. Res Sup tracks up to **512
resonances per band** with one active band, including separately resolved peaks
in notes and chords. The table above shows the capacity for larger setups.

In Details, the **sidechain source menu** selects what triggers that band's
Dynamics and Res Sup. Its first entry, **External SC**, uses the plug-in's
sidechain input routed by the DAW, in mono or stereo. **MAIN** uses the band's
own input. The remaining entries use the named live instances' Post audio,
including instances with closed editors or in another host process. Each band
chooses independently of the comparison display. A stopped or closed source
releases the processing. **SC filter**, **SC Low** and **SC High** focus what the
detector listens to without filtering the main audio path. Instance audio is
buffered by a host block; scheduling between tracks or hosts can add delay.

## Make room for kick and bass from one window

1. **Put Ressup-EQ on both tracks and play the section together.** Open the
   bass instance with the kick running through its own instance.
2. **Click the Instances icon in the header, beside Compare and Mix.** The browser
   lists **External sidechain**, then **Main**, then the other live instances.
   Each has a spectrum and applied EQ preview. Give instances track names so
   the kick, bass and other parts are easy to find.
3. **Select the kick and enable Compare.** Its spectrum overlays the bass
   spectrum. Orange vertical highlights grow wider and stronger where the
   two Post signals compete for the same frequencies.
4. **Choose which track should own that area.** Listen for the kick's weight
   and the bass's body. The highlights give you a place to investigate;
   overlapping energy can also be exactly what the arrangement needs.
5. **Shape either EQ from this window.** Use the selector beside **Instances**
   to choose **MAIN** or a named reference directly. Main stays green; the reference
   is brick-coloured. Clicking a node also selects the instance to edit. Drag,
   change Q, use its band controls, or add and delete bands while listening.

**Editing Reference changes that track's actual EQ and sound.** Those settings
are saved with the target instance, including when its editor is closed.
The competition display itself applies no cuts or automatic ducking.

| Tracks | Listen for | Try |
| --- | --- | --- |
| **Kick + bass** | A low end that gets heavy or loses definition | Keep the weight of one part and shape the other around it. |
| **Lead vocal + guitars or pads** | Words getting buried when the arrangement fills out | Compare the presence area and adjust the backing part's reference EQ. |
| **Synth layers** | A harsh or crowded region when layers combine | Decide which layer needs that character, then shape the other. |
| **Backing vocals + lead** | Extra thickness hiding the lead | Compare low mids and presence before choosing where to make room. |

To compare audio without another Ressup-EQ instance, route it to the external
sidechain input and choose **External sidechain** in Instances. That source
provides comparison audio. To edit another track's EQ, select its Ressup-EQ
instance as the reference. A band's sidechain source menu controls its detector
separately.

Instances are discoverable across formats and host processes for the same user,
including with closed editors, up to **128 live instances**. Other open DAW
projects can appear too. Use matching plug-in versions for instance exchange.
Names, comparison selections and each band's instance sidechain sources are
saved in the project. Connections restore automatically, including when the DAW
loads the source instances later or in a different order. Each instance has a
saved identity; temporary host IDs can change without renaming it or breaking
the chain. Duplicating a live instance creates a separate identity.
Projects saved with older versions have no instance names or connections in
their state: assign them once and save again with this version.
Turning Compare off returns editing to Main. If a reference closes, its
highlights clear and editing returns to Main.

## Use the analyzer to support your ears

**Pre and Post** show the live mono sum of the stereo input and output.
**Side** shows the input stereo difference, useful for seeing what happens away
from the centre. Side and the external sidechain input remain separate signals.

The wide logarithmic grid includes frequency subdivisions and a **dBFS scale
on the right**. The spectrum and EQ response use independent vertical mappings.
One combined response includes EQ, Mix and live Dynamics and Res Sup corrections.
Deep responses continue outside the view; Input and Output trims change your
listening level without moving the response away from the band settings.

Click the **Q** label to show or hide the selected band's shaded width projection.
Red means visible. At zero gain, a dashed guide keeps the width readable without
changing the sound. The projection also works for disabled and reference bands.

**Freeze** remembers Post spectral maxima while the live analyzer keeps moving.
Up to twelve prominent peaks are marked. Hover near a peak, including an unmarked
local maximum, to read its frequency; click to add a band there. Turning Freeze
off clears the memory.

Open the **gear icon** to adjust the view:

| Setting | Use it for |
| --- | --- |
| **Resolution: 1024–65536 samples (64k)** | Distinguish closely spaced frequencies, especially in the low end. Default: **16384**. |
| **Minimum: 0–120 dB below 0 dBFS** | Choose how far down the spectrum you can see. Default **100** shows **0 to −100 dBFS**. |
| **Speed: Very Slow → Very Fast** | Slow the rise and fall for an easier trace to read, or follow changes more closely. |
| **Curve suggetion** | Choose the initial curve from the frequency where you insert a band. |

Analyzer resolution, minimum and speed affect the display without adding audio
latency. The settings are saved per instance. **Save as default** remembers
Resolution, Minimum, Speed and Curve suggestion for newly inserted instances,
across plugin formats. **Reset default** restores factory settings in the current
instance and removes saved startup preferences. Bands and audio controls are
excluded from these defaults. Click outside the menu to close it.

Defaults are stored in `~/Library/Application Support/Valla Productions/Ressup-EQ/`
on macOS, `%APPDATA%\Valla Productions\Ressup-EQ\` on Windows, and
`$XDG_CONFIG_HOME/Valla Productions/Ressup-EQ/` on Linux (default `~/.config/`).

## Judge changes at a similar level

Use **Input** and **Output**, each **−24 to +24 dB**, to manage levels, and
**Mix** to blend processed and original audio for parallel treatment.

**Loudness Match** adjusts the output toward the input's momentary loudness using
K-weighting and a **400 ms** window. It includes EQ, Mix and trims in the comparison,
accounts for plug-in latency, and leaves your manual Output setting in place.
Its transient guard prevents an old large compensation from suddenly amplifying
content after a spectral change. Use **Bypass** to hear the latency-aligned
original. Mix 0% also uses the original delayed dry signal.

Automation and band edits use short smooth transitions. EQ and trims have no
permanent output limiter or clipper, so leave headroom for boosts.

## Pick a processing mode for the session

| Mode | Use it for |
| --- | --- |
| **Zero latency** | IIR equalization. Start at **Detail 0** for recording and responsive instrument playing. |
| **Natural** | 2× oversampled IIR processing with symmetric resampling filters. Compare it by ear as you shape the tone. |
| **Linear** | Symmetric linear-phase FIR processing. Try higher Detail for narrower corrections and sharper transitions. |

**Detail 0–5** changes processing precision. Higher settings refine resonance
analysis, use more CPU and can add latency. This is independent of the analyzer's
Resolution setting. New instances start at Detail 0.

The DAW receives the actual processing latency for compensation. At **48 kHz**,
Linear reports **8,704 samples at Detail 0** and **17,408 at Detail 1–5**.
Natural reports **49 samples at Detail 0** and **561 at Detail 1–5**.
Changing Phase or Detail can require the host to reconfigure its delay compensation.

Very narrow or deep Linear filters have finite frequency resolution; the main
and comparison curves show the applied FIR response. For heavy 24-band Linear
configurations at maximum Detail, start with a host buffer of **128 samples or
more** and check the headroom available in your complete session.

## Download and install

Choose your format, extract the ZIP and copy the plug-in to the folder below.
Close the DAW before replacing a version, then reopen it and rescan if needed.
Copy the **entire VST3 or AU bundle**; on Linux, copy **Ressup-EQ.clap**.
The AU includes its engine and works without a separate VST3 installation.

| Download | Requirements | Installation folder |
| --- | --- | --- |
| [Mac VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.26.2/Ressup-EQ-1.26.2-macOS-AppleSilicon-VST3.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/VST3/` |
| [Mac AU](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.26.2/Ressup-EQ-1.26.2-macOS-AppleSilicon-AU.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/Components/` |
| [Windows VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.26.2/Ressup-EQ-1.26.2-Windows-x64-VST3.zip) | Windows 10/11, x64 | `C:\Program Files\Common Files\VST3\` |
| [Linux CLAP](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.26.2/Ressup-EQ-1.26.2-clap.1-Linux-x86_64-CLAP.zip) | Linux x86-64, glibc 2.35+ (Ubuntu 22.04+), X11/XWayland | `~/.clap/` |

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

### Package validation

The Mac builds are validated
with the VST3 and Audio Unit validators. Windows x64 is cross-built and checked
for architecture, version, exports and runtime dependencies; **native Windows
DAW testing remains pending**. Linux CLAP is checked with audio and editor tests,
the CLAP validator and a REAPER load/render test in an Ubuntu 22.04 x86-64
userspace running under Rosetta on the development Mac. These checks establish
functionality, rather than performance on a physical Windows or Linux machine.

The release contains **four binary packages** and checksums. Packages include
compiled plug-ins, installation information and licenses.
File checksums are in [SHA256SUMS.txt](SHA256SUMS.txt).

## Credits and license

Created by **Francesco Valla · Valla Productions**.
Original Ressup-EQ software and documentation are [proprietary](LICENSE).
© 2026 Francesco Valla. All Rights Reserved. Use requires express authorization
under this license or a separate written agreement. Third-party components
retain their own licenses; see [Third-Party Notices](THIRD_PARTY_NOTICES.md).
