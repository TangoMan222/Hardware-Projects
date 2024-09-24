# Raspberry Pi 5 NAS Build
**This project documentation is not complete**
This project documents the process of building a 4-bay NAS using a Raspberry Pi 5, 4 SSDs, and OpenMediaVault. This setup is based on a guide by [The DIY Life](https://www.the-diy-life.com/i-built-a-4-bay-raspberry-pi-5-based-nas/), with 3D print files for the enclosure provided by the original creator.

## Table of Contents
- [Introduction](#introduction)
- [Hardware](#hardware)
- [Software Setup](#software-setup)
- [Enclosure Design](#enclosure-design)
- [Final Build](#final-build)
- [Performance Tests](#performance-tests)
- [Power Consumption](#power-consumption)
- [Attribution](#attribution)
- [Final Thoughts](#final-thoughts)

## Introduction
This project aims to create a cost-efficient and highly customizable NAS using the Raspberry Pi 5. The build leverages 3D print files for the enclosure from the original creator to house the Pi and SSDs securely.

## Hardware
The following hardware was used for this build:
- **Raspberry Pi 5**
- **Radxa Penta SATA Hat (Pi 5 Kit)** - Allows up to 5 SATA drives to connect.
- **4 x Crucial 2.5″ BX500 SSDs** - Chosen for their balance between cost and quality.
- **Raspberry Pi 5 Active Cooler** - Custom modified to fit.
- **12V 3A Power Supply**
- **32GB Sandisk Ultra MicroSD Card** - Used for the OS.
- **Noctua 40mm 5V Fan** - For additional cooling.
- **M2.5 Button Head Screws & Brass Inserts** - For securing components.

Optional:
- **Wavelink 2.5G Ethernet Adaptor** - To boost network speeds.

## Software Setup
1. **Operating System**:  
   I installed Raspberry Pi OS Lite on the microSD card using Raspberry Pi Imager. SSH was enabled to allow remote setup.
   
2. **OpenMediaVault Installation**:  
   OpenMediaVault (OMV) was installed using the following script:
   ```bash
   sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
    ```
3. **After installation, I enabled the PCIe port by editing the config file**:
```bash
sudo nano /boot/firmware/config.txt
```

4. **Add the following lines**:
```bash
dtparam=pciex1
dtparam=pciex1_gen=3
```

### RAID Setup:
I set up the 4 SSDs in a RAID 5 configuration to balance storage capacity and redundancy, resulting in 3TB of usable storage.

### Network Access:
The NAS was configured to allow SMB file sharing for Windows, and a user account was created to access the shared folder.

### Enclosure Design
The NAS enclosure was designed by the original creator of the guide, and I used their 3D print files to build the case. Key design features include:
- Vertical arrangement of drives.
- Cooling provided by a 40mm fan.
- LED activity lights on the side for drive status.
- A transparent side window to view the drives.

### Final Build
The NAS was assembled with the following key steps:
- Mounted the Raspberry Pi and Radxa Penta SATA Hat.
- Installed the SSDs and secured them with spacers.
- Connected the active cooler and fan.
- Fitted the enclosure components using M2.5 screws and brass inserts.
- Finalized the setup by attaching the power supply and Ethernet.

### Performance Tests
**Network Speed (1G Ethernet):**  
Copying large files yielded average speeds of 112MB/s.

**Network Speed (2.5G Ethernet):**  
With the 2.5G Ethernet adaptor, speeds increased to 260MB/s for large files.

### Power Consumption
The NAS is very power-efficient, consuming around 9W at idle and 12W under load—significantly lower than most commercial NAS devices.

### Attribution
This build closely follows the original guide by [The DIY Life](https://www.the-diy-life.com/i-built-a-4-bay-raspberry-pi-5-based-nas/).

### Final Thoughts
This Raspberry Pi 5 NAS offers impressive performance for its price, especially with the 2.5G Ethernet upgrade. It’s cost-effective, customizable, and very power-efficient.
