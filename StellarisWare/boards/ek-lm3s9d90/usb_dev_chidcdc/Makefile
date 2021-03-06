#******************************************************************************
#
# Makefile - Rules for building the USB composite device hid mouse CSC serial example.
#
# Copyright (c) 2010-2013 Texas Instruments Incorporated.  All rights reserved.
# Software License Agreement
# 
# Texas Instruments (TI) is supplying this software for use solely and
# exclusively on TI's microcontroller products. The software is owned by
# TI and/or its suppliers, and is protected under applicable copyright
# laws. You may not combine this software with "viral" open-source
# software in order to form a larger program.
# 
# THIS SOFTWARE IS PROVIDED "AS IS" AND WITH ALL FAULTS.
# NO WARRANTIES, WHETHER EXPRESS, IMPLIED OR STATUTORY, INCLUDING, BUT
# NOT LIMITED TO, IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE APPLY TO THIS SOFTWARE. TI SHALL NOT, UNDER ANY
# CIRCUMSTANCES, BE LIABLE FOR SPECIAL, INCIDENTAL, OR CONSEQUENTIAL
# DAMAGES, FOR ANY REASON WHATSOEVER.
# 
# This is part of revision 10636 of the EK-LM3S9D90 Firmware Package.
#
#******************************************************************************

#
# Defines the part type that this project uses.
#
PART=LM3S9D90

#
# The base directory for StellarisWare.
#
ROOT=../../..

#
# Include the common make definitions.
#
include ${ROOT}/makedefs

#
# Where to find source files that do not live in this directory.
#
VPATH=../../../utils

#
# Where to find header files that do not live in the source directory.
#
IPATH=../../..

#
# The default rule, which causes the USB composite device hid mouse CSC serial example to be built.
#
all: ${COMPILER}
all: ${COMPILER}/usb_dev_chidcdc.axf

#
# The rule to clean out all the build products.
#
clean:
	@rm -rf ${COMPILER} ${wildcard *~}

#
# The rule to create the target directory.
#
${COMPILER}:
	@mkdir -p ${COMPILER}

#
# Rules for building the USB composite device hid mouse CSC serial example.
#
${COMPILER}/usb_dev_chidcdc.axf: ${COMPILER}/cmdline.o
${COMPILER}/usb_dev_chidcdc.axf: ${COMPILER}/startup_${COMPILER}.o
${COMPILER}/usb_dev_chidcdc.axf: ${COMPILER}/usb_dev_chidcdc.o
${COMPILER}/usb_dev_chidcdc.axf: ${COMPILER}/usb_dev_mouse.o
${COMPILER}/usb_dev_chidcdc.axf: ${COMPILER}/usb_dev_serial.o
${COMPILER}/usb_dev_chidcdc.axf: ${COMPILER}/usb_structs.o
${COMPILER}/usb_dev_chidcdc.axf: ${ROOT}/usblib/${COMPILER}-cm3/libusb-cm3.a
${COMPILER}/usb_dev_chidcdc.axf: ${ROOT}/driverlib/${COMPILER}-cm3/libdriver-cm3.a
${COMPILER}/usb_dev_chidcdc.axf: usb_dev_chidcdc.ld
SCATTERgcc_usb_dev_chidcdc=usb_dev_chidcdc.ld
ENTRY_usb_dev_chidcdc=ResetISR
CFLAGSgcc=-DTARGET_IS_FIRESTORM_RA2

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
