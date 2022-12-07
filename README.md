# Magisk Delta

This repo hosts Magisk delta related files

![](https://github.com/topjohnwu/Magisk/raw/master/docs/images/logo.png)

## Introduction

#### **This is not an officially supported [topjohnwu](https://github.com/topjohnwu) project**. 

> If you are looking for official Magisk source, you are in the wrong place, please [go to this page and download Official Magisk](https://github.com/topjohnwu/Magisk)

Yet another crazy custom Magisk by HuskyDG, is always synchronized with official Magisk, including back MagiskHide and some custom features.

- [Internal Documents](./docs/internal-guide.md)
- [MagiskHide Documents](./docs/sulist.md)

## Download

> If you are fine with official Magisk setup, it is recommended to stay. If you choose to use Magisk Delta, make sure you read all FAQs and changelog before using Magisk Delta.

### Stable / Beta

> For most user, Stable build is recommended.

#### Stable

- [Magisk 25.2-delta-5](https://huskydg.github.io/download/magisk/25.2-delta-5.apk)
- [Source code](https://huskydg.github.io/download/magisk/25.2-delta-5.zip)
- [Changelog](https://github.com/HuskyDG/magisk-files/blob/main/note_stable.md)

#### Beta

> Same as Stable Channel


### Canary / Debug

⚠ Only accept bugreports from Magisk Delta debug variant.

#### Download

- [Download Canary](https://huskydg.github.io/magisk-files/app-release.apk)
- [Download Debug](https://huskydg.github.io/magisk-files/app-debug.apk) 
- [Changelog](https://github.com/HuskyDG/magisk-files/blob/main/note.md)

## FAQ

### How to install Magisk Delta from start?

- Process like installing Magisk: <https://topjohnwu.github.io/Magisk/install.html>

### How to switch from current Magisk to Magisk Delta and vice versa?

Just do like when you update Magisk!

#### Direct Install (Recommended)

1. Install, open and then grant root acccess to Magisk Delta.
2. In **Magisk** section, tap "Install" and then "Direct Install". If you don't see this, try close and open the app.

#### Just flash Magisk Delta from current Magisk app

1. Rename the extension `magisk.apk` to `magisk.zip`
2. Open Magisk app, click "Modules" tab -> "Install from storage" and choose `magisk.zip`

### How do I run magisk on devices with exploit/temporarily root?

Occasionally, there would be exploits in certain devices that could lead to full fledged root. On modern Android, it is possible to use MagiskSU if you can gain a shell with the following conditions:

- Effective UID should be privileged (root, or euid=0)
- Have the ability to reload sepolicy (which 99.9% of the time means SELinux permissive)
- Have full Linux capabilities

If you meet all requirement above (after running exploit root tool):

- Push `magisk.apk` and `busybox` binary to `/data/local/tmp` and run [this script](https://huskydg.github.io/script/temp-magisk.sh) with root access

Note that these changes are not persistent, and you will need to find ways to rerun the whole process every boot.

### How to install Magisk into emulator (such as NoxPlayer, LDPlayer, etc...)?

- Before start:

1. Only Magisk Delta support Magisk installation into system partition. 
2. Although emulator has ramdisk image, patching ramdisk is not used because ramdisk is stored in seperate partition with very SMALL disk size that is not enough to store Magisk binaries.
3. Bluestacks and MumuPlayer X will not be supported

- Step to step to install Magisk into emulator:

1. Enable Root access in emulator settings
2. Install and open Magisk Delta
3. Grant root access to Magisk Delta, click "Install" under Magisk field and use "Direct Install into system partition" option instead of "Direct Install" option. If you don't see this option, close and re-open Magisk Delta app.
4. Disable Root access in emulator settings.
    *Some emulators delete `su` executable after disabling root access, accidentally remove magisk's `su` so backup and delete `/system/xbin/su` instead.*

### Pass Safetynet / Play Integrity (Device Integrity)

1. Enable Zygisk or install Riru core
2. Enable MagiskHide and install [Safetynet Fix Mod](https://github.com/HuskyDG/safetynet-integrity-fix/releases/latest)
3. Reboot your device

### Why not restore Magisk modules online repo?

The official Magisk modules repository is dead and no longer maintained. Due to that, add them back is meanless. However, [Fox2Code](https://github.com/Fox2Code) has developed [Magisk Modules Manager](https://github.com/Fox2Code/FoxMagiskModuleManager)  app which allows you to download Magisk modules online.

## Donate me

- Paypal: [paypal.me/huskydg](http://paypal.me/huskydg)
- You can now donate me if you want. Remember, I will not make this as a monetization tool and donate is not obligated. Thanks for all your supports and hope you have a good day! 👍


## Other links

- [Telegram group](https://t.me/magiskdelta)

## Credits

- Magisk author: [topjohnwu](https://github.com/topjohnwu/magisk)
- Magisk contributors: [vvb2060](https://github.com/vvb2060), [yujincheng08](https://github.com/yujincheng08), [RikkaW](https://github.com/RikkaW), [canyie](https://github.com/canyie)
- Maru (zygisk native bridge): [5ec1cff](https://github.com/5ec1cff)
- Other: [osm0sis](https://github.com/osm0sis), [diareuse](https://github.com/diareuse),...

## License

Our license obviously is the same as [Magisk's license](https://github.com/topjohnwu/Magisk#License)

```
Magisk, including all git submodules are free software:
you can redistribute it and/or modify it under the terms of the
GNU General Public License as published by the Free Software Foundation,
either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```
