# Lenovo-P11-Pro-TB-J706F-March-2022-bootloader-twrp-root-debloat
Guide for your new tablet :)

if anyone needs a guide to get bootloader+twrp+root+debloat without having a headache (i haven't been able to found latest update rom file online so I dumped boot.rom myself) :

0. Dowload , unzip and rename img file to twrp.img https://www.mediafire.com/file/wdpxfr5t2z4mrye/TWRP-3.4.2B-1208-LENOVO_TBJ706F.zip/file
1. Enable OEM unlock in developers settings
2. Reboot in bootloader (adb reboot bootloader)
3. In bootloader enter :

Code:

fastboot flashing unlock


and answer yes when you're ready
WARNING: UNLOCK BOOTLOADER WILL WIPE YOUR DEVICE!!!!!
4. Use QFIL to flash ROM (https://mirrors.lolinet.com/firmware/lenovo/Tab_P11_Pro/TB-J706F/TB-J706F_S620150_211226_ROW.zip)
5. Do initial setup. DO NOT RESTORE
6. Install Magisk (apks folder)
7. Update to latest ota through settings, reboot(TB-J706F_S630229_220312_ROW)
8. Enter fastboot and enter :

fastboot flash recovery twrp.img
fastboot flash boot patched_boot.img (ONLY DO THIS IF YOU ARE ON TB-J706F_S630229_220312_ROW, I DON'T KNOW IF THIS IMAGE WILL BE COMPATIBLE FOR NEXT UPDATES)

15. Reboot, enable Zygisk in Magisk settings and install safetynet fix on Magisk (modules folder), reboot
17. Open UAD and uninstall the selection, there will be remaining bloats but I wasn't able to find them in UAD
18. Hide your Magisk app in the settings
19. Add Play Store to Magisk hide list, wipe cache and data for Play Store & Google Play Services
20. Done, you can install Netflix from Playstore and stuff, but I still get widevine L3 :/

Troubleshoot :
- TWRP will ask for a password if your device has pin/pattern to unlock, disable it to get access to user data
- wtf why my touch screen is glitched after going to TWRP? idk it's odd but just reboot and it'll be fixed
- Play store not installing apps? Format your SD card to external storage

(modified guide from https://forum.xda-developers.com/t/...-if-running-android-11.4374645/#post-86108685)
