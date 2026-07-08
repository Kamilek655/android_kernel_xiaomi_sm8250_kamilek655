
**English:**  
The kernel source code is still under development and may cause some unpredictable problems. Please use it with caution.  

# Kamilek's Xiaomi SM8250 Kernel  

**English:**  
This repository is based on the `lineage-23.2` branch of [LineageOS/android_kernel_xiaomi_sm8250](https://github.com/LineageOS/android_kernel_xiaomi_sm8250).  

Code required for HyperOS/MIUI support, as well as some device-specific drivers, was selectively cherry-picked by comparing commit histories from [Strawing's repo](https://github.com/liyafe1997/kernel_xiaomi_sm8250_mod), which in turn sources changes from [UtsavBalar1231's repo](https://github.com/UtsavBalar1231/kernel_xiaomi_sm8250) and [Xiaomi_Kernel_OpenSource](https://github.com/MiCode/Xiaomi_Kernel_OpenSource).  

This kernel stands on the shoulders of giants, combining contributions from multiple upstreams to make it as practical and well-rounded as possible.  

---

## 特性 / Features

**English:**  
This kernel supports [ReSukiSU](https://github.com/ReSukiSU/ReSukiSU) (based on [SukiSU Ultra](https://github.com/SukiSU-Ultra/SukiSU-Ultra), a fork of KernelSU with KPM support) & [SuSFS](https://gitlab.com/simonpunk/susfs4ksu).  
Please install the ReSukiSU Manager by yourself.  
The NoKernelSU version supports Magisk and APatch (and their forks).  

The prebuilt kernel in the **Release** section is compiled from the `android16-aptusitu-new` branch, and should work on stock MIUI/HyperOS as well as third-party AOSP-based ROMs for Android 11–16.  
Feedback is welcome (via Issues or Pull Requests)! Coolapk users can join the discussion in [this post](https://www.coolapk.com/feed/69700122), you can also join my QQ group, or send me private feedback.  

Below are some of the key features:  
1. Support for USB serial drivers (CH340 / FTDI / PL2303 / OTI6858 / TI / SPCP8X5 / QT2 / UPD78F0730 / CP210X)  
2. Support for CAN bus and USB CAN adapters (e.g. CANable)  
3. F2FS with realtime discard enabled for improved flash TRIM behavior  
4. Support for EROFS  
5. zRAM with support for multiple compression algorithms, including LZ4, LZ4HC, lz4k_oplus, LZ4KD, and ZSTD  
6. Backported BPF from Linux 5.10 (Android 16 compatible)  
7. Touchscreen, camera, audio, GPU/DRM/MSM, and CNSS2 drivers use Xiaomi-specific implementations (sourced from UtsavBalar1231’s repository and MiCode. The AOSP version of the Display/DRM driver is the LineageOS version); also, the `double_tap` node has been added to the touchscreen driver  
8. Fixes [the issue where the battery percentage gets stuck at 1%](https://github.com/liyafe1997/Xiaomi-fix-battery-one-percent), and supports recognizing higher-capacity replacement batteries  
9. Integrate [BBG(Baseband-guard)](https://github.com/vc-teahouse/Baseband-guard)  

---

**English:**  
**Note**: The kernel zip package **contains** `dtbo.img`, but it will **not** flash your dtbo partition by default.  
It is recommended to use the stock `dtbo`, or one from the bundled files of a third-party ROM (if the original author confirms it works well).  
The `dtbo.img` built from this source has some issues—for example, on the lock screen, the display may suddenly flash to max brightness when trying to turn off the screen.  
If you have flashed other third-party kernels or encounter strange issues, please check whether your `dtbo` has been replaced.  

**Warning**: If you are using HyperOS/MIUI, please flash the **MIUI version**.  
The AOSP version has different display drivers, which will cause the screen not to display properly on HyperOS/MIUI.  
If you get a black screen after flashing, check if you are on HyperOS/MIUI but flashed the AOSP version.  
Feedback about this specific issue will not be accepted by default.  

---

 Supported Devices
|  Codename  |  Device Name            |
|---------------------|-----------------------------------|
| psyche              | Xiaomi 12X                        |
| thyme               | Xiaomi 10S                        |
| umi                 | Xiaomi 10                         |
| munch               | Redmi K40S / POCO F4              |
| lmi                 | Redmi K30 Pro / POCO F2 Pro       |
| cmi                 | Xiaomi 10 Pro                     |
| cas                 | Xiaomi 10 Ultra                   |
| apollo              | Xiaomi 10T / Redmi K30S Ultra     |
| alioth              | Xiaomi 11X / POCO F3 / Redmi K40  |
| elish               | Xiaomi Pad 5 Pro                  |
| enuma               | Xiaomi Pad 5 Pro 5G               |
| dagu                | Xiaomi Pad 5 Pro 12.4             |
| pipa                | Xiaomi Pad 6                      |

---
