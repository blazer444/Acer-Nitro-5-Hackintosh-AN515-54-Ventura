# Acer-Nitro-5-Hackintosh-AN515-54-Ventura
Acer Nitro 5 Hackintosh AN515-54 Ventura OpenCore 0.9.3
macOS Ventura on Acer Nitro 5 AN515-54 with OpenCore 0.9.3 EFI folder.

# macOS Ventura : version 13.6.1

The project was made from scratch with the help of [Opencore - Dortania Guide](https://dortania.github.io/OpenCore-Install-Guide/). A huge thanks to the awesome community for the documantation.

`Opencore Version : 0.9.3`

<img src="https://github.com/blazer444/Acer-Nitro-5-Hackintosh-AN515-54-Ventura/blob/main/screenshot.png" alt="macOS Ventura">

## Configuration

| Specifications      | Details                                            |
| ------------------- | -------------------------------------------------- |
| Laptop Model        | AN515-54 574Q                                      |
| Processor           | Intel® Core™ i5-9300H                              |
| Graphics            | Intel® UHD Graphics 630 & Nvidia GeForce® GTX 1650 |
| RAM                 | 8GB DDR4-2666Mhz                                   |
| Disk                | KINGSTON RBUSNS8154P3512GJ1 512gb                  |
| Audio               | Realtek HD Audio ALC255                            |
| Wifi                | Intel Wi-Fi 6 AX200 160MHz                         |
| Ethernet            | RealTek RTL8168/8111 PCI-E Gigabit Ethernet        |

## What's working

- [x] Audio (Input & Output)
- [x] iGPU
- [x] ACPI Display brightness
- [x] Ethernet
- [x] Sleep + Wake
- [x] Smart Touchpad + Gestures
- [x] WiFi (2.4Ghz and 5GHz)
- [x] Native hotkey support with Fn keys
- [x] iServices (Messages, FaceTime, etc.)

## What's not working

- [ ] GTX 1650 (macOS does not support recent Nvidia GPUs).
- [ ] HDMI port (since it's connected to the GTX 1650).

## Important Note
- THIS IS ILLEGAL USE IN PERSONAL ONLY!!!
- Set SATA mode to AHCI (Use CTRL+S in BIOS to unhide SATA Mode menu)
- Disable Secure Boot
- Generate new SMBIOS (https://github.com/corpnewt/GenSMBIOS) - Optional

## Installation

### First-time installation

- Set-up the BIOS configuration:
  - Boot to BIOS by pressing F2 during boot.
  - In the Main screen, enable F12 boot menu, disable Fast Boot, then press Ctrl+S and change the new SATA mode option to AHCI.
  - In the Boot screen, disable secure boot.
  - Finally, go to the Exit screen and select "Exit saving changes".
- Read through the following tutorial to create a bootable USB, and then place the EFI folder inside it:
   - https://dortania.github.io/OpenCore-Install-Guide/
- You should add Serial Number, UUID, MLB and ROM details to Config -> PlatformInfo -> Generic if you want to get iServices working as explained [here](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html).

### Post Install

- Clone the [ComboJack repo](https://github.com/hackintosh-stuff/ComboJack) and run the installer inside the `ComboJack_Installer` folder to get the jack port working correctly.
- Run the following commands for sleep wake:
  ```
  sudo pmset -a hibernatemode 0
  sudo pmset -a autopoweroff 0
  sudo pmset -a standby 0
  sudo pmset -a proximitywake 0
  ```
- If dual-booting with Windows, follow [this](https://www.tonymacx86.com/threads/fix-incorrect-time-in-windows-osx-dual-boot.133719/) guide to fix time.

## Disable CFG Lock (Advanced users only)

To disable CFG Lock, follow [this](https://www.reddit.com/r/hackintosh/comments/hz2rtm/cfg_lockunlocking_alternative_method/) guide. Note that you'll be modifying the BIOS, so be very careful or you could end up bricking your device. If you're not sure about something, do NOT do it.

After following the guide, disable Kernel -> Quirks -> AppleXcpmCfgLock and you're done.

## Credits

- Thanks to [Hoang63X](https://github.com/Hoang63X/AN515-54-51X1-Hackintosh) for providing their configuration, which helped me solve various issues.
- Thanks to [Acidanthera](https://github.com/acidanthera) for providing [AppleALC](https://github.com/acidanthera/AppleALC), [AppleSupportPkg](https://github.com/acidanthera/AppleSupportPkg),  [Lilu](https://github.com/acidanthera/Lilu), [OcBinaryData](https://github.com/acidanthera/OcBinaryData), [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg), [VirtualSMC](https://github.com/acidanthera/VirtualSMC), [VoodooInput](https://github.com/acidanthera/VoodooInput), [VoodooPS2](https://github.com/acidanthera/VoodooPS2), and [WhateverGreen](https://github.com/acidanthera/WhateverGreen).
- Thanks to [alexandred](https://github.com/alexandred) for providing [VoodooI2C](https://github.com/alexandred/VoodooI2C).
- Thanks to [Sniki](https://github.com/Sniki) for providing [OS-X-USB-Inject-All](https://github.com/Sniki/OS-X-USB-Inject-All).
- Thanks to [corpnewt](https://github.com/corpnewt) for providing [USBMap](https://github.com/corpnewt/USBMap) and [ProperTree](https://github.com/corpnewt/ProperTree).
- Thanks to [zxystd](https://github.com/zxystd) for providing [itlwm](https://github.com/OpenIntelWireless/itlwm) and [IntelBluetoothFirmware](https://github.com/zxystd/IntelBluetoothFirmware).
