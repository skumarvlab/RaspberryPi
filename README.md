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
4. Setup Host: sudo reaspi-config
	Change Hostname
	Expnad FileSystem
	Change Memory Split 16 from 64
5. CleanUp:
	sudo apt-get autoremove --purge
	sudo apt-get clean
6. Setup Wifi bi modifying: sudo nano /etc/wpa_supplicant/wpa_supplicant.conf

country=IN
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
        ssid="Sujeet"
        scan_ssid=1
        psk=2da3d890ed248ed4cce2486a8b394e21a29425d1d34c286c32433bf4c5c1d216
        key_mgmt=WPA-PSK
}

7. Add following to (if wpa_supplicant is not ready): sudo nano /etc/rc.local

wpa_supplicant -iwlan0 -D wext -c/etc/wpa_supplicant/wpa_supplicant.conf -B

8. Assign static IP: sudo nano /etc/dhcpcd.conf
	interface eth0
	#metric 203
	static ip_address=192.168.1.201/24
	#static ip6_address=fe80::72fb:8884:2389:c076/64
	static routers=192.168.1.1
	static domain_name_servers=192.168.1.1 8.8.8.8 fd51:42f8:caae:d92e::1
	interface wlan0
	#metric 202
9. Check Internet access
	a.  ip route
	b. Temp Fix: sudo ip route del 0/0 dev eth0
	c. Permanent Fix change rank of prefeed interface: sudo nano /etc/dhcpcd.conf
		interface eth0
		metric 203
		interface wlan0
		metric 202

10. Add host to nodes: sudo nano /etc/hosts

192.168.1.201 pi01 pi01.local pi01.lan

