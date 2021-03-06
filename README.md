RoboCTL
=======

RoboCTL is a suite of communication tools for Robotics controllers currently
supporting Lego and Vex PIC-base controllers.

Installation
========================================================================

FreeBSD
-------
    pkg install roboctl

Pkgsrc or pkgsrc-wip
--------------------
If your system provides binary packages (e.g. NetBSD):

    pkgin install roboctl

All other Unix-like systems:

    cd devel/roboctl
    make install (bmake install on non-BSD systems)

Installing manually
-------------------
You will need the following tools:

    make (tested with BSD and GNU)
    A C compiler (tested with Clang and GCC)

    libc, libusb, libbluetooth

Debian based systems generally have separate packages for runtime libraries
and headers, etc., so you will need to install additional packages to enable
compiling roboctl, such as:

    libusb-dev, libbluetooth-dev, bluez-utils


General build instructions
========================================================================

To build, run

    make depend
    make install

The Makefiles default to a PREFIX of /usr/local.  They will expect to
find add-on libraries such as libusb in ${PREFIX}/lib, and headers in
${PREFIX}/include.

If your PREFIX is not /usr/local, run

    make PREFIX=your-prefix

Examples:

If you've installed prerequisites from MacPorts:

    make PREFIX=/opt/local

If you've installed prerequisites from Fink:

    make PREFIX=/sw

Communication ports
========================================================================

Users must have write access to the generic serial, USB or Bluetooth
device(s) to which the controller is connected.

Run "man legoctl", "man vexctl", or "man roboctl" after installing
for more information.

Notes
========================================================================

This software is developed on FreeBSD and Mac OS X.  Porting to other
POSIX platforms with a working libusb should not be difficult.
