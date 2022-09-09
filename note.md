## Magisk b68eccb8-delta by HuskyDG

### What is new?

- Revert "Inject Magisk service through `exec`"

### Diffs to official Magisk

- [General] MagiskHide rely on logcat to listen start up process events
- [General] The package name is `io.github.huskydg.magisk`
- [General] Add Core-only mode
- [General] Support installing Magisk without boot image for emulators
- [General] Fix the `/data` need of Magisk survival script `addon.d` when `/data` can't be decrypted
- [Manager] Show all supported languages in Language settings for Chinese ROM
- [Modules] Support systemless deleting files or folders for modules
- [General] Built-in Bootloop Protection
- [General] Tune F2FS for unencrypted devices
- [MagiskInit] Support Early-init mount

### About MagiskHide

- Start with Magisk Delta 25202, to avoid [Tracer detection](https://github.com/vvb2060/magiskdetector), MagiskHide will start to rely on logcat to catch start up app process. For MagiskHide to work, do not disable logd. ROMs with abnormal or slow logcats will cause MagiskHide to work incorrectly.
- Hiding isolated process and app zygote is now possible in MagiskHide on Android 11 and higher. For Android 10 and bellow, because of isolated processes's mount namespace use the same with zygote's mount namespace, handling isolated processes is not possible at all, you will need [Riru-Unshare](https://github.com/vvb2060/riru-unshare/releases) to force isolated processes's mount namespace to be detached.

### About Canary and Debug?

- They are built from the same source code
- Debug has more detailed logs than Canary

## Magisk (4737c511) (25202)

- [General] Fix minor bug in module files mounting implementation
- [MagiskPolicy] Fix minor bug in command line argument parsing
- [Zygisk] Prevent crashing daemon in error
- [Zygisk] Rewrite zygote code injection with new loader library approach

## Magisk (38ab6858) (25203)

- Update app to target API 33

## Diffs to v25.2

- [General] Fix minor bug in module files mounting implementation
- [MagiskPolicy] Fix minor bug in command line argument parsing
- [Zygisk] Prevent crashing daemon in error
- [Zygisk] Rewrite zygote code injection with new loader library approach