# OmbleAventure

An educational VR experience developed with Unreal Engine 5.4 focused on underwater exploration and marine biology, centered on the Arctic Charr (*Omble chevalier*) and its freshwater ecosystem. Developed at the UMR CARRTEL (INRAE – USMB), with support from the CSTI call (USMB), and a partnership with #ASL and #LaMaisondelaRivière.

## Overview

OmblAventure immerses users in an interactive underwater environment where they can explore aquatic habitats, discover fish species, and learn about ecological areas. The experience features:

- Detailed underwater world with dynamic water simulation
- Interactive ecological zones (spawning grounds, muddy zones, mussel beds)
- 3D models of Arctic Charr (*Omble*) and Burbot (*Lotte*) with male/female variants
- Historical shipwreck exploration elements
- Full VR interaction with grab mechanics, teleportation, and hand tracking

## Requirements

- **Unreal Engine 5.4** (download via Epic Games Launcher)
- **Windows 10/11** (primary development target; multi-platform builds supported)
- A VR headset with OpenXR support (optional — project also runs in desktop mode)
- ~3 GB of free disk space
- Git LFS installed (assets are tracked via LFS)

## Getting Started
- To launch the app, point to the Test Inra icon 
- Then, using the right joystick, point to Start and confirm (index finger button)
- The introductory text appears : read it and click A
### Clone the repository

```bash
git lfs install
git clone <repository-url>
cd INRAEOmbleAventure-main
```

### Open the project

1. Launch the **Epic Games Launcher** and ensure Unreal Engine 5.4 is installed.
2. Navigate to `TestINRAE/` and double-click `TestINRAE.uproject`.
3. If prompted to rebuild modules, click **Yes**.
4. The editor opens with the default map: `World/Map/look_Map`.

### Run in VR

1. Connect and configure your OpenXR-compatible headset.
2. In the Unreal Editor toolbar, select **VR Preview**.
3. Alternatively, package the project: **Platforms > Windows > Package Project**.

## Project Structure

```
INRAEOmbleAventure-main/
└── TestINRAE/
    ├── TestINRAE.uproject      # Project descriptor
    ├── Config/                 # Engine, input, and game configuration
    └── Content/
        ├── VRTemplate/         # VR pawn, grab system, weapons, menus
        ├── World/
        │   ├── Map/            # Game maps (OmblAventure, ShowMap, Test...)
        │   ├── Environnement/  # Wrecks, rocks, shoreline assets
        │   └── Poisson/        # Fish models (Omble, Lotte)
        ├── Characters/         # XR mannequin characters
        └── StarterContent/     # UE5 default starter assets
```

## Key Features

### Ecological Zones

Interactive information zones guide players through the habitat:

| Blueprint | Zone |
|-----------|------|
| `BP_Zone_Frayere` | Spawning ground |
| `BP_Zone_Vaseuse` | Muddy zone |
| `BP_Zone_moule` | Mussel bed |
| `BP_Zone_Lotte` | Burbot habitat |
| `BP_Zone_TropBasse` / `TropHaute` | Depth limits |
| `BP_Zone_TropLoin` | Distance limit |

### VR Interaction System

- **Grab mechanics** — Pick up and inspect objects with VR controllers
- **Teleportation** — Point-and-teleport locomotion with visual indicator
- **Hand tracking** — OpenXR hand gesture recognition (point, grasp, pinch)
- **Haptic feedback** — Controller rumble for grab and fire events
- **Menu system** — In-world widget-based UI

### Plugins Enabled

| Plugin | Purpose |
|--------|---------|
| OpenXR | Cross-platform VR/AR support |
| OpenXRHandTracking | Hand gesture input |
| OpenXREyeTracker | Eye tracking input |
| Water & WaterExtras | Dynamic water simulation |
| NiagaraFluids | Fluid particle effects |
| NaniteDisplacedMesh | High-detail mesh rendering |

## Maps

| Map | Description |
|-----|-------------|
| `OmblAventure` | Main game world |
| `look_Map` | Default startup/overview map |
| `ShowMap` | Asset showcase |
| `ShowMapWater` | Water simulation showcase |
| `DimensionTest` | Scale and dimension tests |

## Configuration

Key settings are found in `TestINRAE/Config/`:

- **DefaultEngine.ini** — Graphics (DX12/Vulkan, SM5/SM6), audio (48 kHz), and collision profiles
- **DefaultInput.ini** — Input bindings for gamepad, keyboard/mouse, and all VR controller axes
- **DefaultGame.ini** — Project name and ID


## License

For questions about use or distribution, contact the INRAE project team.
The code is open source, but users are asked to acknowledge the project's origins and the fact that it was developed with support from INRAE and USMB.



