# How to install Jetson Nano

- 1 install OS Ubuntu 18.04
- 2 install SDK Manager Nvidia on Ubuntu
- 3 Use jumper caps or Dupont wires to short-circuit the FC REC and GND pins
- 4 Plug USB Jetson Nano in Ubuntu

![2023-03-22_8-43-30](https://user-images.githubusercontent.com/48780839/226781017-348926e7-7747-473e-a855-e732f126f25a.png)
![2023-03-22_8-43-51](https://user-images.githubusercontent.com/48780839/226780985-2a41d5d2-46c1-4552-a259-db4e0412cca9.png)
![2023-03-22_8-44-48](https://user-images.githubusercontent.com/48780839/226780994-fcbd8dbc-69b9-459e-990a-f461dda269f6.png)
![2023-03-22_8-47-13](https://user-images.githubusercontent.com/48780839/226781003-55abdda3-df63-4550-a3c5-f1bca5bef154.png)

```
ls -l
df -h
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
### Download
```
https://github.com/mistelektronik/forecr_blog_files/blob/master/change_rootfs_storage_direct-emmc_to_sdmmc.zip
```
```
sudo ./change_rootfs_storage_direct-emmc_to_sdmmc.sh /dev/sda1
sudo reboot
```

## How to install VNC
### Step 1
```
sudo apt install xfce4 xfce4-goodies
sudo apt install tightvncserver
vncserver
```
![2023-03-20_17-00-18](https://user-images.githubusercontent.com/48780839/226307763-f6843d25-1cd7-4077-8efc-81ddf5901137.png)

![2023-03-20_17-00-53](https://user-images.githubusercontent.com/48780839/226307791-bd8382c6-095d-4488-bfe3-920e8e3bfbb9.png)

### Step 2
```
vncserver -kill :1
mv ~/.vnc/xstartup ~/.vnc/xstartup.bak
nano ~/.vnc/xstartup
```
### Add
```
#!/bin/bash
xrdb $HOME/.Xresources
startxfce4 &
```
### Run VNC Server
```
sudo chmod +x ~/.vnc/xstartup
vncserver
```
