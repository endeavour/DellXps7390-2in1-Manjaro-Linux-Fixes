# Kernel 5.4
This branch is experimental.

Known issues:
Wifi not working.

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

5. Grab latest mkinitcpio since this isn't availble in Manjaro stable repos yet (as of 8/Nov/2019):
```wget https://www.mirrorservice.org/sites/repo.manjaro.org/repos/unstable/core/x86_64/mkinitcpio-27-1.2-any.pkg.tar.xz```

6. Install the packages:

   ```sudo pacman -U ./linux54-5.4rc6.d1105.g26bc672-2-x86_64.pkg.tar.xz ./mkinitcpio-27-1.2-any.pkg.tar.xz```

   (Change filenames as necessary)

6. Reboot with new kernel.

## KDE Issues
Inability to click/type into application launcher - switch to modesetting driver by running

```pamac remove xf86-video-intel``` then reboot.

## What's still not working?
- Webcam

# Acknowledgements
Many thanks to the redditors, particularly silverhaul, for providing fixes:
https://www.reddit.com/r/Dell/comments/cx0fkc/xps_13_2_in_1_7390_linux_boot_attempt/
