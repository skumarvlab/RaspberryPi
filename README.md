# Raspberry Pi Setup

# Image Download


Raspbian Buster Lite https://www.raspberrypi.org/downloads/raspbian/

# Basic Setup

1. Connect to router and boot
2. Change passwd: 
	passwd
	sudo passwd
3. Update and Upgrade
	sudo apt-get update
	sudo apt-get upgrade
Change Hostname
4. Setup Host: sudo raspi-config
	Change Hostname
	Expnad FileSystem
	Change Memory Split 16 from 64
5. CleanUp:
	sudo apt-get autoremove --purge
	sudo apt-get clean

