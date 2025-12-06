# Ubuntu Touch device tree for Xiaomi Mi 8 Pro (equuleus)

This is based on Halium 9.0, and uses the mechanism described in [this page](https://github.com/ubports/porting-notes/wiki/GitLab-CI-builds-for-devices-based-on-halium_arm64-(Halium-9)).(Now available for use in GitHub Actions)

You can download the ready-made artifacts from gitlab: take the [latest archive](https://github.com/ubports-dipper/xiaomi-dipper/suites/4028909010/artifacts/101927864e), unpack the `OTA images.zip` file (make sure that all files are created inside a directory called `out/`, then follow the instructions in the [Install](#install) section
You can apply patches yourself, just use [script](https://github.com/istadem2077/simg2zip).

Or you can use installable ZIP archives from Releases. Just install it as any other Custom ROM. Do a full wipe and format data (WARNING!! ALL DATA WILL BE LOST, FORMATTING DATA IS NECESSARY IF YOU ARE DOWNGRADING FROM ANDROID 10 OR HIGHER), and install zip. Don't install Magisk, it wont work here, and may even destroy your system. Firmware and Vendor are already packed in zip so no need to additionally install vendor+fw.

## Pre-requisites

As this is based on Android 9, it is required to install stock vendor.img from Android 9. You can Android 9 stock firmware from [Xiaomi Firmware Updater](https://xiaomifirmwareupdater.com/). [GLOBAL](https://github.com/TryHardDood/mi-vendor-updater/releases/download/equuleus_global-stable/fw-vendor_equuleus_miui_MI8UDGlobal_V11.0.5.0.PECMIXM_390eb435f5_9.0.zip), [CHINA](https://github.com/TryHardDood/mi-vendor-updater/releases/download/equuleus-stable/fw-vendor_equuleus_miui_MI8UD_V11.0.3.0.PECCNXM_88e4eae066_9.0.zip)

Copy these images to directory `out/` above together with the artifacts.

## Install

```bash
fastboot flash boot out/boot.img
fastboot flash recovery out/recovery.img
fastboot flash system out/system.img
```

