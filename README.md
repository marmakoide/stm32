# STM32 tutorial projects

This repository is a set of small educational STM32 projects I did for my 
personal entertainment and enlightenment. The development environment is Linux, 
plain C/C++, Makefile, and a shell.

Unless specified otherwise, those projects are targeting the STM32 Nucleo-64 
L476RG board.


## Software environment

I did those project on a vanilla Archlinux install. I installed the following 
packages:

* [arm-none-eabi-gcc](https://archlinux.org/packages/community/x86_64/arm-none-eabi-gcc/) C language toolchain for ARM CPUs and MPUs
* [arm-none-eabi-newlib](https://archlinux.org/packages/community/x86_64/arm-none-eabi-newlib/) C standard library implementation for ARM MPUs
* [picocom](https://archlinux.org/packages/community/x86_64/picocom/) Minimalistic serial terminal

I also installed those packages from the AUR packages repository

* [stlink-git](https://aur.archlinux.org/packages/stlink-git) Uploading tool for STM32 boards

I compiled [libopencm3](https://github.com/libopencm3/libopencm3), a thin, low-level library to
handle STM32 MCUs. As it is not advised to install libopencm3 system-wide, I installed at the
root of this repository. I made a (very naive) script to automate the installation process,
[install-libopencm3](install-libopencm3).


## Projects

* [led-blinker](projects/led-blinker) : blinks the STM32L476RG on-board led


## Authors

* **Alexandre Devert** - [marmakoide](https://github.com/marmakoide)
