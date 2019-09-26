# Dell XPS 7390 2-in-1 Manjaro Linux Fixes

This repository allows you to build a custom kernel that fixes issues with the Dell XPS 7390 2-in-1 on Linux.

Usage:
1. Install Manjaro on your system using ```noapic``` kernel parameter.
  - if can't find the hard drive, boot into BIOS and under `System Configuration` change `SATA Operation` from `RAID On` to `AHCI`. This will make your windows partitions (if any) unusable.

2. Get latest linux firmware package from 
```https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/```
and copy the intel files into ```/lib/firmware/intel``` on your local system (fixes bluetooth).

3. Clone this repo

4. Run ```makepkg -s``` to build the kernel packages.

5. Install the packages that were built:

   ```sudo pacman -U ./linux53-5.3.0-0-x86_64.pkg.tar.xz```

   (Change filenames as necessary)

6. Reboot with new kernel.

## What's still not working?
- Webcam
- Suspend isn't working properly (black screen / cursor when resuming, and mouse/kb inoperational) - possibly related to thunderbolt

## KDE Issues
Fix for horizontal purple lines flashing on top few pixels of screen and inability to click/type into application launcher:

```pamac remove xf86-video-intel``` then reboot.

(purple lines still seem to appear on logon screen but once logged in they are fixed)


Many thanks to the redditors for providing fixes:
https://www.reddit.com/r/Dell/comments/cx0fkc/xps_13_2_in_1_7390_linux_boot_attempt/
