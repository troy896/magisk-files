## Magisk ec008f3a-delta by HuskyDG

### What is new?

- Fix MagiskHide handle slowly

### Diff from official

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

### About Canary and Debug?

- They are built from the same source code
- Debug has more detailed logs than Canary

## Magisk (b496923c) (25201)

Synchronized to [b496923c](https://github.com/topjohnwu/magisk/tree/b496923c)

- No changelog