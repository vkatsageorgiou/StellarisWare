#******************************************************************************
#
# Makefile - Rules for building the SimpliciTI Polling with Access Point device example.
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
# This is part of revision 10636 of the DK-LM3S9D96-EM2-CC2500-SIMPLICITI Firmware Package.
#
#******************************************************************************

#
# Defines the part type that this project uses.
#
PART=LM3S9D96

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
VPATH=../../../SimpliciTI-1.1.1
VPATH+=../../dk-lm3s9d96/drivers
VPATH+=../../../utils

#
# Where to find header files that do not live in the source directory.
#
IPATH=.
IPATH+=../../..
IPATH+=../../../SimpliciTI-1.1.1
IPATH+=../../../SimpliciTI-1.1.1/Components/bsp
IPATH+=../../../SimpliciTI-1.1.1/Components/bsp/boards/dk-lm3s9d96
IPATH+=../../dk-lm3s9d96
IPATH+=../../../SimpliciTI-1.1.1/Components/bsp/drivers
IPATH+=../../../SimpliciTI-1.1.1/Components/mrfi
IPATH+=../../../SimpliciTI-1.1.1/Components/simpliciti/nwk
IPATH+=../../../SimpliciTI-1.1.1/Components/simpliciti/nwk_applications

#
# The default rule, which causes the SimpliciTI Polling with Access Point device example to be built.
#
all: ${COMPILER}
all: ${COMPILER}/simpliciti_polling_dev.axf

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
# Rules for building the SimpliciTI Polling with Access Point device example.
#
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/kitronix320x240x16_ssd2119_8bit.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/set_pinout.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/simpliciti_polling_dev.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/simplicitilib.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/startup_${COMPILER}.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/touch.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/uartstdio.o
${COMPILER}/simpliciti_polling_dev.axf: ${COMPILER}/ustdlib.o
${COMPILER}/simpliciti_polling_dev.axf: ${ROOT}/grlib/${COMPILER}-cm3/libgr-cm3.a
${COMPILER}/simpliciti_polling_dev.axf: ${ROOT}/driverlib/${COMPILER}-cm3/libdriver-cm3.a
${COMPILER}/simpliciti_polling_dev.axf: simpliciti_polling_dev.ld
SCATTERgcc_simpliciti_polling_dev=simpliciti_polling_dev.ld
ENTRY_simpliciti_polling_dev=ResetISR
CFLAGSgcc=-DTARGET_IS_FIRESTORM_RA2 -DSIMPLICITI_CONFIG_HEADER

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
