# Dell XPS 7390 2-in-1 Manjaro Linux Fixes

This repository allows you to build a custom kernel that fixes issues with the Dell XPS 7390 on Linux.

Usage:
1. Install Manjaro on your system using ```noapic``` kernel parameter.

2. Get latest linux firmware package from 
```https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/```
and copy the intel files into ```/lib/firmware/intel``` on your local system (fixes bluetooth).

3. Clone this repo

4. Run ```makepkg -s``` to build the kernel packages.

5. Install the packages that were built.

6. Reboot with new kernel.

## What's still not working?
- Webcam

Many thanks to the redditors for providing fixes:
https://www.reddit.com/r/Dell/comments/cx0fkc/xps_13_2_in_1_7390_linux_boot_attempt/
