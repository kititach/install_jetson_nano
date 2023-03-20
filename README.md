# How to install Jetson Nano

- 1 install OS Ubuntu 18.04
- 2 install SDK Manager Nvidia on Ubuntu
- 3 Use jumper caps or Dupont wires to short-circuit the FC REC and GND pins
- 4 Plug USB Jetson Nano in Ubuntu

```
ls -l
df -k
```

## Tutorial Jetson Nano
- https://www.waveshare.com/wiki/JETSON-NANO-DEV-KIT#Method_One:_Adopt_SDK_Manager_Tool
- https://www.waveshare.com/wiki/JETSON-NANO-DEV-KIT#Overview

## Boot from USB : Tutorial https://www.forecr.io/blogs/bsp-development/change-root-file-system-to-sd-card-directly
### Step1
```
sudo jetson_clocks
gnome-disks
```

### Step2
- Create a new partition from SD card storage.
- Format the disk as ext4 format (partition size is up to you but must be min current file system’s size).


### Step3
```
sudo ./change_rootfs_storage_direct-emmc_to_sdmmc.sh /dev/sda1
sudo reboot
```
