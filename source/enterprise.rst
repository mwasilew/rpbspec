.. _chapter-enterprise:

Enterprise Edition Reference Platform
=====================================

Hardware
--------

[EE1.0] The hardware that Enterprise Reference Platform runs on *shall* be SBBR compliant [ref1]_.

Boot
----

[EE2.0] The board *shall* be able to boot using PXE. [EE2.1]When OS is installed to the hard drive, the board *shall* be able to boot from this device.

Power cycle
-----------

The following actions *shall* be possible using software:

 - Shutdown [EE3.0]
 - Reboot [EE3.1]


Storage
-------

[EE4.0] It *shall* be possible to read from and write data to the hard drive. [EE4.1]It *shall* also be possible to use at least software RAID capabilities.

Networking
----------

[EE5.0] It *shall* be possible to download and upload data using network interfaces on the board.

Virtualization
--------------

[EE 6.0] The board *shall* support Linux virtualization: Bootloaders and firmware *shall not* rely on using/reserving EL2 for their use, but must leave this available to the OS. In particular it *shall* be possible to run 32 and 64 bit Linux guest in system emulation.

The following virtualization tools *shall* be provided:

 - QEMU [EE6.1]
 - LibVirt [EE6.2]
 - Bridge Utilities [EE6.3]

PCIe
----

[EE 7.0] The board *shall* support PCIe cards. The list of the reference cards used for testing this feature will be provided as appendix

Container tools
---------------

It *shall* be possible to use container tools:
 - Docker (https://www.opencontainers.org) [EE 8.0]
 - LXC [EE 8.1]

ARM optimized server stack
--------------------------

It *shall* be possible to run the following software stacks using Reference Software Platform:

 - PHP [EE 9.0]
 - MySQL [EE 9.1]
 - Apache [EE 9.2]
 - NGiNX [EE 9.3]
 - OpenSSH Server [EE 9.4]

The above mentioned software *shall* run with sufficient performance. [EE 9.5]

Development tools
-----------------

The following development tools *shall* be available

 - GNU C/C++ compiler [EE 10.0]
 - Make [EE 10.1]
 - LIBC Development Libraries and Header files [EE 10.2]
 - OpenJDK 7 & 8 [EE 10.3]

Enterprise use cases
--------------------

The following enterprise software stacks *shall* be supported:

 - OpenStack (Core) [EE 11.0]
 - Ceph [EE 11.1]
 - Hadoop [EE 11.2]
 - Spark [EE 11.3]
 - HAProxy [EE 11.4]
