# What even is a "Pwnagotchi"?

Pwnagotchi is an AI-powered tool that leverages Raspberry Pi to automate the process of capturing WPA2 Wi-Fi handshakes. Designed for ethical hacking and security testing, it learns from its environment to optimize and improve its performance in detecting and capturing handshake data. Pwnagotchi helps security professionals identify vulnerabilities in wireless networks, making it a valuable tool for penetration testing and network security assessments.

<img src="/Pwnagotchi/images/Pwnagotchi_img1.jpg" alt="Description" width="500"/>

<img src="/Pwnagotchi/images/Pwnagotchi_img6.jpg" alt="Description" width="500"/>

## Items I used for the project:

- Raspberry Pi Zero (Required)
- Pi Sugar 2  
  <img src="/Pwnagotchi/images/Pwnagotchi_img7.jpg" alt="Description" width="500"/>
- 2.13 e-Paper HAT Waveshare (marked V4) (Required for this tutorial, but possible to be Hatless)  
  <img src="/Pwnagotchi/images/Pwnagotchi_img5.jpg" alt="Description" width="500"/>
- Micro USB cable (Required)
- 3D Printed case  
  <img src="/Pwnagotchi/images/Pwnagotchi_img2.jpg" alt="Description" width="500"/>
- Micro SD Card (32GB) (8GB Required) (UHS-1 and above)  
  <img src="/Pwnagotchi/images/Pwnagotchi_img3.jpg" alt="Description" width="500"/>

## Software used for the project:
- Pwnagotchi Software (Version I used that worked well):
    - [Pwnagotchi Torch](https://github.com/jayofelony/pwnagotchi-torch.git)
- Original Pwnagotchi Project:
    - [Pwnagotchi Official Repository](https://github.com/evilsocket/pwnagotchi)
- Raspberry Pi Flasher (balenaEtcher works well too):
    - [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
- Driver Required to connect to PC (without this, the PC won't recognize it correctly)

## Install

### 1. Flash the image onto the SD card
- Download and launch Raspberry Pi Imager
- Choose your device (mine is a Raspberry Pi Zero)
- Under operating system, select "Use Custom"
- Select the downloaded `.IMG` file
- Select the SD card for the storage device  
    - **WARNING: THIS WILL ERASE ALL DATA ON THE STORAGE DEVICE**
- Flash the SD card
- Once complete, read the SD Card on your PC and navigate to the `config.toml` file to change settings  
    - **DO NOT** change the config file’s `waveshare-3` setting. It works with both V3 and V4.
- Remove the SD card from your PC and insert it into the Pi Zero

### 2. Booting up
- Connect the micro-USB cable to the **data port** of your Pwnagotchi’s RPi0W (inboard port) and the other end to your PC
- If this is not your first boot-up:
    - Skip the next bullet point
- If this is your first boot-up:
    - It will take a few minutes to boot up and/or become visible or responsive
    - **DO NOT INTERRUPT YOUR PWNAGOTCHI DURING THIS PROCESS** (RSA keys are being generated and losing power could corrupt them)
    - If corrupted, reflashing the SD card should fix the issue
- If the screen is installed, the bottom of the screen may display "MANU"
    - The screen may not change due to being in manual mode
- Open "Device Manager" and monitor for a new "USB Serial Device" or "Ethernet Gadget"
    - Update the driver for the device to the one provided
    - The device will now display as an Ethernet interface  
        - You may want to rename it for clarity
- Configure the Pi with a static IP address:
    - IP: `10.0.0.1`
    - Netmask: `255.255.255.0`
    - Gateway: `10.0.0.1`
    - DNS (if required): `8.8.8.8`
- You can now ping your Pi at `10.0.0.2`

### 3. PowerShell commands
- SSH into the Pi:
    ```bash
    ssh pi@10.0.0.2
    ```
- The default password is `raspberry`
- Answer "yes" to accept the ECDSA key
- Change the password:
    ```bash
    passwd
    ```
- Switch to root:
    ```bash
    sudo su
    ```
- Change the root password:
    ```bash
    passwd
    ```

### 4. Operation
- Plug the Pi into a power source using the **power micro-USB** (outboard port)
- The Pi should power on and display "Auto" in the bottom left-hand corner
- After a couple of minutes, it should display "AI"

You’re now done with the basics of setting up a Pwnagotchi!

## Additional Resources

- **Pwnagotchi Documentation**:  
  - [Official Docs](https://pwnagotchi.ai)
- **Community Contributions**:  
  - [Pwnagotchi Add-ons and Plugins](https://github.com/evilsocket/pwnagotchi)
- **Wi-Fi Security and Ethical Hacking**:  
  - [WPA2 Security Overview](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access)

## Disclaimer

**This project is intended for educational and personal use only. Please use it responsibly and ensure that you are only testing against networks you have permission to test. This project is not to be used for malicious purposes.**
