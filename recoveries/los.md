---
layout: default
title: LineageOS recovery
parent: Recoveries
---

1. Download the latest recovery.img and vbmeta.img from here: [A52 4G](https://download.lineageos.org/devices/a52q/builds) or [A72](https://download.lineageos.org/devices/a72q/builds)
2. Open a command prompt in the same folder that you downloaded recovery.img and vbmeta.img to (`SHIFT` + `Right Click` → `Open Command Prompt here`).
3. Run the following command: `tar --format=ustar -cvf files.tar vbmeta.img recovery.img`. This will pack both `.img` files into a TAR file called `files.tar`.
4. Download the latest Samsung USB Drivers from here and install them: [developers.samsung.com](https://developer.samsung.com/android-usb-driver)
5. Download [Odin for Windows](https://gitlab.com/Ryzen5950XT/odin_dl/-/raw/main/Odin3_v3.14.4.zip) or [Odin for Linux](https://xdaforums.com/t/official-samsung-odin-v4-1-2-1-dc05e3ea-for-linux.4453423/#post-86977569), depending on the operating system your computer runs. For MacOS, use [Heimdall](https://glassechidna.com.au/heimdall/#downloads).
6. **Odin for Windows:** _Extract_ the zip file (`Right Click` → `Extract`) and run `Odin3 v3.14.1.exe`.
7. **Odin for Linux:** Extract the zip file, make the odin4 binary executable (`chmod +x odin4`) and run `./odin4 -h` to display the help message. Follow the instructions noted under `IMPORTANT` to fully set up Odin4. Otherwise Odin4 will not be able to detect your phone.
8. **MacOS:** Install Heimdall and follow its instructions.
9. Boot your device into download mode. Fully turn off your phone, then connect it to a **PC** using a USB cable.
10. Now hold `Volume up`, `Volume down` and the `Power` button together. Once the blue download mode screen appears, release all the keys and press `Volume Up` once to confirm booting into download mode.
11. Make sure your device is detected by Odin. On Windows, a small blue bar will be visible on the top left under "ID:COM". On Linux, run `./odin4 -l` to check if your device is detected. Empty output means no device detected.
12. In Odin (Windows) click on the `AP` button on the right and select the `files.tar` file you created in step 3.
13. On the left click on "Options" next to "Log" and "Pit" and untick `Auto reboot`.
14. Click on `Start` to start installing LineageOS recovery.
15. If it says "Pass" in green in Odin everything went fine. If it says "FAIL" in red then you did something wrong and should start again from step 1. Note that the error message will be shown **on the phone** and **NOT** in Odin.
16. Next you need to reboot your phone and immediately boot into recovery mode, otherwise LineageOS recovery will be replaced by Android stock recovery again. **Please read the following steps first before continuing!**
17. Hold the `Power` and `Volume Down` buttons for around 10 seconds. The screen will turn off and the phone will start rebooting.
18. Once the screen turns off, release both keys and then start holding `Power` and `Volume Up` buttons until you reach LineageOS recovery. If you messed up the timing and booted into Android instead, you will have to repeat the steps again starting from step 6.
19. If using Odin for Linux: run `./odin4 -a files.tar` to flash LineageOS recovery. **Note that your phone will reboot automatically**, so prepare to hold the recovery key combination once the screen turns off (`Power` + `Volume Up`).
20. If using MacOS, follow the proper instructions provided by Heimdall.
21. Once you entered LineageOS recovery select `Factory Reset` and fully wipe your phone.

{: .highlight }
*Continue to [Installing a custom ROM]({% link roms/index.md %})*