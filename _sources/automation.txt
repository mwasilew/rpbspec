.. _chapter-automation:

Test Automation Requirements
============================

The goal of the Reference Software Platform is to allow automated requirement
validation. In order to enable easy automated testing the following items must
be provided:

 - The board *shall* provide access to serial port to interact with bootloader
   and OS console. [AU 1.0]
 - The board *shall* boot on power on without any additional interaction
   (pressing buttons, toggling switches, etc.) [AU 1.1]
 - The board *shall* be able to boot using network (TFTP or PXE) capability in
   bootloader(s) [AU 1.2]
