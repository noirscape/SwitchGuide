---
layout: default
title: Final notes
---

### Dump your NAND

1. Put your Switch into RCM and boot Hekate. To do this, follow the instructions at [Launching CFW](launching-cfw){: .a-table} for your OS again, but stop at the point where it instructs you to go to `Launch`.
2. Use the volume and power buttons to select `Tools`, then select `Backup`.
3. Use the volume and power buttons to select `Backup eMMC BOOT0/1`.
4. Wait for the backup to complete. This should not take too long.
5. Press any key to return to the Hekate menu.
6. Use the volume and power buttons to select `Backup eMMC RAW GPP`.
7. For the next step, it depends on wether you have an SD card that has at least 30GB of storage free.
  - If you have an SD card that at least 30GB of storage available, you can just wait for the backup to complete. This can easily take several hours.
  - If you don't have an SD card that has at least 30GB of storage available, Hekate will make partial NAND dumps and you will need to move them to your computer during the backup. Hekate will prompt you when to do this. When it does, plug your SD card into your computer and move the `backup/(number)/rawnand.bin` files (they'll be named as `rawnand.bin.00`, `rawnand.bin.01` and so on) to a folder on your computer. After that, unplug your SD card and put it in your Switch, press any button and then select `Backup eMMC RAW GPP` again. Rinse and repeat until it says it finished.
8. Unplug your SD card and put it in your computer.
9. Move the contents of the `backup` folder to a safe folder on your computer.
10. Put your SD card back in your Switch.
11. If your SD card has had less than 30GB of space available during the backup process or your SD card was not formatted as exFAT, you will need to combine the "rawnand.bin" files. See below on how to do that.

### Combining rawnand.bin files

Note that you *cannot* restore partial NAND backups. If you need to restore a NAND backup, you will need to have an SD card that is at least 30GB in size and it must be formatted as exFAT.
{: .info-box}

1. Go to the latest release of [hekate](https://github.com/CTCaer/hekate/releases/latest){: .a-table} and download the `joiner_scripts_for_windows_linux_macos.zip` file and extract it.
2. Add `.sh` to the end of the filename of `join_15_2GBparts_linux_macosx` and `join_30_1GBparts_linux_macosx`.
3. Count how many partial dumps you have (you should have either 15 or 30 files, if you have a different amount, you are missing partial dumps) and move all the partial dumps to the folder you extracted the zip to.
4. Open the appropriate script for your system and your amount of dumps:
  - If you had 15 files and are on Windows, open the `join_15_2GBparts_windows.bat` file.
  - If you had 15 files and are on macOS/Linux, open the `join_15_2GBparts_linux_macosx.sh` script. (Note: Linux users may need to run this file from a terminal instead and mark it as executable.)
  - If you had 30 files and are on Windows, open the `join_30_1GBparts_windows.bat` file.
  - If you had 30 files and are on macOS/Linux, open the `join_30_1GBparts_linux_macosx.sh` script. (Note: Linux users may need to run this file from a terminal instead and mark it as executable.)
5. Once the script finishes running, you should have a file called `rawnand.bin` in the same folder. This file is your NAND backup.

#### About restoring NAND backups

When restoring NAND backups, you must use an exFAT filesystem! FAT32 filesystems will not work for restoring NAND backups due to size limitations on FAT32 filesystems (FAT32 cannot hold files larger than 4GB and the rawnand.bin is ~29GB). Hekate comes with it's _own_ exFAT driver. This means you do not need to install the exFAT "update" from Nintendo to restore your NAND.

### Updating Atmosphére and Hekate

To keep track of new releases of Atmosphére and Hekate, I recommend subscribing to [/r/switchhacks](https://reddit.com/r/switchhacks).

### Installing pyNX

1. Open the Homebrew Launcher.
2. Open `hb App Store` through the Homebrew Launcher.
3. Look for the program called `Pynx`.
4. Press `A`
5. Press `A` to download Pynx.
6. Press the home button to exit `hb App Store`

### Download the latest version of SwitchGuide-Updater

1. [Download switchguideupdater.py](https://github.com/noirscape/SwitchGuide-Updater/releases/latest).
2. Turn off your Switch and put your microSD card in your computer.
3. Open the `switch` folder.
4. Open the `PyNX` folder.
5. Copy `switchguideupdater.py` to this folder.
6. Safely remove your microSD card and plug it back in your Switch.
7. Boot CFW again using the instructions at [Launching CFW](/launching-cfw/) for your system.

### Updating Atmosphere or Hekate

1. Open the Homebrew Launcher.
2. Open `PyNX` through the Homebrew Launcher.
3. Press the green button with the text `switchguideupdater.py` on it using the touch screen.
4. Press `Update Atmosphere` or `Update Hekate` to update Atmosphere or Hekate respectively.
5. To use the updated version of Atmosphere, reboot your Switch. You'll need to boot CFW again using the instructions at [Launching CFW](/launching-cfw/) for your system.

<!-- #### Updating Atmosphére

1. [Download the latest release of Atmosphére](https://github.com/Atmosphere-NX/Atmosphere/releases/latest). Download both the zip file and `fusee-primary.bin`.
2. Turn off your Switch and put your microSD card in your computer.
3. Delete `fusee-primary.bin` and `fusee-secondary.bin` from the root your SD card.
4. Copy `fusee-secondary.bin` from the Atmosphére zip to the root of your SD card.
5. Copy `fusee-primary.bin` to the to the root of your SD card.
6. Safely remove your microSD card and plug it back in your Switch.
7. Boot CFW again using the instructions at [Launching CFW](/launching-cfw/) for your system.

### Updating Hekate

1. [Download the latest release of Hekate](https://github.com/CTCaer/hekate/releases/latest).
2. Turn off your Switch and put your microSD card in your computer.
3. Open the `bootloader` folder on your SD card and if it exists, remove `update.bin`.
4. From the Hekate zip, copy the file starting with `hekate_ctcaer` to the `bootloader` folder on your SD card.
5. Open the `bootloader` folder on your SD card and rename the file starting with `hekate_ctcaer` to `update.bin`. 
6. Safely remove your microSD card and plug it back in your Switch.
7. Boot CFW again using the instructions at [Launching CFW](/launching-cfw/) for your system. -->


### What next?

- You have now succesfully installed CFW on your Nintendo Switch.
- You can manage save data using Checkpoint (by Flagbrew), a save manager.
- You can download new homebrew using hb App Store (also known as Appstore-NX, by vgmoose).
- You can transfer files to your Switch over FTP using sys-ftpd (by jakibaki) if you are running a firmware above 3.0.0. No authentication is needed and the FTP server runs on port 5000. If you don't want this, remove the `sys-ftpd.kip` file from the `kips` folder in the `atmosphere` folder.
- You can load any KIP file you want by placing them in the `kips` folder in your `atmosphere` folder. These KIPs will be loaded automatically when booting Atmosphére. **Loading KIPs from unknown sources may damage your system. Be careful with what KIPs you load.**
- When rebooting, your access to CFW will be lost, unless you follow the steps at Launching CFW again.
- If you need to launch Stock firmware, select the `Stock` option when in Hekate's `Launch...` menu. You should not need to do this under normal circumstances, but it may be useful for troubleshooting.
  - **If you use the homebrew ChoiDuJourNX to update your Switch's firmware to prevent burning these fuses, this option will burn fuses!**

It is highly advised to also read the [FAQ](faq.html){: .a-table target="_blank")}
{: .info-box}