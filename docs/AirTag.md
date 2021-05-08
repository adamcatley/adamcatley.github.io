---
nav_order: 1
---

# Apple AirTag

This page serves as a central resource for technical details, security research, reverse engineering, and anything else about the Apple AirTag. It is a combination of my own work and a collection of publicly available information.

[Tweet me](https://twitter.com/adamcatley) with corrections/improvements/suggestions.

## Key Facts

- Uses **off the shelf** components, apart from Apple's U1 chip for UWB
- The popular **nRF52832** is used for BLE and NFC
- Sleep curent consumption of **2.3µA** gives over 10 years of potential battery life
- Updates BLE address and advertisement data **once a day** at 02:00 UTC
- Updates last byte of advertisement data every **15 minutes**
- Goes into lost mode exactly **3 days** after being away from owner
- Makes noise once every **6 hours** while in lost mode and movement is detected
- Samples the accelerometer every **10 seconds** when waiting for movement
- Transmits BLE advertisement every **2 seconds** when away from owner's device
- Connection inverval of **1 second** when near owner's device
- Needs at least **1.9V** battery voltage to startup
- 32Mbit flash storage is **unencrypted**
- Programming interface easily accessible via test pads

## Background Research

### Privacy Claims

### Supported devices

Support for the AirTag was introduced in iOS 14.5. Apple lists which iPhone, iPod Touch and iPad devices are supported [here](https://support.apple.com/en-gb/HT211348).

Apple presumably uses authentication to stop non-Apple devices connecting to the AirTag, as connections are terminated by the AirTag shortly after connecting. This could be investigated further to add some kind of Android support, although an Apple ID is needed to benefit from the FindMy network.


## Hardware 

### Teardown

[Twitter Thread](https://twitter.com/adamcatley/status/1388196843184697346)

### PCB Overview

#### Revisions

### Antennas

### Speaker

### Power
<!--- +/- tabs, capacitor --->

## Theory of Operation

### Architecture

### States

### Bluetooth

### UWB

### NFC

## Battery Life

The AirTag is supplied with a CR2032 Lithium coil cell from Panasonic. This has a nominal capacity and voltage of 225mAh and 3V.

![](img/airtag/CR2032%20discharge.png)

I measure a 2.3µA load on the battery while the AirTag is idle. The [datasheet](https://industrial.panasonic.com/cdbs/www-data/pdf2/AAA4000/AAA4000C321.pdf) shows the expected capacity with such a small load to be almost the whole 225mAh. The AirTag will power up from a supply of at least 2V, which works well with the cell's cut off voltage of 2.0V.

This gives a **maximum battery life of at least 11 years**, if the device never came out of sleep.

Achieving a sleep current of 2.3µA is impressive given the nRF52832 alone uses 1.9µA (at 1.8V) while asleep with RTC running, according to its datasheet. This means the rest of the circuitry is designed to be very efficientl, minimise leakage and actively shutdown or remove power from unuused components such as the U1 and flash.

## Privacy

## Security
