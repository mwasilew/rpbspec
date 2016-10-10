.. _chapter-introduction:

Introduction
============

Purpose and Scope
-----------------

The goal of the Reference Software Platform Lead project is to deliver
Linaro output for ARM SoCs using 96Boards or other compliant hardware
for use cases ranging from the Embedded to the Enterprise segments. The
releases may contain bootloader, kernel, distribution and/or user level
middleware/applications. The releases will comprise loadable software
for 96Boards products or other compliant hardware, reference source code,
and documentation on building the source code, any hardware dependencies
including porting tips for other SoCs, and configurations chosen for the
reference builds.

 

The Reference Software Platform releases are expected to be used by
Linaro members for product development, and by the wider community (
i.e.  
`96Boards.org <https://www.google.com/url?q=http://96boards.org&sa=D&ust=1475849114829000&usg=AFQjCNFTZx7XEZjxmTe105D8WrFoTdKeBw>`__
). Releases will be provided for different segments - for example an
Enterprise release might include reference UEFI/ACPI software to boot
CentOS “out of the box” and a configuration of OpenStack and Hadoop,
configured to run optimally on a 96Boards EE hardware product, with
documentation on hardware dependencies, configuration and build from
source information.


This specification, the |spec-fullname| (|spec|),

**Organization of this document**

* Chapter :ref:`chapter-introduction` introduces the architecture being
  specified by |spec|.
* Chapter :ref:`chapter-common` specifies common requirements for all reference platforms |spec|.
* Chapter :ref:`chapter-iot` specifies IoT version of the |spec|.
* Chapter :ref:`chapter-consumer` specifies Consumer version of the |spec|.
* Chapter :ref:`chapter-enterprise` specifies Enterpise version of the |spec|.

**Conventions Used in this Document**

The word *shall* is used to indicate mandatory requirements strictly to
be followed in order to conform to the standard and from which no
deviation is permitted (*shall* equals *is required to*).

The word *should* is used to indicate that among several possibilities
one is recommended as particularly suitable, without mentioning or
excluding others; or that a certain course of action is preferred but
not necessarily required; or that (in the negative form) a certain
course of action is deprecated but not prohibited (*should* equals *is
recommended that*).

The word *may* is used to indicate a course of action permissible within
the limits of the standard (*may* equals *is permitted*).


Definition of Terms
-------------------

The following nomenclature will be used in this document.

.. glossary::

    Reference Software Platform
        The Reference software platform will consist of a set of “Building
        Blocks” that make up a given Reference Software Platform Build.

    Reference Platform Build (RPB)
        An end to end software implementation delivered on a reference 96Boards
        hardware product. Note that where possible this will include an
        “off-the-shelf” 3rd party distribution without modification.

        Example: Bootloader, kernel and Debian and applications  delivered as an
        RPB on HiKey.

    Component
        A software building block or component that is used to create an RPB.

        Examples: An ARM Trusted Firmware based bootloader, OP-TEE, an OpenStack
        build

