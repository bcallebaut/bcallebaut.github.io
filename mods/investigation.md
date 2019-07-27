---
title: Investigations
---
The investigation goes along several axes :
 - __Hardware__ : which components are good candidates to be part of the final product
 - __Software__ : Which software building blocks (Operating Systems, Libraries...) are good candidates for the final product.
 - __Application__ : Which kind of applications are a good fit for the final product(s)
 - __Tooling__ : Which tools to use in order to support the project

# Hardware

## Microcontroller
According to the [requirement document](requirements.md) and the [architecture document](architecture.md) the microcontroller are divided in to the following categories,
each one with specific requirements.

### IO and Communication
 - LCD panel Interface
 - HDMI interface
 - USB 2.0/3.0 Host interface
 - USB 2.0/3.0 device interface
 - Ethernet 100MBit/1GBit
 - Capacitive touch capability
 - SDHC/SDIO

  These microcontroller don't process sensitive data. As such tampering is not a big deal.
  It will alter the functionality of the module but no critical data will be breached.

  - Microchip SAM3/SAM4 microcontroller are good candidates as they support capacitive touch. PIC32 are also potential candidates. Extensive documentation exist for capacitive sensing
  - MSP430 from TI are also a good candidate
  - NXP Kietis KE1SZ are also candidates.
  - STMicroelectronics STM32 support also Capacitive touch

### Audio/midi data routers
  - High Number of serial port (MIDI ports)
  - High number of I2S port

   In this category, the following processors are good candidates:
   - NXP LPC 558x, [LPC55S6X](https://www.nxp.com/products/processors-and-microcontrollers/arm-based-processors-and-mcus/general-purpose-mcus/lpc5500-cortex-m33/high-efficiency-arm-cortex-m33-based-microcontroller-family:LPC55S6x)
   - [Microchip](https://www.microchip.com) PIC32MFDA, SAME5

### Audio processors
  - DSP functionality
  - High MIPS/FLOP
  - UART
  - Audio Interfaces (I2S/McASP)

  Good Candidates are :
  - TI DSP T[MS320C6748](http://www.ti.com/product/TMS320C6748)
  - TI DSP [66K2G12](http://www.ti.com/product/66AK2G12)
  - TI AM3358/ [OSD3558](https://octavosystems.com/octavo_products/osd335x-c-sip/)
  - Octavo systems [OSD32MP15x](https://octavosystems.com/octavo_products/osd32mp15x/)

### Bela Cape
[Bel Cape](https://www.hackster.io/112305/bela-low-latency-audio-sensor-cape-for-pocketbeagle-1615e0) provides a nice set of capes for PocketBeagle and the BeagleBoard.

# Software

## Virtual Rack 
 [VCV](https://github.com/VCVRack/Rack) provides a nice GUI for Virtual Effects based on Eurorack Modules.


# References
 - [History of synth](https://www.hi5electronics.co.uk/a-brief-history-of-synthesizers/)
 - [Digital Waveguide Mesh](https://reuk.github.io/wayverb/waveguide.html) A sound synthesis technique
 - [SyntherJack](https://syntherjack.net/) Some Stuff for DIY synth makers.
 - [Sonic-PI](https://sonic-pi.net/) : Learn programming by making music. For kids and adults.
 - [Pro Audio Files](https://theproaudiofiles.com/) About Music Production
 - [Pure Data](https://puredata.info/) Pure Data is an open source visual programming language for multimedia.
 - [CSound](https://csound.com/) Csound is a sound and music computing system
 - [Faust](https://faust.grame.fr/) Faust (Functional Audio Stream) is a functional programming language for sound synthesis and audio processing
 - [SuperCollider](https://supercollider.github.io/) SuperCollider is a platform for audio synthesis and algorithmic composition
 - [Free Music Sound Sites](https://designmodo.com/free-music-sounds/) If you ever need free sounds.
 - [Physical Sound synthesis](http://homes.esat.kuleuven.be/~bdmdotbe/bdm2013/documents/doc_080327_14.10.pdf) 
 - [Introduction to Computer Music](http://www.indiana.edu/~emusic/etext/toc.shtml) from Jeffrey Hass Indiana University

# Product References
## Pogo Pins and Connectors
 - [Hyte](https://www.hyte.pro/product/m411p.html) Chinese manufacturer of magnetic connectors
 - [Zhenghe](http://www.pogopin.net/Item/Show.asp?m=2&d=894) Chinese manufacturer
 - [NH-Technology](https://www.nh-technology.de/en/federkontakt/federkontakte) A German company
## Digital Audio Workstation 
 - [QTractor](https://qtractor.sourceforge.io/qtractor-index.html#Intro) A DAW written in C++ with the QT framework.
 - [Ardour](https://ardour.org/) a DAW written in C++ based on GTK+ toolkit
 - [Audacity](https://www.audacityteam.org/) a DAW written in C++ using Wx Widgets
 - [VST Plugin SDK](https://github.com/steinbergmedia) directly from [Steinberg](http//www.steinberg.net)
