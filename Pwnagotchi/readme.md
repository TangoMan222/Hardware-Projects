# Items I used for project:

  - Raspberry Pi Zero (Required)
  - Pi Sugar 2
  - 2.13 e-Paper HAT Waveshare (marked V4)(Required for this tutorial)(possible to be Hatless) 
  - Micro USB cable (Required)
  - 3D Printed case
  - Micro SD Card (32GB) (8GB Required) (UHS-1 and above)

# Software used for project:
 - Pwnagotchi Software (Version I used that worked well)
    - https://github.com/jayofelony/pwnagotchi-torch.git
  - Raspberry Pi Flasher (balenaEtcher works well too)
    - https://www.raspberrypi.com/software/
  - Driver Required to connect to PC (without this the PC won't see it correctly)

# Install

## 1. Flash image onto SD card
  - Download and launch Raspberry Pi Imager 
  - Choose your device(mine is a raspberry pi zero)
  - Under operating system select "Use Custom"
  - Select downloaded .IMG file
  - Select the SD card for Storage device
      - **WARNING THIS WILL ERASE ALL DATA ON THE STORAGE DEVICE**
  - Flash the SD card
  - Read the SD Card on your PC and navigate to the Config.toml file to change settings
      - DO NOT change the config files waveshare-3 setting. it works with v3 and v4.
  - Remove SD card from PC and insert into Pi Zero 

## 2. Booting up
  - Connect the micro-USB cable to the data port of your Pwnagotchi’s RPi0W(inboard port) and the other end to your PC
  - If not your first boot-up:
      - skip the next bullet point
  - If you have never booted your Pwnagotchi before:
      - it will take a few minutes to boot up and/or become visible or responsive.
      - **DO NOT INTERRUPT YOUR PWNAGOTCHI DURING THIS PROCESS** (RSA keys are being generated and losing power could cause them to become corrupt)
          - If corrupted reflashing the SD card should fix the issue
  - If screen is installed the bottom of the screen may display "MANU"
      - Screen may not change due to not updating while in manual mode.
  - Open "device manager" and monitor for a new "USB Serial Device" or "ethernet Gadget"
      - update the driver for the device to the one provided
      - now the device will display as an Ethernet interface
          - I recommend renaming it to something else
  - configure pi with a static IP address:
      - IP: 10.0.0.1
      - Netmask: 255.255.255.0
      - Gateway: 10.0.0.1
      - DNS (if required): 8.8.8.8
  - you can now ping your pi at 10.0.0.2

## 3. PowerShell commands
  - "ssh pi@10.0.0.2" # default password: raspberry
  - answer "yes" to the ECDSA key
  - "passwd" (change password)
  - "sudo su" (switch to root)
  - "passwd" (change password for root)

## 4. Operation
  - plug pi into a power source using the Power Micro USB(Outboard port)
  - Pi should power on and display Auto in the bottom left hand corner.
  - After a couple of minutes it should display AI

Now you are done with the basics of setting up a Pwnagotchi!
