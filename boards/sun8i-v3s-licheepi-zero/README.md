This file collects notes and information relevant to the Lichee Pi Zero board.

As this board has such a small amount of RAM available (only 64Meg),
it is not possible to run it with a ramdisk.  The disk image created by
this builder is one that with a standard root filesystem - created from
the debian ramdisk image.

Power Usage
-----------

During testing, I measured the power used.

| Setup                                        | Max    | CC/CV  | Idle   |
|----------------------------------------------|-------:|-------:|-------:|
| MMCdisk, nothing else plugged in             |  187mA |  162mA |   92mA |

TODO
----
* Make the hostname less unclear (currently has prefix "ramdisk")
* Add support for USB gadget bits (serial console, ethernet, maybe blockdev)
    * gadget is pre-configured for console+ethernet
    * add ttyGS0 to securetty and start serial-getty@ttyGS0
    * cdc ether is as simple as using netdev usb0 - need to decide how is best
* Try using the armbian allwinner kernel with the licheepi-zero dtb
* Ensure that the lichee official SDIO WIFI works
* Add drivers and firmware for TOP-GS07 WIFI
* Maybe automatically detect and use the swap partition?
* config for onboard LED:
    gpio (Blue 192, Green 193, Red 194)
    The mainline kernel already has a dts that correctly defines these leds
