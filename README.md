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
7. Disable SWAP: 
	sudo dphys-swapfile swapoff
	sudo dphys-swapfile uninstall
	sudo update-rc.d dphys-swapfile remove
	sudo apt purge dphys-swapfile
	sudo free -m
8. sudo apt-get remove --purge wolfram-engine triggerhappy anacron logrotate xserver-common lightdm
9. sudo apt-get autoremove --purge
10. sudo apt-get clean
11. Assign static IP:  sudo nano /etc/dhcpcd.conf
12. Check Internet access
	a.  ip route
	b. Temp Fix: sudo ip route del 0/0 dev eth0
	c. Permanent Fix change rank of prefeed interface: sudo nano /etc/dhcpcd.conf
		interface eth0
		metric 400;
13. Add host to nodes:
192.168.1.201 pi01 pi01.local pi01.lan
192.168.1.202 pi02 pi02.local pi02.lan
192.168.1.203 pi03 pi03.local pi03.lan
192.168.1.204 pi04 pi04.local pi04.lan

