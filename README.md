# OpenCore-EFI for ASUS ROG (X570) Crosshair VIII Impact

**Current macOS version:** 13.5.1 (22G90) \
**Current OpenCore version:** 0.9.4

## System Information

| **Component** | **Model**                             |
| ------------- | ------------------------------------- |
| CPU           | AMD Ryzen™ 9 5900X                    |
| Motherboard   | ASUS ROG (X570) Crosshair VIII Impact |
| RAM           | G.SKILL Trident Z Neo 32GB (2x16GB)   |
| GPU           | AMD Radeon™ RX 6800 XT                |
| Audio         | ASUS ROG SupremeFX8-Channel S1220     |
| Ethernet      | Intel® I211-AT                        |
| Wireless      | Intel® Wi-Fi 6 AX200                  |
| Storage       | Samsung 860 PRO SATA 2.5" SSD 1TB     |

## What works

- Stable operation (No random crashes, panics, etc.)
- External Audio (Microphone & Headphones connected to DAC)
- USB Ports (All external ports are mapped + Bluetooth & Wi-Fi, RGB Header & Internal USB C Header)
- DRM (Netflix, Apple TV+, Amazon Prime Video, etc.)
- iServices (iMessage, FaceTime, App Store, etc.)
- Sleep/Wake
- Wi-Fi & Bluetooth (Handoff, AirDrop, etc.)
- CPU Power Management
- GPU Hardware Acceleration
- FileVault
- UEFI Secure Boot (see efikeys)
- OpenCore GUI (OpenCanopy) + Picker GUI
- Dual Booting Windows 11 (AMD RAID 0 on 2x Samsung 980 PRO PCIe® 4.0 NVMe® SSD 1TB)

## What doesn't work

- Ethernet (Intel® I211-AT) is possible with AppleIGB.kext, but it's not stable
- Internal audio (ASUS ROG SupremeFX8-Channel S1220) is possible with AppleALC.kext, but I don't need it

## EFI Setup

- OpenCore.efi ([Acidanthera](https://github.com/acidanthera/OpenCorePkg/))
- BOOTx64.efi ([Acidanthera](https://github.com/acidanthera/OpenCorePkg/))

### Drivers

- OpenRuntime.efi ([Acidanthera](https://github.com/acidanthera/OpenCorePkg/))
- OpenCanopy.efi ([Acidanthera](https://github.com/acidanthera/OpenCorePkg/))
- HfsPlus.efi ([Apple](https://developer.apple.com/))
- ResetNvramEntry.efi ([Acidanthera](https://github.com/acidanthera/OpenCorePkg/))

### Tools

- OpenShell.efi ([Acidanthera](https://github.com/acidanthera/OpenCorePkg/))

### Kexts

- Lilu.kext ([Acidanthera](https://github.com/acidanthera/Lilu))
- VirtualSMC.kext ([Acidanthera](https://github.com/acidanthera/VirtualSMC))
- WhateverGreen.kext ([Acidanthera](https://github.com/acidanthera/WhateverGreen))
- NVMeFix.kext ([Acidanthera](https://github.com/acidanthera/NVMeFix))
- PortMap.kext ([XLNC](https://github.com/naveenkrdy))
- AirportItlwm.kext ([OpenIntelWireless](https://github.com/OpenIntelWireless/itlwm))
- IntelBTPatcher.kext + IntelBluetoothFirmware.kext ([OpenIntelWireless](https://github.com/OpenIntelWireless/IntelBluetoothFirmware))
- BlueToolFixup.kext ([Acidanthera](https://github.com/acidanthera/BrcmPatchRAM))
- AppleMCEReporterDisabler.kext ([XLNC](https://github.com/naveenkrdy))
- RestrictEvents.kext ([Acidanthera](https://github.com/acidanthera/RestrictEvents))
- AMDRyzenCPUPowerManagement.kext + SMCAMDProcessor.kext ([trulyspinach](https://github.com/trulyspinach/SMCAMDProcessor))
- RadeonSensor.kext + SMCRadeonGPU.kext ([ChefKissInc](https://github.com/ChefKissInc/RadeonSensor))

## Tools used

- OCAuxiliaryTools ([ic005k](https://github.com/ic005k/OCAuxiliaryTools)) - For updating OpenCore and validating config.plist.
- AMD Vanilla OpenCore ([Shanee, XLNC, dhinakg](https://github.com/AMD-OSX/AMD_Vanilla)) - AMD Patches to run macOS on AMD CPUs.
- SSDTTime ([CorpNewt](https://github.com/corpnewt/SSDTTime)) - Generating SSDT-EC.aml and SSDT-USBX.aml.
- USBMap ([CorpNewt](https://github.com/corpnewt/USBMap)) - Discovering USB ports.
- MaciASL ([acidanthera](https://github.com/acidanthera/MaciASL)) - Editing ACPI.
- Hackintool ([benbaker76](https://github.com/benbaker76/Hackintool)) - For device information.

## Guides used

- [OpenCore Configuration](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html)
- [OpenCore Post-Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [OpenCore UEFI Secure Boot](https://github.com/perez987/OpenCore-and-UEFI-Secure-Boot)

## Credits

- [Apple](https://apple.com) for macOS
- [AMD-OSX Developers](https://github.com/AMD-OSX) for kernel patches for AMD CPUs
- [Acidanthera](https://github.com/acidanthera) for OpenCore and most of used kexts
- [ic005k](https://github.com/ic005k) for OCAuxiliaryTools
- [benbaker76](https://github.com/benbaker76) for Hackintool
- [Shanee](https://github.com/Shaneee) for patches for AMD CPUs and work on AppleIGB.kext which I didn't use here.
- [Trulyspinach](https://github.com/trulyspinach) for Ryzen power management and monitoring kexts
- [XLNC](https://github.com/naveenkrdy) for patches for AMD CPUs, AppleMCEReportedDisabler kext and a bunch of troubleshooting help!
- [Pavo](https://github.com/Pavo-IM) for research about AppleMCEReportedDisabler in Monterey
- [CorpNewt](https://github.com/corpnewt) for SSDTTime and USBMap
- [OpenIntelWireless developers](https://github.com/OpenIntelWireless) for AirportItlwm and IntelBluetoothFirmware kexts
- [ChefKissInc](https://github.com/ChefKissInc) for RadeonSensor and SMCRadeonGPU
- [perez987, profzei, khronokernel, sakaki](https://github.com/perez987) for work on UEFI Secure Boot and guide
- [Dortania](https://github.com/dortania) for OpenCore configuration guides
- [AMD-OSX Community](https://amd-osx.com) for support while making my Hackintosh
