---
title: "Satellite Communication Bus"
summary: Developed and a tested a communication bus and protocol for a CubeSat
date: 2022-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["Satellite", "STM32", "RTOS", "C", "ARM"]
# author: " "
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
# description: "Desc Text."
# canonicalURL: "https://mostafaayesh.com/to/page"
disableHLJS: true # to disable highlightjs
disableShare: true
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: false
ShowWordCount: false
ShowRssButtonInSectionTermList: false
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---
![Demo](/images/cubesat/demo.jpg)
*OpenMCT (PC) **<- UART ->** STM32 NUCLEO-L476RG **<- CAN ->** STM32 B-L475E-IOT01A*
## Purpose
The satellite's communication bus is used to communicate data between the different subsystems of the satellite. The data can be scientific measurements, health data, commands, etc. The purpose of this project is to design and a test an implementation of a communication bus as well as a protocol.

A demonstration has been presented at [McMaster NEUDOSE's](https://mcmasterneudose.ca/) Satellite Team Aerospace Review Show (STARS). In the demonstration scientific data was transmitted from a basic scientific instrument to the On-Board computer module over Controller Area Network (CAN) using the [CubeSat Space Protocol (CSP)](https://github.com/libcsp/libcsp). The scientific data is then transmitted to a computer using serial communication and plotted on [NASA's OpenMCT](https://nasa.github.io/openmct/) mission control software.

### Controller Area Network (CAN)
Controller Area Network (CAN) was chosen as the primary communication bus for the satellite because of its various features including arbitration and its distributed nature.

### Cubesat Space Protocol (CSP)
[CubeSat Space Protocol (CSP)](https://github.com/libcsp/libcsp) is a protocol stack that implements helpful features similar to the TCP/IP stack. It includes a router, a socket buffer pool and a connection oriented socket API.

## Demo
The demo consists of three nodes: the scientific instrument, the on-board computer and the ground station.

### The Scientific Instrument
The goal of the scientific instrument is to periodically collect scientific data and send them to the On-Board Computer over CAN. The scientific data collected includes:
- 3-Axis Acceleration
- Humidity
- 3-Axis Magnetic field strength
- Air pressure
- Temperature

The hardware selected for the scientific instrument is the [B-L475E-IOT01A](https://www.st.com/en/evaluation-tools/b-l475e-iot01a.html) development kit from STMicroelectronics. The reasons behind the selection are:
- Built-in CAN Controller, required for transmitting data over CAN bus to the on-board computer
- Support for [FreeRTOS](https://freertos.org/) real-time operating system which is supported by the CubeSat Space Protocol (CSP)
- There are built in sensors that allows for collection for the scientific data

### The On-Board Computer
The goal of the on-board computer is to collect the scientific data transmitted from the scientific instrument and prepare them to be sent to the ground station over UART (serial).

### The Ground Station
The goal of the ground station is to receive the scientific data from the on-board computer through a serial port. The data is then timestamped, logged and plotted in the user interface.