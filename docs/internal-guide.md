# Magisk Delta Internal Documentation

## Early-init mount

- Some files requires to be mounted earliest in the boot process, Magisk delta has provided the way to mount files in `early-init` through `early-mount.d`
- The chose location to mount files in `early-mount.d` is placed in same place with `sepolicy.rules` directory. Example your directory to store custom sepolicy rules is `/data/unencrypted/magisk` then the location to mount files is `/data/unencrypted/early-mount.d`
- You can place your files into the corresponding location under `early-mount.d` directory. For example, you want to replace `/vendor/etc/vintf/manifest.xml` and your mount directory is `/data/unencrypted/early-mount.d`, copy your `manifest.xml` to `/data/unencrypted/early-mount/system/vendor/etc/vintf/manifest.xml` , Magisk will mount your files in the next reboot​

## File or folder removal

- Magisk provides the way to modify read-only system files by using modules while keeping system partition untouched. The beaty of Magisk modules is the changes are stored in data partition while it is visible in system partition. 

- Magisk modules can add or replace files into `/system`, `/vendor`, `/product` and `/system_ext`. However, magisk does not provide the way to make files in system disappeared.

- In Magisk documentation:

> It is complicated to actually remove a file (possible, not worth the effort). Replacing it with a dummy file should be good enough

> It is complicated to actually remove a folder (possible, not worth the effort). Replacing it with an empty folder should be good enough. Add the folder to the replace list in "config.sh" in the module template, it will replace the folder with an empty one

- In some case, replace file or folder with blank one is not enough and might cause issue. And some modding require files to be disappeared in order to take effect. So Magisk Delta has added removal support for modules. Replacing the target which you want to be deleted with the broken symlink point to `/xxxxx`. When Magic mount happened and detected this symlink, the target will be ignored and disappeared.

- Example creating symbolic link as `/data/adb/modules/mymodule_id/system/vendor/etc/thermal-engine-normal.conf`, the target `/vendor/etc/thermal-engine-normal.conf` will be ignored and disappeared:

```
ln -s "/xxxxx" /data/adb/modules/mymodule_id/system/vendor/etc/thermal-engine-normal.conf
```
