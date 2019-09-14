# Dell XPS 7390 2-in-1 Manjaro Linux Fixes

This repository allows you to build a custom kernel that fixes issues with the Dell XPS 7390 on Linux.

Usage:
Install Manjaro on your system using ```noapic``` kernel parameter.

Get latest linux firmware package from 
```https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/```
and copy the intel files into ```/lib/firmware/intel``` on your local system (fixes bluetooth).

Clone this repo
Run ```makepkg -s``` to build the kernel packages.
Install packages.

## What's still not working?
- Webcam

Many thanks to the redditors for providing fixes:
https://www.reddit.com/r/Dell/comments/cx0fkc/xps_13_2_in_1_7390_linux_boot_attempt/
