.. _chapter-consumer:

Consumer Edition Reference Platform
===================================

Hardware
--------

The hardware that Consumer Reference Platform runs on *should* be 96Boards compliant [ref2]_. The following requirements assume that software runs on 96Boards CE compliant hardware.

Accelerated graphics support
----------------------------

Accelerated graphics drivers *shall* be fully supported either with open source code, or through royalty free binary drivers. If binary drivers are utilized, the vendor *shall* provide support to provide updated drivers/libraries to support new mainline Linux kernel features.

Boot
----

The board *shall* boot from eMMC. The board *should* boot from SD card.

Bluetooth
---------

Bluetooth *shall* be supported. 

The device *shall* be possible to do the following bluetooth actions:

 - Scanning
 - Pairing
 - Audio Streaming (A2DP)
 - File transfer (FTP)

List of the reference 3rd party hardware for testing the above mentioned features will be provided as appendix.

USB
---

The following USB device types *shall* be supported in the software:

 - HID
 - Mass storage device
 - Ethernet

WiFi [Scanning, Profiles, Downloading]
SD [SD-HC, SD Read/Write (ext2), SD Read/Write (fat32)

Power cycle
-----------

The following actions *shall* be possible using software:

 - Shutdown
 - Reboot

LEDs
----

It *shall* be possible to control "user" and "status" LEDs available on the board from software.

Robustness
----------

Software running on the board *shall not* shutdown or reboot on it's own.

User interface
--------------

Graphical user interface (GUI) software builds *shall* be provided. Builds without GUI *may* be provided.

