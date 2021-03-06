SD card using FAT file system

This example application demonstrates reading a file system from
an SD card.  It makes use of FatFs, a FAT file system driver.  It
provides a simple widget-based console on the display and also a UART-based
command line for viewing and navigating the file system on the SD card.

For additional details about FatFs, see the following site:
http://elm-chan.org/fsw/ff/00index_e.html

This application supports remote software update over serial using the
LM Flash Programmer application.  Firmware updates can be initiated by
entering the "swupd" command on the serial terminal.  The LMFlash serial
data rate must be set to 115200bps and the "Program Address Offset" to
0x800.

UART0, which is connected to the 6 pin header on the underside of the
IDM-L35 RDK board (J8), is configured for 115200bps, and 8-n-1 mode.  The
USB-to-serial cable supplied with the IDM-L35 RDK may be used to connect
this TTL-level UART to the host PC to allow firmware update.

-------------------------------------------------------------------------------

Copyright (c) 2008-2013 Texas Instruments Incorporated.  All rights reserved.
Software License Agreement

Texas Instruments (TI) is supplying this software for use solely and
exclusively on TI's microcontroller products. The software is owned by
TI and/or its suppliers, and is protected under applicable copyright
laws. You may not combine this software with "viral" open-source
software in order to form a larger program.

THIS SOFTWARE IS PROVIDED "AS IS" AND WITH ALL FAULTS.
NO WARRANTIES, WHETHER EXPRESS, IMPLIED OR STATUTORY, INCLUDING, BUT
NOT LIMITED TO, IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE APPLY TO THIS SOFTWARE. TI SHALL NOT, UNDER ANY
CIRCUMSTANCES, BE LIABLE FOR SPECIAL, INCIDENTAL, OR CONSEQUENTIAL
DAMAGES, FOR ANY REASON WHATSOEVER.

This is part of revision 10636 of the RDK-IDM-L35 Firmware Package.
