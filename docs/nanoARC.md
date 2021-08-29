---
nav_order: 2
---

# nanoARC
*An tiny open source controller for tiny robots.*

## What is nanoARC?

nanoARC (Adam's Robot Controller) is a 15x15mm robot controller using Bluetooth Low Energy. It is capable of independently driving two DC motors and a servo/ESC - perfect for small robots. Additional features, such as extra motor drivers or motion sensors, can be added by using expansion boards.

nanoARC was designed for antweight robot wars competitions where size is most important and weight is limited to 150g. A video of such events is below:

<iframe width="700" height="440" src="https://www.youtube.com/embed/35GUWOIz-VQ?rel=0" frameborder="0" allowfullscreen></iframe>

## Features
+ Bluetooth Low Energy (BLE 4.0)
+ 2 channel DC motor driver (bidirectional, up to 1.5A each)
+ 9 axis IMU for advanced control methods and stability
+ Servo/ESC output
+ 2 status LEDs
+ 3-11V supply (works with 1 or 2 cell LiPo battery)
+ TX mode by reading PPM from RC transmitters
+ No pairing required
+ Simple manufacturing requirements

## Firmware
The firmware that runs on the TI CC2640 microcontroller is available in [this](https://github.com/adamcatley/nanoARC) repository. TI-RTOS, TI's BLE stack and CCS are used for development.

## Hardware
The main PCB was designed on Upverter and is shown below. Detailed designs, including BOMs and expansion board designs, can be found on the project page [here](https://upverter.com/RobotWars/).

<iframe title="nanoARC" width="700" height="600" scrolling="no" frameborder="0" name="nanoARC" class="eda_tool" src="https://upverter.com/eda/embed/#designId=327cf61723c5d63f,actionId="></iframe>

## Release History

### v1.2 (2017)
+ 2 layer PCB, simplified 1 sided assembly
+ 9 axis IMU added
+ Reduced BOM count

### v1.1 (2016)
+ 2 layer PCB, 1 sided assembly
+ Standard 10 pin programming connector
+ Whip antenna

### v1.0 (2015)
+ 4 layer PCB, two sided assembly
+ Integrated chip antenna
+ Expasnsion ccnnector for add-on boards