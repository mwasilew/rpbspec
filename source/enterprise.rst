.. _chapter-enterprise:

Enterprise Edition Reference Platform
=====================================

Hardware
--------

The hardware that Enterprise Reference Platform runs on *shall* be SBBR compliant [ref1]_.

Boot
----

The board *shall* be able to boot using PXE. When OS is installed to the hard drive, the board *shall* be able to boot from this device.

Power cycle
-----------

The following actions *shall* be possible using software:
  Shutdown
  Reboot

Virtualization
--------------

The board *shall* support Linux virtualization. Bootloaders and firmware *shall not* rely on using/reserving EL2 for their use, but must leave this available to the OS. In particular it *shall* be possible to run 32 and 64 bit Linux guest in system emulation. The following virtualization tools *shall* be provided:
 - QEMU
 - LibVirt
 - Bridge Utilities

PCIe
----

The board *shall* support PCIe cards. The list of the reference cards used for testing this feature will be provided as appendix

ARM optimized server stack
--------------------------

It *shall* be possible to run the following software stacks using Reference Software Platform:
 - PHP
 - MySQL
 - Apache
 - NGiNX
 - OpenSSH Server

Development tools
-----------------

The following development tools *shall* be available
 - GNU C/C++ compiler
 - Make
 - LIBC Development Libraries and Header files
 - OpenJDK 7 & 8

Container tools
---------------

It *shall* be possible to use container tools:
 - Docker (https://www.opencontainers.org)
 - LXC
 - Kubernetes

