---
layout: default
title: Setting up your SD card
---

### What you will need

- The latest release of [Atmosphére](https://github.com/Atmosphere-NX/Atmosphere/releases/latest){: .a-table target="_blank"}. For this step, you will need the zip file and `fusee-primary.bin`.
- The latest release of [Hekate](https://github.com/ctcaer/hekate/releases/latest){: .a-table target="_blank"}
- The latest release of the [homebrew launcher](https://github.com/switchbrew/nx-hbmenu/releases/latest){: .a-table target="_blank"}.
- The latest release of [Checkpoint](https://github.com/FlagBrew/Checkpoint/releases/latest){: .a-table target="_blank"}. Download the `.nro` file.
- The latest release of [hb-appstore](https://github.com/vgmoose/hb-appstore/releases/latest){: .a-table target="_blank"}.
- [sys-ftpd.kip](https://noirscape.github.io/SwitchGuide/assets/sys-ftpd.kip){: .a-table} ([source](https://github.com/jakibaki/sys-ftpd){: .a-table target="_blank"})
- [hekate_ipl.ini](https://noirscape.github.io/SwitchGuide/assets/hekate_ipl.ini) (use Ctrl-S or Apple key-S to save this file.) Make sure this file ends in `.ini` ! Some browsers might add `.txt` to the end of this filename. If your browser does this, remove the `.txt` extension! On Windows and macOS you might need to disable hiding extensions from files. To do so, [see this wikihow](https://www.wikihow.tech/Show-File-Extensions-on-Windows). On macOS, see [this iDownloadBlog page](https://www.idownloadblog.com/2014/10/29/how-to-show-or-hide-filename-extensions-in-os-x-yosemite/).
- The latest release of [nx-hbloader](https://github.com/switchbrew/nx-hbloader/releases/latest){: .a-table}

### Setting up your sd card

1. Turn off your Switch and put your microSD card in your computer.
2. Copy the `bootloader` folder from the Hekate zip to your SD card.
3. Copy the `atmosphere` folder from the Atmosphére zip to your SD card.
4. Copy `fusee-secondary.bin` from the Atmosphére zip to the root of your SD card.
5. Copy `fusee-primary.bin` to the to the root of your SD card.
6. Copy `hbmenu.nro`from the `nx-hbmenu` release  to the root of your SD card.
7. Make a folder called `switch` on the root of your SD card.
8. Copy `checkpoint.nro` from the `Checkpoint` release to the `switch` folder.
9. Extract the `hb-appstore` zip and copy `appstore.nro` to the switch folder.
10. In the `atmosphere` folder on your SD card, place `hbl.nsp` from the `nx-hbloader` release.
11. In the `atmosphere` folder on your SD card, make a folder called `kips`.
12. If you are above firmware 3.0.0, in the `kips` folder, place `sys-ftpd.kip`. Otherwise, skip this step.
13. In the `bootloader` folder on your SD card, place `hekate_ipl.ini`.
14. Safely remove your microSD card and plug it back in your Switch.

---

### Next step

The next step depends on the platform you want to boot CFW from.

- If you plan on booting CFW from a Windows system, go [here](os-specific-preparations/windows.html){: .a-table}
- If you plan on booting CFW from a macOS or Linux system, go [here](os-specific-preparations/linux.html){: .a-table}
- If you plan on booting CFW from an Android or chromeOS device, go [here](os-specific-preparations/android.html){: .a-table}
