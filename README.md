# ACIT 2420 Makeup Assignment README

Table of Contents
- [Pre-Requirements](#pre-requirements)
- [Setting Up ArchLinux in VirtualBox](#setting-up-archlinux-in-virtualbox)
- [Starting up ArchLinux from VirtualBox](#starting-up-archlinux-from-virtualbox)
- [Setting the Keyboard Layout](#setting-the-keyboard-layout)
- [Boot Mode Verification](#boot-mode-verification)
- [Connecting to The Internet](#connecting-to-the-internet)

## Pre-Requirements

1. You must have the ISO file pre-installed. You can visit the archlinux download page from this [Link](https://archlinux.org/download/)

2. You have VirtualBox installed.

## Setting Up ArchLinux in VirtualBox

1. On VirtualBox, create a new virtual machine with the initial configuration as follows, then click "Next".
- Name: ArchLinux
- Type: Linux
- Version: Arch Linux (64-bit) or (32-bit)

![name and operating system](images/ss1.png)

2. Set the memory size to 2048 then click "Next".

3. Select "Create a virtual hard disk now" then click "Create".

4. Select VDI (VirtualBox Disk Image) then click "Next".

5. Select "Fixed size" then click "Next".

6. Set the file size to 10GB then click "Create".

7. Once the "ArchLinux" VM is displayed on the right side of the VirtualBox application, right-click on "ArchLinux" then click "Settings"

![vm settings](images/ss2.png)

8. Click on "System", then the  "Processor" tab and increase the number of Processor(s) to 2.

9. Click on "Storage", then double click on "Empty" under "Controller: IDE".

10. Click on the small gear icon to the right of the "Optical Drive:" dropdown menu and select "Choose a disk file...".

11. Select the ISO file and click "Open", then click "Ok" to save all changes made.

- Note: You should now see the ISO filename instead of "Empty" under "Controller: IDE"

![vm settings complete](images/ss3.png)

You have successfully created the Arch Linux VM!

## Starting up ArchLinux from VirtualBox

1. Click on the ArchLinux VM that you have created in the previous step and click the "Start" button.

- Note: This will open up a new terminal where we will be interacting with ArchLinux itself.

- **Note:** It will take a little bit of time for ArchLinux to startup. Once it does, the screen should look as the image below.

![start screen archlinux](images/ss4.png)

## Setting the Keyboard Layout

- Note: The default keyboard layout is set to English US. If this is your preferred layout, then skip this section.

1. To view the list of keyboard layouts available, use the command: `ls /usr/share/kbd/keymaps/**/*.map.gz`

2. To use a specific layout, use the command: `loadkeys *filename*`.

- Note: Only include the filename and NOT the extension, `.map.gz` from the list of layouts available.

3. (Optional) You can also set the font by using the `setfont` command.

- Note: The list of font types can be displayed by using the command: `ls /usr/share/kbd/consolefonts`

## Boot Mode Verification

1. Use the command: `ls /sys/firmware/efi/efivars` to have an understanding of which boot mode is being utilized.

- If the command does not give an error, boot mode: UEFI

- If the command does give an error, boot mode: BIOS or CSM

- Note: Refer to the motherboard manual to set the desired boot mode.

![boot mode](images/ss5.png)

## Connecting to The Internet

1. To verify that the network interface is enabled, use the `ip link` command.

- For Ethernet: You will only have to plug in the Ethernet cable.

- For Wi-Fi: You must authenticate with the wireless network using the `iwctl` command.

- For Mobile Broadband Modem: You must connect to the mobile network with the `mmcli` command.

2. Test the connection by using the `ping` command to a destination.

	`ping archlinux.org`

- Note: A successful ping command will look similar to the image below.

![testing internet connection](images/ss6.png)















