# Ressup-EQ

**Hear where tracks compete. Make room for both.**

Kick and bass fill the same low end. A vocal gets buried when the guitars come
in. A synth turns sharp as the filter opens. Ressup-EQ helps you shape the tone,
control the moments that jump out, and see how two tracks fit together.

Use **EQ**, **Dynamics** and **Res Sup** across up to **24 bands**. Bring another
track into the analyzer, see where their frequencies overlap, and adjust either
instance's EQ from the same window while listening to the mix.

Made by **Francesco Valla · Valla Productions**.

**Version 1.24.0** · macOS Apple Silicon: VST3 / AU · Windows x64: VST3 · Linux x86-64: CLAP

**[Download Ressup-EQ](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/tag/v1.24.0)**

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

**Res Sup Density selects how many resonances are treated.** The new rotary
control runs from **0–100%**. At 0% it treats the strongest qualifying peak;
raising it gradually includes secondary peaks, up to eight at 100%. Threshold
determines which peaks qualify, Res Sup Q sets their width, and Amount sets
their direction and strength. New and restored bands default to **100%** to
retain the previous sound. Each band saves its own Density setting.

**Attack and Release set the movement.** Attack runs from **1–500 ms** and
Release from **10–2000 ms**. Leave Auto timing on as a starting point; editing
either control switches to manual timing. **(A)** beside a timing label means
automatic timing is active.

**Main Q and Res Sup Q do different jobs.** Main Q focuses the band and its
sensitivity around the chosen frequency. **Res Sup Q**, from **0.01x to 4x**,
sets the width of individual adaptive corrections: lower values are broader,
higher values narrower. Its default is **1x**. Res Sup tracks up to **eight
resonances per band**, including separately resolved peaks in notes and chords.

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
2. **Click Instances in the header, beside Compare and Mix.** The browser
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
latency. The settings are saved per instance. Click outside the menu to close it.

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
| [Mac VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.24.0/Ressup-EQ-1.24.0-macOS-AppleSilicon-VST3.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/VST3/` |
| [Mac AU](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.24.0/Ressup-EQ-1.24.0-macOS-AppleSilicon-AU.zip) | macOS 14+, Apple Silicon | `~/Library/Audio/Plug-Ins/Components/` |
| [Windows VST3](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.24.0/Ressup-EQ-1.24.0-Windows-x64-VST3.zip) | Windows 10/11, x64 | `C:\Program Files\Common Files\VST3\` |
| [Linux CLAP](https://github.com/vallaproductionsoriginal-byte/Ressup-EQ/releases/download/v1.24.0/Ressup-EQ-1.24.0-clap.1-Linux-x86_64-CLAP.zip) | Linux x86-64, glibc 2.35+ (Ubuntu 22.04+), X11/XWayland | `~/.clap/` |

On Linux, create `~/.clap/` if needed and use a CLAP-compatible DAW. Standard
fontconfig, FreeType and X11 desktop libraries are required. On Wayland, the
DAW must host the editor through X11/XWayland.

Mac builds are ad-hoc signed and are **not Apple notarized**. They are validated
with the VST3 and Audio Unit validators. Windows x64 is cross-built and checked
for architecture, version, exports and runtime dependencies; **native Windows
DAW testing remains pending**. Linux CLAP is checked with audio and editor tests,
the CLAP validator and a REAPER load/render test in an Ubuntu 22.04 x86-64
userspace running under Rosetta on the development Mac. These checks establish
functionality, rather than performance on a physical Windows or Linux machine.

The release contains **four binary packages** and checksums. Packages include
compiled plug-ins and their licenses. **Project source code is not distributed.**
File checksums are in [SHA256SUMS.txt](SHA256SUMS.txt).

## Credits and license

Created by **Francesco Valla · Valla Productions**.
Original Ressup-EQ software and documentation are [proprietary](LICENSE).
© 2026 Francesco Valla. All Rights Reserved. Use requires express authorization
under this license or a separate written agreement. Third-party components
retain their own licenses; see [Third-Party Notices](THIRD_PARTY_NOTICES.md).
