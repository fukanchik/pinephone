# pinephone
## Problems:
* Short battery life
* upower does not work
* evince does not support djvu. Addressed here [here](https://gitlab.alpinelinux.org/alpine/aports/-/merge_requests/12573), [here](https://gitlab.alpinelinux.org/alpine/aports/-/merge_requests/12673)
* general lack of applications adapted for phone
* Security: Before passcode screen it shows you the desktop!
* Bluetooth is always on. Turns back on after reboots and unlocks.
* No way to turn off passcode on unlock screen
* cheese does not see any cameras (camera itself works)
* powertop is not working (even dedicated ARM version)
* back of the device is always hot
* reboot menu is too small

## Dev setup
I'm not interested in rebuilding the whole phone image from scratch every time. My setup is for developing user apps.

* alpine x86\_64 in LXC container for trying things quickly
* alpine aarch64 in qemu for compiling for the phone. Here I also added postmarketos repo: http://postmarketos1.brixit.nl/postmarketos/v20.05
* the phone itself. I added local package into the list of repositories

The change is done in alpine x86 as it's as fast as my PC. It is compiled and tested in LXC if possible. Next step is to push it to qemu where a package built for the aarch64 which can be executed on the phone directly. Final step is to copy the aarch64 to the phone where I use FS repo to install it and then I can use it on the phone.

