# RaspberryPi_Automount

This program is pretty simple really. Just run it as root and it'll do all the magic for you! If you have a samba server running, it'll automatically share the mounted device too!

Setup:
------

Setting up this is a breeze! Simply place "mountall" somewhere (such as, "/home/pi/bin") then modify the /etc/rc.local file to look like this:

	#!/bin/bash -e
	
	sudo chmod 777 "/home/pi/mountall"
	while true; do
		sudo "/home/pi/mountall"
		sleep 2
	done
	exit 0

If you have configured a samba server, add this to the end of "/etc/samba/smb.conf":

	include = /etc/samba/usb.conf

Done! Any problems, just report it in the issues section of GitHub!