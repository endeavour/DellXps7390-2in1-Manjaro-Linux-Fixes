# Dell XPS 7390 2-in-1 Manjaro Linux Fixes

This repository allows you to build a custom kernel that fixes issues with the Dell XPS 7390 2-in-1 on Linux.

Usage:
1. Install Manjaro on your system using ```noapic``` kernel parameter.

2. Get latest linux firmware package from 
```https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/```
and copy the intel files into ```/lib/firmware/intel``` on your local system (fixes bluetooth).

3. Clone this repo

4. Run ```makepkg -s``` to build the kernel packages.

5. Install the packages that were built:

   ```sudo pacman -U ./linux53-5.3rc8.d0908.gf74c2bb-1-x86_64.pkg.tar.xz ./linux53-headers-5.3rc8.d0908.gf74c2bb-1-x86_64.pkg.tar.xz```

   (Change filenames as necessary)

6. Reboot with new kernel.

## What's still not working?
- Webcam
- Thunderbolt (Ice Lake thunderbolt support should be included when kernel 5.4 arrives)

Many thanks to the redditors for providing fixes:
https://www.reddit.com/r/Dell/comments/cx0fkc/xps_13_2_in_1_7390_linux_boot_attempt/
