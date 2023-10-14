# Hackintosh for 13900K, Z690 AORUS ELITE DDR5 and RX 6600XT

## System Overview
![neofetch](https://i.imgur.com/uxOoz2a.jpg)

### System Configuration
- **Motherboard:** GIGABYTE Z690 Aorus Elite DDR5
- **CPU:** Intel Core i9-13900K
- **GPU:** AMD RX 6600XT
- **RAM:** Kingston Fury Beast Black 64GB 5200MHz DDR5
- **Storage:** WD Black SN850X 2TB PCIe Gen4 x4 NVMe M.2
- **Wireless Card:** ASUS PCE-AX3000
- **Ethernet:** Realtek RTL8125B PCI Express 2.5 Gigabit Ethernet
- **Additional Hardware:** 
    - **Cooling:** Noctua NH-D15 
    - **2nd GPU:** GIGABYTE GeForce RTX 3080Ti GAMING OC 12G (disabled for dual boot with Windows 11)
    
## Software Requirements
### Operating System
- **macOS:** macOS Sonoma (14.0 23A344)
- **SMBIOS**: iMacPro1,1 with dual boots macOS and Windows 11
### Bootloader
- **Bootloader Software:** OpenCore 0.9.6 MOD
## Tools
Don't be an idiot and use these great tools instead of wasting your time with propertree or other plist editors:
- [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/) - easy `config.plist` management
  - [OpenCore Auxiliary Tools](https://github.com/ic005k/QtOpenCoreConfig) - alternative
- [Hackintool](https://github.com/headkaze/Hackintool/releases) - debug and map USB ports

> **Warning** 
> 
> Use the [modded OpenCore version](https://gitee.com/btwise/OpenCore_NO_ACPI) to prevent Windows thinking you're running in BootCamp and creating multiple issues around ACPI. Why isn't this the default OC behaviour is beyond me.

## Get it running
1. Make sure to update your BIOS, disable CSM support and secure boot, enable XHCI Hand-off (for Airdrop/Continuity/Sidecar) and enable XMP.
2. Create an macOS Ventura USB-Installer Stick, install OpenCore and copy my EFI folder ([how?](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/))
3. Generate a new serial number, motherboard id, ROM (that's your motherboard's mac address without dots) and SMUUID (make sure serial number is **invalid** in order to iMessage/Facetime to work) ([how?](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#platforminfo))
4. Boot the new macOS partition
5. Copy the EFI to the local disk

> **Note** 
> 
> Enable HiDPI Display settings by running `sudo defaults write /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled -bool true` and rebooting the PC

Here are some [tips and tricks](https://github.com/5T33Z0/OC-Little-Translated/tree/main/A_Config_Tips_and_Tricks) and the full [OpenCore Documentation](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html)

## What works
- macOS Sonoma
- WiFi and Bluetooth + Airdrop + Sidecar + Continuity
- Audio
- HDMI/DP (with VRR)
- Most USB ports (Capped at macOS limit of 15)
- Everything iCloud related (Drive, iMessage, FaceTime, unlock with Apple Watch, etc)
- Intel Quick Sync (if you enable iGPU in BIOS)
- Temperature monitoring
- Resizable Bar Support (enable Above 4G Decoding in BIOS)
- Update to newer macOS builds over time

## What doesn't work
- Wake for sleep (temporary to disable sleep mode on macOS)

## Port mapping
Both USB 3.0 ports and USB-C port of the case (front), all USB 2.0 ports, another 3 USB 3.0 ports (first ones coming down) + USB-C port on motherboard. Create your own mapping on Windows using [USBToolBox](https://github.com/USBToolBox/tool)

## Thanks/Credits
- insanelymac
- tonymacx86
- rursache
