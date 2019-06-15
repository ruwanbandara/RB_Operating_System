
A Simple OS Design & Implementation To Show Hardware Information
Go to the profile of Ruwan Bandara

Introduction

The RB_OS kernel is written in 16-bit x86 real mode assembly language. This gives the information of the hardware. This provides easy access to BIOS routines for handling the keyboard, screen and floppy drive, so that we don’t need complicated drivers.

Structure
These are the most important files and directories in the AchiOS zip file:

source/ — Contains the entire OS source code
source/bootload/ — Source to generate BOOTLOAD.BIN, which is added to the disk image when building
source/features/ — Components of AchiOS such as FAT12 support, string routines, the BASIC interpreter etc.
source/kernel.asm — The core kernel source file, which pulls in other source files
programs/ — Source code for programs added to the disk image
so that we have to download two things before starting of making the operating system.

nasm
nasm is for converting .asm files to .bin files. Before start making the operating system we need to download this with ubuntu terminal. Code is given below.

sudo apt-get install nasm

qemu
qemu is used for making the operating system run on our Ubuntu OS terminal.

sudo apt-get install qemu

How to build
sudo bash ./build-linux.sh
How to run on Ubuntu terminal
sudo qemu-system-i386 -soundhw pcspk -drive format=raw,file=disk_images/kavios.flp,index=0,if=floppy
Following screenshots are from RBOS


Reference

Mike OS — http://mikeos.sourceforge.net/#handbooks

NASM — https://www.nasm.us/

Qemu — https://www.qemu.org/
