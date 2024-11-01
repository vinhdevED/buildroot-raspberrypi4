# Minimal Embedded OS into Raspberry Pi 4
Using Buildroot to build a minimal embedded OS which will deploy into Raspberry Pi 4 to do some task with Wifi Connection - Camera - Qt Application with Capacitve Touch Screen.

# Requirement
+ Raspberry Pi 4
+ SD Reader
+ SD Card (32GB)
+ Ubuntu (Host build / Storage >30GB / Virtual / Real)
  
# Buildroot Config
Buildroot is a generic build system hence in order to build Linux for Raspberry Pi I need to configure. In order to configure buildroot for my board I start the configuration utility by entering
```
make menuconfig
```
<div align="center">
  <img src="https://github.com/vinhdevED/buildroot-raspberrypi4/blob/main/Image/buildroot_config.png" alt="Buildroot Configuration" width="800"/>
</div> 

This will allow you to configure the buildroot for your target architecture. By going through each submenu, you can choose suitable option which you want.
But in this time, I use an alternative config from Buildroot. It provides config files for some popular boards, these default config files do all the basic configuration for me. I use this command below to list all.

```
make list-defconfigs
```

<div align="center">
  <img src="https://github.com/vinhdevED/buildroot-raspberrypi4/blob/main/Image/list-config.png" alt="Buildroot Configuration" width="800"/>
</div> 

I apply default setting for Raspberry Pi 4 (64 bit), just type 

```
make raspberrypi4_64_defconfig
```
The first thing I need to enable root login and set the root password _(This is an important factor for accessing through SSH connection)_. 
After that, I will list some requirement need to set up for embeddedOS
+ Qt5 (All packages of Qt5)
+ OpenSSH
+ Graphic Driver (VDR4-VC3)
+ Raspberry Pi TS(Touch Screen) in **linux-menuconfig**

When finishing needed config, I use **make** command line for going to the final step before it generates some folders of booting section.
```
make
```
The output folder will be generated which contains some important file.
<div align="center">
  <img src="https://github.com/vinhdevED/buildroot-raspberrypi4/blob/main/Image/output_folder.png" width="800"/>
</div> 
Next, I put file wpa_supplicant.conf into this path output/usr/etc/ to enable Wireless Connection.
And make again !!! 

# Booting Result
