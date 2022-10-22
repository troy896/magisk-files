## Magisk c7710975-delta by HuskyDG

### What is new?

- Properly detect zygote and system_server in logcat MagiskHide

### Diffs to official Magisk

- [General] Restore MagiskHide, uses system logcat to monitor app processes startup: disabled or abnormal logcat can't use MagiskHide.
- [General] DenyList is removed. There is no zygisk denylist feature
- [App] The package name is `io.github.huskydg.magisk`
- [App] Support Magisk installation without boot image for emulators
- [General] Copy required files to `/system` for `addon.d`
- [Manager] Show all supported languages in Language settings for Chinese ROM
- [Modules] Support systemless deleting files or folders for modules
- [General] Built-in Bootloop Protection
- [General] Tune F2FS for unencrypted devices
- [MagiskInit] Support Pre-Init mount, replace system files before `init` starts
- [MagiskInit] Support loading custom rc script from pre-init directory
- [App] Wait for service to bind before accessing [topjohnwu/Magisk#6268](https://github.com/topjohnwu/Magisk/pull/6268)


### About Canary and Debug?

- They are built from the same source code
- Debug has more detailed logs than Canary

## Magisk (c3b4678f) (25204)

- Make hiding the Magisk app 100% offline
- Cleanups and minor refactoring of Zygisk

## Diffs to v25.2

- [General] Fix minor bug in module files mounting implementation
- [MagiskPolicy] Fix minor bug in command line argument parsing
- [Zygisk] Prevent crashing daemon in error
- [Zygisk] Rewrite zygote code injection with new loader library approach