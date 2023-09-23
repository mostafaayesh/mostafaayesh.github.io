---
title: "Model Based Pacemaker"
summary: Implemented a Pacemaker using MATLAB Simulink with hardware code generation for NXP FRDM-K64F
date: 2020-06-01T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["MATLAB" ,"Simulink", "ARM", "C++", "UART"]
author: " "
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
# description: "Model Based Pacemaker"
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
![Model](/images/pacemaker/model.png)
*Example Simulink Model*
## The Project
The Model Based Pacemaker project is an initiative to develop an implementation of the **Boston Scientific** System Specification in **MATLAB Simulink**. In addition to the implementation, educational material is developed to assist students in developing their own implementation in both **SFWRENG 3K04** and **SFWRENG 3MD3** at **McMaster University**. I have been an active contributor to the project and was a teaching assistant for both courses from **2016** to **2022**. 

### Code Generation
Simulink hardware code generation is used to generate C code from the models and compile the code into a binary compatible with the hardware which is an ARM Cortex M4 based microcontroller from NXP [FRDM-K64F](https://www.nxp.com/design/development-boards/freedom-development-boards/mcu-boards/freedom-development-platform-for-kinetis-k64-k63-and-k24-mcus:FRDM-K64F). 

A video including demonstration is available in the [Demo](#demo) section. 

## Contributions
I have contributed to the development of various aspects of the project including both the implementation of a functioning Model Based Pacemaker as well as educational material to guide students towards a working implementation.

### Simulink Models
Simulink models that closely follows the requirements specified by **Boston Scientific's** Pacemaker System Specification. Additional models with **UART** functionality were developed to provide templates for developing their own Device Controller Monitor (DCM) a Graphical User Interface (GUI) used for monitoring and updating the Pacemaker's parameters in real-time without the need of reprogramming.

### Automated Hardware Testing & Verification
An integrated development kit was built to allow students to remotely test their hardware outputs and inputs without the need of oscilloscopes or function generators. I have developed firmware (based on [ARM Mbed](https://os.mbed.com/)) and python scripts to automate the process of testing the circuitry and development boards before packaging and handing them to the students.

The testing procedure starts with a python script that flashes different versions of the firmware to the development boards (using [pyOCD](https://github.com/pyocd/pyOCD) and [pylink](https://github.com/square/pylink)) and communicates with the boards over UART to verify working hardware inputs and outputs by using a set of function tests. The automated testing source code is available on [Github](https://github.com/theguymeyer/heartview/tree/master/course_dev/testing).

<!-- ### Educational Material
> "You never really know something until you teach it to someone else" - John C. Maxwell
 -->

## Publication
A benchmark proposal was submitted to [Applied Verification for Continuous and Hybrid Systems 2022](https://cps-vo.org/group/ARCH) and was accepted for presentation at the conference in **Sep 2022**. The models used for the benchmark proposal are available on [Github](https://github.com/3md3/3md3).


## Demo
The following video contains an overview of the development hardware as well as demonstration of a functional Simulink Model:
<iframe width="100%" height="400" src="https://www.youtube.com/embed/af1o3PwmRa4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>