# Magisk Delta Internal Documentation

## Early-init mount

- Some files requires to be mounted earliest in the boot process, Magisk delta has provided the way to mount files in `early-init` through `early-mount.d`
- The chose location to mount files in `early-mount.d` is placed in same place with `sepolicy.rules` directory. Example your directory to store custom sepolicy rules is `/data/unencrypted/magisk` then the location to mount files is `/data/unencrypted/early-mount.d`
- You can place your files into the corresponding location under `early-mount.d` directory. For example, you want to replace `/system/media/bootanimation.zip` and your mount directory is `/data/unencrypted/early-mount.d`, copy your new boot animation zip to `/data/unencrypted/early-mount/system/media/bootanimation.zip`, Magisk will mount your files in the next reboot​
