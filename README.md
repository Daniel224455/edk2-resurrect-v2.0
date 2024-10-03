# EDK2 Resurrect v2.0rc2 for SDM845 Platforms

EDK2 implementation for Snapdragon 845 platforms.

## Resources

[Support group](https://t.me/WinOnOP6)

[Windows Drivers for OnePlus 6 series](https://github.com/Daniel224455/WoA-on-OnePlus6-Series/releases/tag/Drivers)

[Install guide for OnePlus 6 series](https://github.com/Daniel224455/WoA-on-OnePlus6-Series)

[Contact if you want to add any device](https://t.me/Daniel6745)

## WARNING

**DO NOT EVER TRY TO PORT IT TO *SONY* and *GOOGLE* DEVICES**

**YOUR UFS WILL BE WIPED CLEAN!!!**

## Supported devices

[Windows Status Spreadsheet](https://docs.google.com/spreadsheets/d/1oUuZ4VeFS1Lz59oMmt0uTAT6-sXvckPn9W2ELrDLQVs/edit?usp=drivesdk)

## Dependencies

For Windows/MacOS/Other Linux distributions:

Install Docker manually or use an Ubuntu virtual machine

For Ubuntu 20.04:

```bash
sudo apt update
sudo apt upgrade
sudo apt install build-essential uuid-dev iasl git nasm gcc-aarch64-linux-gnu python3-distutils python3-pil python3-git gettext fastboot
```

## Building

1.Clone this project

```bash
git clone https://github.com/Daniel224455/edk2-resurrect-v2.0.git --depth=1
cd edk2-resurrect-v2.0
```

2.1 Build this project (only on linux)
NOTE : If your device has multiple ram configs, then instead of `fajita` ex. use `fajita-8g` (8gb ram config)

```bash
bash build.sh --device DEVICE
```
2.1,5 Building EDK2 as DEBUG (optional, used for debugging certain issues)
```
bash build.sh --device -r DEBUG
```

2.2 For macOS/Windows (you can use docker)

````bash
docker-compose run edk2 ./build.sh -d DEVICE
````

3.Boot the image

```bash
fastboot boot boot_DEVICE.img
```

(DEVICE is the codename of your phone.)

Additionally, you can flash the image to recovery to achieve dual-boot.

```bash
fastboot flash recovery boot_DEVICE.img
```

## Credits
 
`Daniel6745` for fixing/resurrecting v2.0rc2 edk2-msm source

`fxsheep` for his original `edk2-sagit`

`strongtz` for maintaining Renegade Project

`BigfootACA` for build script

`Lemon_Ice` and `NTAuthority` for guidance and some blobs

`@Freak2112`, `TAO_Croatia` and `废物` for working hard on testing and debugging

`NekokeCore` for fixing MemoryMap
