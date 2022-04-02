# Lenovo P11 Pro (TB-J706F) - March 2022 - Bootloader + TWRP + Root + Debloat

A guide for your new tablet :)

# Download list : 

- Platform Tools : https://dl.google.com/android/repository/platform-tools-latest-windows.zip

- QPST 2.7.480 (100% success rate with this version, it includes QFIL and driver, install both) : https://www.mediafire.com/file/lzc0svab3iehid7/QPST_2.7.480.zip/file

- Get the previous ROM, latest isn't available atm : https://mirrors.lolinet.com/firmware/lenovo/Tab_P11_Pro/TB-J706F/TB-J706F_S620150_211226_ROW.zip

- TWRP 3.4.2B for TB-J706F : https://www.mediafire.com/file/wvls8y5j0xpn501/twrp.img/file

- SafetyNet Fix : https://github.com/kdrag0n/safetynet-fix/releases (get .zip file)

- Magisk : https://github.com/topjohnwu/Magisk/releases (get .apk)

- Universal Android Debloater : https://github.com/0x192/universal-android-debloater/releases (get uad_gui-windows.exe, put uad_exported_selection.txt in the same folder)

- Patched boot.img for TB-J706F_S630229_220312_ROW : https://www.mediafire.com/file/p3q2rpjtlqtyfpc/patched_boot.img/file

# Guide : 

Download, unzip and rename img file to twrp.img

Enable OEM unlock in developers settings

Reboot to bootloader (adb reboot bootloader)

In bootloader enter :
`fastboot flashing unlock`  <- WARNING: UNLOCK BOOTLOADER WILL WIPE YOUR DEVICE!!

and answer yes when you're ready

Use QFIL to flash ROM

Do initial setup. DO NOT RESTORE

Install Magisk

Update to latest ota through settings (TB-J706F_S630229_220312_ROW), reboot

Go to bootloader and enter :
`fastboot flash recovery twrp.img`

`fastboot flash boot patched_boot.img` <- (ONLY DO THIS IF YOU ARE ON TB-J706F_S630229_220312_ROW, I DON'T KNOW IF THIS IMAGE WILL BE COMPATIBLE FOR NEXT UPDATES)
(If you're on a newer rom dump boot.img yourself through TWRP (adb shell and dd if="/dev/block/bootdevice/by-name/boot_b" of="/sdcard/boot.img", patch the image with Magisk)

Reboot, enable Zygisk in Magisk settings and install safetynet fix in Magisk, reboot

Open UAD and uninstall the selection, there will be remaining bloats but I wasn't able to find them in UAD

Hide your Magisk app in the settings

Add Play Store to Magisk hide list, wipe cache and data for Play Store & Google Play Services

Done, you can install Netflix from Playstore and stuff, but I still get widevine L3 :/


# Troubleshoot :

- TWRP will ask for a password if your device has pin/pattern to unlock, disable it to get access to user data
- wtf why my touch screen is glitched after going to TWRP? idk it's odd but just reboot and it'll be fixed
- Play store not installing apps? Format your SD card to external storage
