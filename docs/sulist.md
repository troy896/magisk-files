## SuList

Recently Magisk Delta introduces a new hidden feature: SuList.  When enabled, Magisk will be hidden for all apps by default, only apps added to the SuList will be able to access Magisk Root.

More information:

 - SuList has the strongest root hiding ability because of limited modification of the application environment
  - SuList uses logcat to monitor application startup, please do not disable logcat service or you will lose root.
  - SuList uses separate lists.  After enabling SuList and restarting, you should be able to configure sulist
  - Select apps that need Magisk access to SuList, not banking apps
  - SuList doesn't work like MagiskHide
  - SuList applies unmount Magisk directly in zygote, zygote will no longer read the module file after it finishes booting.
  - SuList cannot coexist with Zygisk because Zygisk is causing more detection.
  - Most modules will not work or broken properly in SuList because of the way it works, or will break the system.  Please don't ask why some modules don't work.
  - Riru modules will still work because most of them don't use the Magic mount feature.
  - SuList cannot be disabled immediately without restarting
