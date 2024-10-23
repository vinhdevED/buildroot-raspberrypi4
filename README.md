# Minimal Embedded OS into Raspberry Pi 4
Using Buildroot to build a minimal embedded OS which will deploy into Raspberry Pi 4 to do some task with Wifi Connection - Camera - Qt Application.

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
  <img src="https://github.com/vinhdevED/buildroot-raspberrypi4/blob/main/Image/buildroot_config.png" alt="Buildroot Configuration" width="1000"/>
</div> 

This will allow you to configure the buildroot for your target architecture. By going through each submenu, you can choose suitable option which you want.
But in this time, I use an alternative config from Buildroot. It provides config files for some popular boards, these default config files do all the basic configuration for me. I use this command below to list all.

```
make list-defconfigs
```
