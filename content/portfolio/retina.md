---
title: "Real-Time Indoor Navigation Assistant "
summary: RETINA aims to make indoor navigation more accessible for the visually impaired
date: 2020-06-01T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["Flutter", "Bluetooth Low Energy (BLE)", "REST API", "SQLite", "Ultra-WideBand (UWB)"]
# author: " "
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
## Motivation
RETINA is a navigation system to assist people with visual impairment navigate buildings. The project utilizes Ultra-Wide Band (UWB) to offer submeter precision and integrates with OpenStreetMaps to take advantage of the existing tools that support OpenStreetMaps to enable community built maps. 

The solution consists of three major components:
- The Ultra-WideBand (UWB) transceiver
- The mobile app
- The server

### Ultra-Wide Band (UWB) Transceiver
The hardware used in the project is [Decawave's DWM1001](https://www.qorvo.com/products/p/DWM1001-DEV) UWB/BLE transceiver. The Bluetooth Low Energy (BLE) connection is used to communicate location data from the device to the user's smartphone.

### The Mobile App
A cross-platform mobile app supporting both Android & iOS and built using [flutter](https://flutter.dev/). 

The source code for the app is available on [Github](https://github.com/MostafaAyesh/retina_app.git).

![App](/images/capstone/app.png)

### The Server
Consists of two main components:
- **[Pelias](https://pelias.io/)** the geocoder used to search nearby destinations and resolve their coordinates.
- **[Valhalla](https://github.com/valhalla/valhalla)** the routing engine used to generate turn by turn instruction between a start and an end point.