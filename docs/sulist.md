## MagiskHide

 Hide Magisk modifications from target on hidelist

### Implementation

- Use `logcat` to monitor start up app process and check whenever a process is on hidelist. If a target is on hidelist, MagiskHide will fork new process, enter its mount namespace and do unmount all modifications including Magisk tmpfs path and modules to hide Magisk.

## MagiskHide SuList
 MagiskHide in whitelist mode: Magisk is hidden by default, only process on sulist will be able to explore Magisk root privilege.

### Implementation

- **SuList applies unmount Magisk directly in Zygote mount namespace** to make Magisk hidden in app processes by default.
- Use `logcat` to monitor start up app process, only processes checked in sulist will have `su` mounted and thus will be able to execute `su` to obtain root access.

### Advantage

- Solve most banking apps problem, which MagiskHide might be inapplicable
- Do not touch non-target apps memory environment

### Disadvantage

- Module functionality is almost broken: Due to the implementation of SuList, module system files are no longer mounted in zygote process after start, that's why most modules might not work and expect to break the system.
- SuList doesn't work on system with abnormal `logcat`, cause Magisk unable to be mounted normally. **Please do the final check before using it!**
