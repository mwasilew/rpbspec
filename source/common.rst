.. _chapter-common:


Common Components
==========

The following common Components are specified for the release RPBs

 - ARMv8 Open source bootloader
 - OP-TEE Open Source Trusted Execution Environment (option)
 - Linux kernel - Reference Platform Kernel
 - Blend distribution

Common Requirements
===================

[CM 0] All supported targets *shall* be built from a multi-platform configuration

Boot architecture
-----------------

[CM 1.0] At least one open source implementation *shall* be available. 

ARMv8 Open Source Bootloader
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The open source reference bootloader consists of the following components:

.. glossary::

    ARM Trusted Firmware (ATF)
        This is for 64 bit ARMv8A SoCs and provides boot authentication, Power
        State Coordination Interface (PSCI), SMC calling convention and an
        interface to the optional OP-TEE (or other Trusted OS). Source code is
        maintained at:
        https://github.com/ARM-software/arm-trusted-firmware. 

    Tianocore/edk2 UEFI
        This provides the industry standard UEFI implementation. Device Tree
        bindings are used to provide the SoC description for the CE RPBs and
        ACPI is used to provide the description for the EE RPB. Source code is
        maintained at:
        https://github.com/96boards/edk2

    GRUB2
        Provides standardized boot options configuration. 
        Network boot is provided via USB ethernet dongle (Mobile) or built in
        ethernet (Enterprise)

    Fastboot
        Fastboot support is provided for image download and update over USB.

    OP-TEE
        An option will be available to integrate the open source OP-TEE trusted
        OS. Source code is available at:
        https://github.com/op-tee

Boot Delay
~~~~~~~~~~
[CM 1.1] There *should not* be a boot “delay” to wait for user input. Rather
if a key is pressed at boot time (or no bootable file is found) the console
should break into the UEFI menu. There should be a visual indication of this
in case a UART is not in use (for example turn all user LEDs on). 


OP-TEE Open Source Trusted Execution Environment
------------------------------------------------

This is an optional component. By default it will not be configured into an RPB.
However. documentation shall be provided with instructions on how to install it. 

Instructions for the current OP-TEE build for HiKey can be found here:

 - https://github.com/OP-TEE/optee_os
 - https://github.com/OP-TEE/manifest

Environments
~~~~~~~~~~~~
OP-TEE runs plain Linux by default on both ARMv7 and ARMv8. But there is also
support to run it on Android. In optee_client there is an Android makefile
(Android.mk), which has been used when running OP-TEE on the Allwinner A80
platform as an  example.

Memory requirements
~~~~~~~~~~~~~~~~~~~

.. glossary::

    SRAM
        Hardware using OP-TEE *should* have at least 256kB. We can go lower than
        that but that will require some manual configuration. Lower than 200kB
        would require us to optimize the code more and/or add more compile time
        flags.

    DDR
        Configurable, but the default setup uses 32MB.

    Use of Console I/O
        During development it is preferable to have two UARTs, one dedicated
        for normal world and one for secure world.

    IRQ/FIQ
        OP-TEE handles both IRQ and FIQ and will re-route IRQ’s that was
        supposed to go to normal world and the Linux kernel.

ARMv8 software components used by OP-TEE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. glossary::

    ARM Trusted Firmware
        Serves as secure monitor. OP-TEE uses a fork since the official ARM-TF
        does not have  support for parsing OP-TEE’s header.

    Tianocore EDK2
        Boot loader.

    build
        Helper makefiles to build OP-TEE.

    busybox
        Used together with gen_roots.

    Foundation_Platformpkg (optional)
        When OP-TEE should be used on FVP.

    gen_rootfs
        Used to create the main root fs. Will work with any root fs, but this
        is very small (7MB).

    Linux kernel (later than 3.18)
        There aren’t many dependencies to other interfaces in kernel in
        OP-TEE’s kernel driver. But there were a couple of API changes (DMA and
        ioremap) after 3.18 and 4.0 which the current driver adheres to. It
        still is easy to backport to older kernels is needed.

    optee_client
        User space client library for OP-TEE.

    optee_linuxdriver
        Out of tree kernel module for OP-TEE.

    optee_os
        The Trusted OS for OP-TEE.

    optee_test
        Test suite for testing OP-TEE.

    repo
        We are using `repo <http://source.android.com/source/using-repo.html>`_
        to set up our environment. There are a couple different manifests for
        various targets.

    Toolchains
        We are using both a mix of 32- and 64-bit compilers:
         - gcc-linaro-aarch64-linux-gnu-4.9-2014.08_linux.tar.xz:
           For user space
         - gcc-linaro-aarch64-none-elf-4.9-2014.07_linux.tar.xz:
           For kernel, ARM-Trusted-Firmware, Tianocore.
         - gcc-linaro-arm-linux-gnueabihf-4.9-2014.08_linux.tar.xz
           For secure side code (optee_os)

ARMv7 Key Differences
~~~~~~~~~~~~~~~~~~~~~

.. glossary::

    bios_qemu_tz_arm
        Bios blob for QEMU that parses the device tree blob before giving the
        DT blob to the kernel.

    QEMU (Optional)
        When running OP-TEE in an emulated ARMv7 environment.

    soc_term (optional)
        Handles serial port for secure and non-secure side when using OP-TEE.

    Toolchains
        gcc-linaro-arm-linux-gnueabihf-4.9-2014.08_linux.tar.xz
        Everything, since we are only running in 32bit mode here.


Kernel
------

[CM 2.0] Supported boards *shall* use unmodified Reference Platform Kernel
(RPK) [ref6]_. Builds that don't use RPK are derivative of Reference Software
Platform.

Distribution
------------

The following distribution blends *shall* be provided:

 - Debian
 - CentOS

Robustness
----------

[CM 3.0] Software running on the board *should not* shutdown or reboot on it's
own.
