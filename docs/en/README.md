# AE-1.20-UI Multi-module adaptation

An Applied Energistics-style UI resource pack for Minecraft 1.20.x (`pack_format` 15), providing a unified AE-style interface for multiple mods while optimizing the text and texture display effects of the UI.

This repository maintains the pack originally created by LeeQianXi as [AE-Light-UI Multi-module](https://www.curseforge.com/minecraft/texture-packs/ae-light-ui-multi-module), and is released under LGPLv3.

We have added AE-style UIs for a large number of mods, available in both light and dark versions, such as:
- **Applied Energistics 2** and its addons
- **Sophisticated Storage / Core**
- **GregTech Modern** and **GTOCore**
- **Farmer's Delight**
- **Avaritia**
- ……See "Adapted Mods" below for the complete list.

## Versions
- Supports Minecraft 1.20.x (`pack_format` 15)
- Light (`LightMode`) and Dark (`DarkMode`) variants
- The version number lives in the `VERSION` file at the repository root; release artifacts are tagged by CI from that file

## Core Features
1. **Dual-style UI Resources**
   Provides two UI resource packs: `LightMode` and `DarkMode`, catering to different players' visual preferences.
2. **Multi-mod Compatibility**
   Adds AE-style interface adaptations for multiple popular Minecraft mods, covering survival, storage, and tech mods, ensuring visual consistency across different mod interfaces.
3. **UI Detail Optimization**
   Includes UI text corrections and texture fixes, repairing display flaws in some mod UIs to enhance the interface's aesthetics and readability.
4. **Modpack-specific Adaptation**
   Specially adapted for the [GregTech-Odyssey (GTO)](https://gtodyssey.com) modpack, perfectly compatible with the mod environment of this modpack.
5. **Lightweight Adaptation**
   Only modifies UI-related resources without affecting the core functional logic of the mods, fully compatible with the original functions of the mods.

## Installation and Usage
1. **Obtain the Resource Pack**
   You can download `AE-Light-UI-<version>.zip` / `AE-Dark-UI-<version>.zip` from the Releases page of the repository, or clone the repository and package it locally:
    ```bash
    git clone https://github.com/GregTech-Odyssey/AE-1.20-UI.git
    cd ./AE-1.20-UI
    git switch gto            # GTO-adapted build; use master-1.20.1 for the base pack
    cd scripts && bash pack.sh  # produces LightMode.zip and DarkMode.zip under pack/ at the repo root
    ```
    > `pack.sh` requires the `zip` command (available on Linux / macOS; on Windows, zip the `LightMode/` and `DarkMode/` folders with 7-Zip or similar).
2. **Installation Steps**
    - Place the downloaded or packaged zip (or the `LightMode/` and `DarkMode/` folders) into the `resourcepacks` directory of Minecraft
    - Launch Minecraft, in the "Options → Resource Packs" interface, move this resource pack to the top of the resource pack list
    - After applying the resource pack, you can experience the AE-style UI interface

## Adapted Mods
More than 70 mod namespaces are covered (`LightMode/assets/` has 75 entries and `DarkMode/assets/` 76, `minecraft` included), mainly:

- **AE2 and its addons**: Applied Energistics 2, Advanced AE, ExtendedAE, Expanded AE, ExtendedAE Plus, MEGA Cells, AE2WTLib, AE2 Things, AE2 Additions, AE2 Network Analyser, AppFlux, AppMek, AppliedE, ME Requester, etc.
- **Storage**: Sophisticated Storage / Sophisticated Core / Sophisticated Backpacks, Functional Storage
- **Tech and magic**: GregTech Modern, GTOCore, Botania, MythicBotany, ArsEng (Ars Énergistique)
- **Tools and UI**: JEI, EMI, FTB Quests, Building Gadgets 2, LaserIO, Pipez, Modular Routers, Chisel Reborn, Apotheosis, Curios, Crafting Tweaks, Travel Anchors, Touhou Little Maid, etc.

For the complete list, see the namespace directories under `LightMode/assets/` and `DarkMode/assets/`.

## Directory Structure Description
```Plain
AE-1.20-UI/
├── docs/              # Repository documentation (Chinese / English)
├── LightMode/         # Light theme UI resources, containing all interface textures and configurations under this theme
├── DarkMode/          # Dark theme UI resources, containing all interface textures and configurations under this theme
├── Tool/              # Pixel replacement tooling used for texture creation
├── scripts/           # Script files related to resource pack building (pack.sh)
├── .github/           # CI: tags releases from VERSION after a PR merge, plus CLA and PR-body checks
├── VERSION            # Current version number
├── CONTRIBUTING.md    # Contribution guide
├── LICENSE            # License (LGPLv3)
└── README.md          # Project quick description document
```

## Adapted Modpacks
- **GregTech-Odyssey (GTO)**: Specially adapted for this modpack, this resource pack can be used directly in this modpack to obtain a unified AE-style interface experience.
  - Artifacts from the `gto` branch already merge the GTO overlay pack — enabling this single pack is enough, the base pack is no longer needed.
  - The base pack (`master-1.20.1` branch) does not include GTO-specific interfaces; GTO players should use the artifacts from the `gto` branch.

## Notes
1. This resource pack needs to be placed at the top of the resource pack list, otherwise its UI effects may be overwritten by other resource packs
2. This resource pack is incompatible with other AE-style UI resource packs, please disable other UI resource packs of the same type when using
3. Only supports Minecraft 1.20.x (`pack_format` 15), not compatible with other versions of the Minecraft client

## Contribution
If you want to participate in the development of this project, adapt AE-style UIs for more mods, or feedback UI display issues, you are welcome to participate through the following ways:
1. Submit issue feedback, feature suggestions, or propose mods to be adapted later on the Issues page of the repository
2. Fork the repository and submit a Pull Request to contribute your adaptation content
3. Before opening a PR, please read [CONTRIBUTING.md](CONTRIBUTING.md); PRs in this repository must sign the CLA and pass the PR body check
