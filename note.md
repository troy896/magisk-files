## Magisk f757317b-delta by HuskyDG

### What is new?

- To avoid some problems, `early-mount.d` no longer mount files directly from `$(magisk --path)/.magisk/mirror/early-mount`, the content of `early-mount.d` will be copied to tmpfs and bind mount
- Update some translation

### Diffs to official Magisk

- [General] Restore MagiskHide, uses system logcat to monitor app processes startup: disabled or abnormal logcat can't use MagiskHide.
- [General] The package name is `io.github.huskydg.magisk`
- [General] Support Magisk installation without boot image for emulators
- [General] Fix the `/data` need of Magisk survival script `addon.d` when `/data` can't be decrypted
- [Manager] Show all supported languages in Language settings for Chinese ROM
- [Modules] Support systemless deleting files or folders for modules
- [General] Built-in Bootloop Protection
- [General] Tune F2FS for unencrypted devices
- [MagiskInit] Support Pre-Init mount, replace system files before `init` starts
- [MagiskInit] Support loading custom rc script from pre-init directory

### About Canary and Debug?

- They are built from the same source code
- Debug has more detailed logs than Canary

## Magisk (66a7ef56) (25203)

- Upstream to [66a7ef56](https://github.com/topjohnwu/Magisk/commits/66a7ef5615f463435b45d29e737d37cf48a9b78c)

## Magisk (38ab6858) (25203)

- Update app to target API 33

## Diffs to v25.2

- [General] Fix minor bug in module files mounting implementation
- [MagiskPolicy] Fix minor bug in command line argument parsing
- [Zygisk] Prevent crashing daemon in error
- [Zygisk] Rewrite zygote code injection with new loader library approach