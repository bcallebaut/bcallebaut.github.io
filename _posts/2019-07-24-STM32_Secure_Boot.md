---
layout: post
title:  "STM32L4 Secure Boot"
date:   2019-07-24 12:14:00 +0200
categories: embedded
---

Today we are discussing about how to boot and protect important assets (keys...) on a STM32L4xxx board.

But first some background information...

# What is secure boot ?
Secure Boot (SB) asserts the integrity and authenticity of the user application image that is
executed: cryptographic checks are used in order to prevent any unauthorized or
maliciously modified software from running. The Secure Boot process implements a Root of
Trust (refer to Figure 1): starting from this trusted component (1), every other component is
authenticated (2) before its execution (3).
>
__Integrity__ is verified so as to be sure that the image that is going to be executed has not
been corrupted or maliciously modified.
__Authenticity__ check aims to verify that the firmware image is coming from a trusted and
known source in order to prevent unauthorized entities to install and execute code.

![Secure Boot](secure_boot1.png)

A second feature that can be added to it is the secure firmware update. In this case, you can upgrade the firmware on the microcontroller with a firmware you know is legitimate.

# Why is it needed ?
A device containing a microcontroller is left alone in the field and as a bunch of communication interface like:
 - Network connection (wired/wireless)
 - Serial Ports
 - A JTAG port
 - USB
 - ...

A device can contain sensitive information (login/password to contact a central server, personal credentials...).

An attacker may want to gain control of it becasue __yes__ there are people who are not __nice__ guys in the world (Not jocking).
>
So if sombody gain access to your device and impersonate you or your client to do nasty stuff like stealing or terrorism attacks, it is very bad for you.

# How to protect

So, you protect your device. There are several levels of protections:
  - Close the ports that are useless (never keep a JTAG port of a serial debug console open in the field)
  - Protect your I/O ports by authentication mechanisms (and not by a stupid or fixed password, you dummy)
  - Make microcontroller resources that shouldn't be accessible inaccessible (Code should be only executable and not readable or writable)
  - Make sure that the onboard firmware and the firmware downloaded is legitimate through cryptographic authentication.
  - Protects your software and hardware against [side Channel Attacks](https://en.wikipedia.org/wiki/Side-channel_attack)

In this article we are discussing about the authentication  of the onboard firmware.

# Anatomy of the Secure Boot
for more information see application note AN5056 on STMicroelecronics website

On the STM32 (default implementation) an application contains 3 parts:
 - __Secure Engine__: protected environment to manage all critical data and operations.
 -  __SBSFU__: Secure Boot and Secure Firmware Update
 - __User Application__ : THe actual application on the device.

This give the following memory map:
![Memory Map](memory_map.png)

The boot sequence looks like :
![Boot sequence](boot_sequence.png)

For this to work you have to set the options bits correctly (enable the flash,RAM... protection) otherwise, there is no protection and generate the cryptographic keys.

Hopefully, these keys are generated as part of the build process (prebuild.bat/prebuild.sh).

# Caveats
Yes there are some.
>
 - The prebuild.sh script is buggy. Correct the first line of it.
 - The Python installation (used by prepareimage.py) is buggy also and only made for Windows. Please use the system python installation. Replace also cryptodomo (deprecated) by a new crypto library.




[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
