.. _chapter-iot:

IoT Reference Platform
======================

IoT Reference Platform does not include *common*/*kernel* section.

Hardware
--------
[IO 1.0] The hardware that the IoT Reference Platform runs on *should* be
96Boards compliant [ref5]_. The following requirements assume that software runs
on 96Boards IoT compliant hardware.

Zephyr
------
Zephyr Project is a small, scalable real-time operating system for use on
resource-constrained systems supporting multiple architectures [ref3]_.
Developers are able to tailor their optimal solution. As a true open source
project, the community can evolve the Zephyr Project to support new hardware,
developer tools, sensor and device drivers.  Advancements in security, device
management capabilities, connectivity stacks and file systems can be easily
implemented.

MyNewt
------
Apache Mynewt is a real-time, modular operating system for connected IoT devices
that need to operate for long periods of time under power, memory, and storage
constraints. The first connectivity stack offered is BLE 4.2 [ref4]_.

The IoT Reference Platform *shall* provide a open-source bootloader that
implements a dual-bank architecture enabling active and passive application
execution.

OTA updates
-----------
[IO 4.0] The IoT Reference Platform *shall* provide a reference/sample
implementation enabling a secure, OTA (over-the-air) update.  When running the
reference application enabling OTA, [IO 4.1] the application *shall* regularly
check with the IoT sw provisioning server, i.e. Hawkbit, over HTTP to determine
if there is an image updated available for deployment. [IO 4.2] The OTA update
*shall* load software onto the currently passive partition and the device will
reboot. [IO 4.3] If the deployment is corrupt or incomplete, the device *shall*
boot from the original partition.

[IO 4.4] The device *shall* communicate via bluetooth to an IoT gateway that has
a route to the Hawkbit server.

SDK
---
[IO 5.0] The IoT Reference Platform *shall* provide all of the necessary tools
and environment with appropriate documentation describing, in detail, how to
rebuild and use the IoT Reference Platform components.

