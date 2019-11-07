# schwabilon-k8s
Creating a cheap alternative bare-metal kubernetes cluster with persistent storage and monitoring

# Table of Contents  
[My Setup](#hardware)  
[Installation](#installation)  


<a name="hardware" />
# My hardware setup
I wanted to experiment with container technology at scale at home. So I decided to explore what that’d be like, and  while I did not want to blow the budget to do this exploration, I choose to built a Raspberry Pi cluster, which have a good cost to performance ratio, and the total power consumption is low.

So lets go over the hardware:

| Amount  | Type                     | Price (Euro)    |
| --------|--------------------------| ----------------|
| 5       | Raspberry Pi 3 model B   | ~165€           |
| 5       | 32 GB micro SD-card      | ~60€            |
| 1       | D-Link Switch 8-Port     | ~9€             |
| 1       | Anker 6-Port USB Charger | ~27€            | 
| 5       | Network cat5 cable       | ~4€             | 
| 5       | Micro USB cable          | ~25€            |
| 1       | RPI stackable CASE       | ~9€             |

For a total of approximately $300 you will have a building block to create a Raspberry Pi cluster.
<a name="installation"/>
# Installation
The following preperation steps need to be executed on all your raspberry pi's.

## Flash your micro SD-cards with HypriotOS
First, we need an operating system. Download and flash [HypriotOS](https://github.com/hypriot/image-builder-rpi/releases). The fastest way to download and flash HypriotOS on your SD cards is by using their [flash tool](https://github.com/hypriot/flash) like so:

`flash --hostname schwabilon-k8s-master https://github.com/hypriot/image-builder-rpi/releases/download/v1.11.4/hypriotos-rpi-v1.11.4.img.zip`

## Start your Raspberry-Pi
After flashing the SD card with the HypriotOS, we can plug in the sd card and startup the pi.
After some initialization time you can ssh into the new setup system:

`ssh pirate@schwabilon-k8s-master.local`

The password **hypriot** will grant you access.

## Install Kubernetes

