#******************************************************************************
#
# Makefile - Rules for building the calibrate example.
#
# Copyright (c) 2009-2013 Texas Instruments Incorporated.  All rights reserved.
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
# This is part of revision 10636 of the RDK-IDM-SBC Firmware Package.
#
#******************************************************************************

#
# Defines the part type that this project uses.
#
PART=LM3S9B92

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
VPATH=../../../third_party/bget
VPATH+=../drivers
VPATH+=../../../utils

#
# Where to find header files that do not live in the source directory.
#
IPATH=.
IPATH+=..
IPATH+=../../..
IPATH+=../../../third_party/bget
IPATH+=../../../third_party/lwip-1.3.2/ports/stellaris/include
IPATH+=../../../third_party/lwip-1.3.2/src/include
IPATH+=../../../third_party/lwip-1.3.2/src/include/ipv4
IPATH+=../../../third_party

#
# The default rule, which causes the calibrate example to be built.
#
all: ${COMPILER}
all: ${COMPILER}/calibrate.axf

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
# Rules for building the calibrate example.
#
${COMPILER}/calibrate.axf: ${COMPILER}/calibrate.o
${COMPILER}/calibrate.axf: ${COMPILER}/kitronix320x240x16_ssd2119_idm_sbc.o
${COMPILER}/calibrate.axf: ${COMPILER}/locator.o
${COMPILER}/calibrate.axf: ${COMPILER}/lwiplib.o
${COMPILER}/calibrate.axf: ${COMPILER}/set_pinout.o
${COMPILER}/calibrate.axf: ${COMPILER}/startup_${COMPILER}.o
${COMPILER}/calibrate.axf: ${COMPILER}/swupdate.o
${COMPILER}/calibrate.axf: ${COMPILER}/touch.o
${COMPILER}/calibrate.axf: ${COMPILER}/ustdlib.o
${COMPILER}/calibrate.axf: ${ROOT}/grlib/${COMPILER}-cm3/libgr-cm3.a
${COMPILER}/calibrate.axf: ${ROOT}/driverlib/${COMPILER}-cm3/libdriver-cm3.a
${COMPILER}/calibrate.axf: calibrate.ld
SCATTERgcc_calibrate=calibrate.ld
ENTRY_calibrate=ResetISR
CFLAGSgcc=-DTARGET_IS_TEMPEST_RB1

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
