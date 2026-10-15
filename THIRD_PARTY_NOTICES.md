# Ressup-EQ — Third-Party Notices

Ressup-EQ is created by **Francesco Valla** and published under the
**Valla Productions** manufacturer name.

The original Ressup-EQ software and documentation are proprietary and subject
to the license in `LICENSE`. Copyright (c) 2026 Francesco Valla.
All Rights Reserved. The repository contains compiled plug-ins, an interface
screenshot and documentation; source code is not included.

The proprietary license for original software does not replace the licenses of the
third-party components included in the compiled plug-ins.

## JUCE Framework 9.0.3

Copyright (c) Raw Material Software Limited.
These builds use the commercial JUCE licence (JUCE Starter, as confirmed
by the product author). The framework is separately dual-licensed under
the commercial JUCE licence or AGPLv3. JUCE remains subject to its own licence.

The upstream framework notice is preserved in `licenses/JUCE-LICENSE.md`.
Notices for bundled third-party libraries are preserved in
`licenses/JUCE-THIRD-PARTY-LICENSES.txt`. The upstream dependency inventory
is included as `licenses/JUCE.spdx.json`.

## Steinberg VST3 SDK 3.8.1

MIT License. Copyright (c) 2026 Steinberg Media Technologies GmbH.
The complete license is preserved in `licenses/VST3-SDK-LICENSE.txt`.
The Audio Unit build uses Steinberg's VST3-to-AU wrapper and embeds the
same VST3 audio engine as the standalone VST3 plug-in.

## CLAP SDK (Linux CLAP build)

MIT License. Copyright (c) 2021 Alexandre BIQUE.
SDK revision: `a47f6badb49d948fd009998f28309cdab78979c9`, headers 1.2.10.
The complete license is preserved in `licenses/CLAP-SDK-LICENSE.txt`.
The native Linux CLAP build does not link the Steinberg or Apple SDKs.

## Apple AudioUnitSDK (Audio Unit build)

Copyright (c) Apple Inc. and the AudioUnitSDK project authors.
Apache License 2.0. The complete license is preserved in
`licenses/AudioUnitSDK-LICENSE.txt`. System Apple frameworks are provided
by macOS and are not redistributed as separate libraries.

## Windows system libraries

The Windows x64 build uses the release Microsoft Visual C++ runtime and
Windows SDK import libraries. Windows system DLLs are supplied by Windows;
SDK headers, development libraries and build tools are not distributed.

The macOS and Windows plug-in bundles include their applicable license
documents in `Contents/Resources/licenses`. The Linux CLAP archive includes
them in its `licenses/` directory. Copies are also provided beside the archives.
