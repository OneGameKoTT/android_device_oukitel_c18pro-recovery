
[![Compiling status](https://github.com/OneGameKoTT/android_device_oukitel_c18pro-pbrp/actions/workflows/ci.yml/badge.svg?branch=android-10.0)](https://github.com/OneGameKoTT/android_device_oukitel_c18pro-pbrp/actions/workflows/ci.yml)

Basic | Spec Sheet
-------:|:-------------------------
SoC | MediaTek MT6757CD Helio P25
CPU | 64-bit, 2.5 GHz Octa-core, Cortex-A53
GPU | ARM Mali T-880 MP2
Shipped Android Version | AOSP 10.0

## Device picture

![Oukitel C18 Pro](https://www.oukitelmobile.com/wp-content/uploads/2020/06/oukitel-c18-pro-rugged-smartphone-23.jpg "Oukitel C18 Pro")


## Sync and Build manually
---------------

To get started with building Recovery, you'll need to get
familiar with [Git and Repo](https://source.android.com/source/using-repo.html).

To initialize your local repository to build Recovery, use a command like this:

```bash
repo init -u https://github.com/SHRP/manifest.git -b v3_10.0
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
git clone https://github.com/OneGameKoTT/android_device_oukitel_c18pro-recovery --depth=1 device/oukitel/c18pro
```

## Then to build
```bash
cd <source-dir>
. build/envsetup.sh
lunch omni_c18pro-eng && mka recoveryimage
```

## To test it
```
fastboot flash recovery out/target/product/c18pro/recovery.img
```

