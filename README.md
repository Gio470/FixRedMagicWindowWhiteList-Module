# Fix RedMagic Window WhiteList

A [Magisk](https://github.com/topjohnwu/Magisk)/KernelSU module that lifts the
floating-window restriction on REDMAGIC (nubia/ZTE) devices and ships a WebUI
for managing which apps are allowed to use floating/split windows.

## What it does

- Disables the `ro.vendor.feature.mfv_feature_windowreply_abroad` property via
  `system.prop`, removing the region lock on the floating window feature.
- Replaces `/system/etc/zte_windowReply_control.xml`, the whitelist consulted
  by the system's window-reply service, with an editable copy.
- Provides a WebUI (`webroot/index.html`), accessible from Magisk Manager /
  KernelSU Manager, for adding, removing, and managing apps in the
  `forceSupport_whiteList` without editing the XML by hand.

## Installation

1. Download the latest built module zip. 
2. Flash it from Magisk Manager or KernelSU Manager: **Modules → Install from
   storage**.
3. Reboot.
4. Open the module's WebUI from the manager app to manage the whitelist.

## Repository layout

```
META-INF/com/google/android/   Flashable zip installer (update-binary, updater-script)
module.prop                    Module metadata (id, name, version, author)
system.prop                    Boot-time system property override
system/etc/zte_windowReply_control.xml   Floating window whitelist
webroot/index.html             WebUI for managing the whitelist
```

## Requirements

- RedMagic OS (tested on my Redmagic 10 Pro (NX789J) Android 16)
- Root

## Credits

https://xdaforums.com/t/magisk-mod-experimental-redmagic-addons.4677270/

https://claude.ai

## Disclaimer

This module modifies system properties and a system whitelist file. It is
intended for REDMAGIC devices affected by the floating window
region restriction. Use at your own risk. I am not responsible for
any damage to your device.

## Note

I made this module for my personal use with the help of AI (I don't know how to code only in lua).

## License

Released under the [MIT License](LICENSE).
