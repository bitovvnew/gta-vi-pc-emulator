# GTA 6 PC Emulator

![Ocean Drive at sunset, illustrated for the winter preview](assets/ocean-drive.jpg)

**Winter preview · Independent PC emulation project**

The first Windows executable is planned for winter. This preview follows two milestones closely: how far gameplay runs in the development build, and whether the RTX 4070 can maintain a 16.67 ms frame budget at native 1440p.

## From the development build

The project maintainer reports that **roughly 17% of gameplay currently runs**. The estimate comes from internal testing. The exact missions, route, and counting method behind it have yet to be documented. A compatibility report with named gameplay sections would let readers see where play continues and where it stops.

## The native 1440p profile

| Graphics card | Render resolution | Render scale | Frame-rate target |
| :--- | :--- | :--- | :--- |
| NVIDIA GeForce RTX 4070 | 2560 × 1440 | 100% | ≈60 FPS |

The profile sets both the internal render resolution and the display resolution to 2560 × 1440. Upscaling and frame generation are disabled. At 60 FPS, each frame has about 16.67 milliseconds to finish. A capture that includes frame times as well as average FPS can show whether driving through a busy intersection introduces stutter even when the average stays close to target.

The [benchmark template](BENCHMARK.md) has space for the build identifier, driver version, test route, capture duration, and raw frame-time data. A measured result for this profile is still pending.

## Windows release

**Soon… Coming in winter.** The project’s first official Windows build is planned as an `.exe`. A download and an exact release date are pending. For now, the files below document the planned build and the settings used to define its performance target.

| Project file | What’s inside |
| :--- | :--- |
| [Windows release preview](releases/README.md) | Packaging status and the winter release window |
| [RTX 4070 target profile](profiles/rtx-4070-native-1440p.json) | Resolution, render scale, and frame-rate target |
| [Benchmark report](BENCHMARK.md) | A reusable capture sheet for comparing builds on the same route |

*GTA 6 PC Emulator is an independent fan project, unaffiliated with Rockstar Games or Take-Two Interactive. The cover is original concept art.*
