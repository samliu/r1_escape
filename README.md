# R1 Escape!

Tired of being locked out of the full potential of your brand new AI companion that's really just Android with a Flutter App?

Well, look no further!

The following collection of scripts will do the following:

 1. Enable "OEM Unlocking"
 2. Unlock the bootloader (will wipe any and all userdata!)
 3. Disable AVB
 4. Flash a userdebug system image of AOSP-13 (with GMS!)
 5. Rabbit Hole escaped!

## Prerequisites
### Linux
You probably need to do nothing, except have a Linux machine with root access (sudo).
If you're using a custom kernel, make sure `cdc_acm` module is present and loaded.
Please note, currently only amd64/x86_64 systems are supported. It will not work on ARM PCs.

*(If you do manage to get it working using box64, I'd be happy to merge it!)*

**The script currently supports Arch, Debian and Fedora distros.**

### Windows
You will need adb/fastboot drivers, you can grab them straight from Google, XDA or use Koush's driver package:
- **Google**: https://developer.android.com/studio/run/win-usb
- **XDA**: https://xdaforums.com/t/official-tool-windows-adb-fastboot-and-drivers-15-seconds-adb-installer-v1-4-3.2588979/
- **Koush**: https://adb.clockworkmod.com

XDA and Koush's all-in-one package is possibly a bit dated, but will do the job.

You will also require MediaTek Preloader USB VCOM drivers. Now, there are many sources on rather shady websites, but I suggest grabbing them from an OEM's instructions directly, for example:
 - **Hovatek**: https://www.hovatek.com/forum/thread-16640.html
 - **Teracube**: https://downloads.myteracube.com/Drivers/MediaTek_Preloader_USB_VCOM_Drivers_Setup_Signed.zip 

Windows might also automatically try downloading and installing these drivers, but your mileage may vary.

## Process
Okay, lets get down to business.
### Windows
1. Open an admin PowerShell
2. Run `Set-ExecutionPolicy unrestricted`
3. Either clone this repository or download it as ZIP
4. Extract it, and in the directory you should see a bunch of files including `r1.ps1`
5. Download and place the system.img file from here.
6. Right click in the directory and click "Open in Terminal"
7. Run `.\r1.ps1`
8. You may be asked to turn off and plug in your device, the script _should_ take care of the rest.

### Linux
1. Either clone this repository or download it as ZIP
2. Open a terminal in the directory of extracted files
3. Run `./r1.sh`
4. The script may ask you for your sudo permissions several times, so please enter your password
5. You may be asked to turn off and plug in your device, the script _should_ take care of the rest.

## Troubleshooting
### Windows
If the script stalls at any point, please check `devmgmt.msc` - Device Manager, and select the appropriate driver.
If the script says "Plug in USB" or similar, you may need to select any "Preloader USB VCOM" driver
If the script says "Waiting for device" or similar, you may need to select any "fastboot" driver.

### Linux
¯\_(ツ)_/¯

## Backup and Restore Stock

*Coming soon*
