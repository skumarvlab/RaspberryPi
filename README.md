# Raspberry Pi Setup

# Image Download


Raspbian Buster Lite https://www.raspberrypi.org/downloads/raspbian/

# Basic Setup

1. Add mac address on router and assign IP
2. Change passwd
3. Change Hostname
4. Expnad FileSystem
5. sudo apt-get Update
6. sudo apt-get Upgrade
7. sudo apt-get autoremove --purge
8. sudo apt-get clean
9. Assign static IP:  sudo nano /etc/dhcpcd.conf
10. Check Internet access
	a.  ip route
	b. Temp Fix: sudo ip route del 0/0 dev eth0
	c. Permanent Fix change rank of prefeed interface: sudo nano /etc/dhcpcd.conf
		interface eth0
		metric 400;
11. Add host to nodes:
	192.168.1.201 pi01 pi01.local pi01.lan

