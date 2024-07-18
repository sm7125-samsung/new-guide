---
layout: default
title: Unlocking the bootloader
nav_order: 2
---

# Unlocking the bootloader
{: .pb-2 }
<p align="center">
  <img loading="lazy" src="/assets/images/dev-options.jpg" width="30%"/>
  <img loading="lazy" src="/assets/images/bl-unlock.png" width="30%"/>
</p>

Unlocking your bootloader is a fundamental step when installing a custom ROM/recovery or simply rooting your device, as it allows you to flash and install unofficial images in it. Please note this procedure **will completely wipe your data**, so make a backup before proceeding.
To check if the bootloader is already unlocked, boot your device in Download mode with its key combo and check the OEM Lock status.

The possible OEM Lock values are:
- **ON (L)**: fully locked.
- **ON (U)**: bootloader locked, OEM unlocking enabled.
- **OFF (U)**: fully unlocked.

To unlock your bootloader, follow the instructions below. If no OEM Lock value is shown in Download mode, your device is probably not unlockable due to market limitations (USA/Canada devices).

KnoxGuard status should also be checked to ensure your device hasn't been locked by your carrier or Samsung itself.

Possible KnoxGuard values are the following:

- `Active`, `Locked`: your device has been remotely locked by your telecom operator or your insurance company.
- `Prenormal`: your device is temporarily locked, reaching 168h of uptime should trigger unlock.
- `Checking`, `Completed`, `Broken`: your device is unlocked.

Having KnoxGuard show `Active` or `Locked` will prevent you from installing/running unofficial images regardless of your bootloader lock state.

{: .warning }
> Unlocking the bootloader and flashing custom ROMs/Recoveries will trip the Knox warranty bit, leading to some OneUI apps to stop working, such as Secure Folder, Samsung Health, Work Profile, ...
>
> If you intend to stay on OneUI, use [KnoxPatch](https://github.com/salvogiangri/KnoxPatch) later on to get back those features.

## Unlocking the bootloader
{: .pb-1 }
- Open the Settings app, enter About Phone → Software info and tap “Build number” 10 times to enable Developer Options.
- Go back into main settings page and you should now see a new category called "Developer Options". Enter it and enable OEM unlocking.
- Reboot your device into Download mode by powering it off. Then plug it into a PC and hold `Power`, `Volume Up` and `Volume Down` buttons until the blue download mode screen appears (see above picture).
- Long press `Volume Up` to unlock the bootloader. **This will wipe your data and automatically reboot the phone.**
- Go through the initial setup. Skip through all the steps since data will be wiped again in later steps. **Connect the device to internet during the setup.**
- Enable Developer Options again and **confirm that the OEM unlocking option exists and is grayed out.** This means KnoxGuard hasn't locked your device and your bootloader has successfully been unlocked.

<p align="center">
  <img loading="lazy" src="/assets/images/blwarning.png" width="30%"/>
</p>

If everything went right, your device will start to display the above warning at every boot, this cannot be removed in any way (other than installing the stock firmware and locking your bootloader) as it's mandatory on every Android device.

## Locking the bootloader
{: .pb-1 }
If you ever feel like locking your bootloader, you can do so by following the unlock instructions in reverse: boot to Download mode (`Power`, `Volume Up` and `Volume Down`), lock your bootloader by holding `Volume Up` and disable OEM unlocking toggle in Developer Options.

Please note that:
- This will again completely wipe your data.
- The device must have the full stock untouched firmware installed, otherwise issues may be faced when locking your bootloader.
- Your Knox Warranty Bit will not be restored by locking your bootloader, a solution such as [KnoxPatch](https://github.com/salvogiangri/KnoxPatch) is suggested if you intend to stay on OneUI.

{: .highlight }
*Continue to [Installing a custom Recovery]({% link recoveries/index.md %})*
