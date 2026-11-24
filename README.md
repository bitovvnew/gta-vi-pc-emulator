# GTA 6 PC Emulator

![Illustrated Ocean Drive at sunset — winter preview cover](assets/ocean-drive.jpg)

**Windows development preview**　·　[Performance](#performance-profile)　·　[Hardware](#hardware-and-settings)　·　[Compatibility](#gameplay-compatibility)　·　[Windows release](#windows-release)

The winter preview tracks an independent effort to run Grand Theft Auto VI on PC. The maintainer’s latest estimate puts gameplay coverage at **roughly 17%**. The reference profile targets **60 FPS at native 2560 × 1440 on a GeForce RTX 4070**. A public frame-time capture for that profile is pending.

| Gameplay coverage | Graphics target | Render scale | Windows build |
| :--- | :--- | :--- | :--- |
| ~17% · maintainer estimate | 1440p / 60 FPS | 100% native | Winter preview planned |

## Performance profile

At native 1440p, a single frame contains **3,686,400 output pixels**. At 60 frames per second, the renderer has **16.67 ms per frame**. The profile keeps upscaling and frame generation disabled so the capture can report how frequently the application presents a rendered frame.

### Frame-time reference

These figures come from dividing 1,000 milliseconds by the frame rate. They provide a scale for reading a future capture.

| Frame rate | Time per frame at steady pacing | Difference from the 60 FPS budget |
| ---: | ---: | ---: |
| 30 FPS | 33.33 ms | 16.67 ms over |
| 40 FPS | 25.00 ms | 8.33 ms over |
| 50 FPS | 20.00 ms | 3.33 ms over |
| **60 FPS** | **16.67 ms** | **On budget** |
| 90 FPS | 11.11 ms | 5.56 ms under |
| 120 FPS | 8.33 ms | 8.33 ms under |

A 50 ms frame occupies the time of three evenly paced frames at 60 FPS. That hitch can be visible in a camera pan even when the average FPS for the whole route stays near 60. The benchmark sheet therefore pairs average FPS with the 99th-percentile frame time.

### Resolution reference

| Output resolution | Pixels per frame | Relative to native 1440p | Output pixels per second at 60 FPS |
| :--- | ---: | ---: | ---: |
| 1920 × 1080 | 2.07 million | 56.25% | 124.42 million |
| **2560 × 1440** | **3.69 million** | **100%** | **221.18 million** |
| 3840 × 2160 | 8.29 million | 225% | 497.66 million |

The table counts output pixels. Actual GPU cost also depends on scene complexity, materials, shadows and post-processing. A resolution change alone cannot predict the frame rate of the development build.

## Hardware and settings

| Component or setting | Reference profile |
| :--- | :--- |
| Platform | Windows PC |
| Graphics card | NVIDIA GeForce RTX 4070 |
| Internal render dimensions | 2560 × 1440 |
| Display output | 2560 × 1440 |
| Resolution scaling | 100% |
| Upscaling / frame generation | Off / off |
| Performance objective | Approximately 60 rendered FPS |
| CPU, system memory, graphics driver | To be recorded with the first published capture |
| Minimum and recommended PC specifications | Pending tests across multiple systems |

The [machine-readable RTX 4070 profile](profiles/rtx-4070-native-1440p.json) stores the target and measured FPS in separate fields. The measured value stays empty until a capture is available.

## Gameplay compatibility

The **17% figure** is the maintainer’s estimate of how much gameplay currently runs. Its scope is still open: the repository does not yet identify a mission list, a test route or a denominator. Readers can use the following proposed checks to interpret the next compatibility update.

| Proposed test | What a passing report would document |
| :--- | :--- |
| Start a session | Build ID, starting state and the point where player input becomes available |
| Traverse the world | A named route, travel time and any stalls or missing assets |
| Complete a mission | Mission identifier, checkpoints reached and completion trigger |
| Resume from a save | Save location, restored mission state and response to the first player input |
| Repeat the run | Whether the same build reaches the same endpoint on a second attempt |

## Benchmark procedure

1. **Record the system.** Include the CPU, RAM, GPU, driver, Windows version and build identifier. Record any frame cap or VSync setting.
2. **Fix the route.** Use the same save, starting position, camera direction and endpoint. Keep loading screens outside the timed interval unless loading is the subject of the test.
3. **Separate the first pass from repeat passes.** Record one cold run and three repeat runs. Retain each capture so a smooth repeat pass cannot hide a first-pass stall.
4. **Report frame pacing.** For each pass, list the capture duration, average FPS and 99th-percentile frame time. Attach the raw frame times and identify where the largest hitch occurred.

A reader should be able to select a build, repeat the route and compare the same interval. The [benchmark report template](BENCHMARK.md) provides the fields for a submission.

## Windows release

**Coming in winter.** The first official executable from this independent project is planned for Windows. The exact date, build number and download are pending. The [release preview](releases/README.md) tracks packaging status.

| Available now | Purpose |
| :--- | :--- |
| [Target profile](profiles/rtx-4070-native-1440p.json) | Inspect the native 1440p settings |
| [Benchmark sheet](BENCHMARK.md) | Prepare a reproducible performance report |
| [Release notes](releases/README.md) | Check the Windows build status |

*Independent fan project. Unaffiliated with Rockstar Games or Take-Two Interactive. The cover is original concept art.*
