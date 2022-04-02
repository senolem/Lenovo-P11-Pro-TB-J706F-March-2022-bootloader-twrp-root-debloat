# Lenovo P11 Pro (TB-J706F) - March 2022 - Bootloader + TWRP + Root + Debloat

## <p align="center"> A guide for your new tablet :) </p>

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

1. Download, unzip and rename img file to twrp.img

2. Enable OEM unlock in developers settings

3. Reboot to bootloader (adb reboot bootloader)

4. In bootloader enter :
`fastboot flashing unlock`  <- WARNING: UNLOCK BOOTLOADER WILL WIPE YOUR DEVICE!!

5. and answer yes when you're ready

6. Use QFIL to flash ROM

7. Do initial setup. DO NOT RESTORE

8. Install Magisk

9. Update to latest ota through settings (TB-J706F_S630229_220312_ROW), reboot

10. Go to bootloader and enter :
`fastboot flash recovery twrp.img`

11. `fastboot flash boot patched_boot.img` <- (/!\ FOR TB-J706F_S630229_220312_ROW ONLY)

12. (If you're on a newer rom dump boot.img yourself through TWRP (adb shell and dd if="/dev/block/bootdevice/by-name/boot_b" of="/sdcard/boot.img", patch the image with Magisk)

13. Reboot, enable Zygisk in Magisk settings and install safetynet fix in Magisk, reboot

14. Open UAD and uninstall the selection, there will be remaining bloats but I wasn't able to find them in UAD

15. Hide your Magisk app in the settings

16. Add Play Store to Magisk hide list, wipe cache and data for Play Store & Google Play Services

17. Done, you can install Netflix from Playstore and stuff, but I still get widevine L3 :/

# Troubleshoot :

- TWRP will ask for a password if your device has pin/pattern to unlock, disable it to get access to user data
- wtf why my touch screen is glitched after going to TWRP? idk it's odd but just reboot and it'll be fixed
- Play store not installing apps? Format your SD card to external storage
