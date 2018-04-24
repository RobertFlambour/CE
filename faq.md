---
layout: page
title: FAQ
permalink: /faq/
---

Answers to some of the most commonly asked questions related to CoreELEC are listed below.

# Installation
- Which file do I need to use (img.gz/tar)?
  - If you are doing a fresh install then you need the img.gz file or if you are updating then you need the tar file.
- Where do I find the dtb files?
  - All dtb files are now included in our images and can be accessed from the device_trees folder on your sdcard or usb drive.
- I have a WeTek Play 2, which dtb do I use?
  - gxbb_p200_2G_wetek_play_2.dtb

### Updating/Upgrading
- I currently have LibreELEC 8.2 by kszaq installed, can I update to CoreELEC?
  - Absolutely, our releases are fully compatible with upgrading from kszaq's builds
- How do I update my installation?
  - There is a few methods you can use to update however the easiest method is to just place the *tar* file inside of the Update folder and then to just reboot, do not place any other files in the update folder like DTB's.
- Does CoreELEC auto-update?
  - The functionality is built into all of our images but is not currently active.

### Hardware Issues
- I have just updated and now my device will not boot
  - This is mostly always as a result of a problem with the DTB and being *installed on internal*,
    the DTB should not be copied into the update folder when updating, it will update automatically.
    To fix the issue follow the instructions below.
    - Boot your device from sdcard or usb with the correct device tree.
    - Login over SSH and execute `dd if=/dev/zero of=/dev/dtb bs=256k count=1` then `dd if=/flash/dtb.img of=/dev/dtb bs=256k`
    - Power off, remove sdcard or usb, boot from internal.
- The display on my box doesn't work.
  - Refer to the following [thread](https://forum.libreelec.tv/thread/11736-led-vfd-displays-in-libreelec/)
- The display on my box shows the time but not the additional icons.
  - Install FD628 addon from CoreELEC addons repository.
- My remote does not work.
  - CoreELEC is not compatible with amremote remote.conf files, refer to the following [thread](https://forum.libreelec.tv/thread/11643-le9-0-remote-configs-ir-keytable-amlogic-devices/?postID=86451) for more information.

### Addons
- Netflix/Amazon does not work
  - These addons are dependant on inputstream.adaptive being installed and enabled and also libwidevinecdm.so being installed on your device.
- Netflix/Amazon plays poorly at 1080p
  - This is because currently there is no H/W based decoding support for these addons so all decoding is done by the CPU which is not powerful enough to decode 1080p.

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include open-embed.html %}
