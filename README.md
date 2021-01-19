# RPiGoldenImage

Download the latest torrent of Raspberry OS Lite from the official site.
Flash a fresh SD card with Etcher (BalenaEtcher)
Then copy the sideload files (ssh and the wireless conf file) to the boot partition. Wifi WPA password encryption: 
https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md

Start up the RPi and it will have ssh enabled and have the proper wifi settings.

nmap -sP 192.168.178.0/24 will give you a list of IP addresses, try to ssh to it using pi:raspberry

# Passwordless SSH towards RPi
ssh-copy-id pi@<ip address>

# Matrix
Remotely apply matrix.yml

Manually:

https://matrix-io.github.io/matrix-documentation/matrix-lite/py-reference/alsa-mics/
Follow "option 1" TO THE LETTER (don't do any other things) and IGNORE the unknown PCM" errors
Add the device id as well as mentioned here by Samreen: https://community.matrix.one/t/raspberry-pi4-buster-alsa-mics-not-working/2865/5

# Pilight:
Remotely apply redfordcam.yml



# VNC
sudo raspi-config --> Interfacing options --> VNC --> Enable
sudo apt-get install lxsession -y
Boot Options->Desktop / ClI-> Desktop Autologin
Advanced options --> Resolution --> 1080p

# Shared folder
https://www.raspberrypi.org/documentation/remote-access/samba.md
aka:
sudo apt update
sudo apt install samba samba-common-bin smbclient cifs-utils -y
cd && mkdir shared
sudo nano /etc/samba/smb.conf

Add:

[share]
    path = /home/pi/shared
    read only = no
    public = yes
    writable = yes

# Spotify
https://pimylifeup.com/raspberry-pi-spotify/

# Speech 
https://hub.docker.com/r/superrobertwa/redfordspeech
sudo docker pull superrobertwa/redfordspeech:latest
sudo docker run -it -p 8888:80 redfordspeech

# Pi-Hole

sudo docker pull pihole/pihole:latest
sudo docker run pihole/pihole:latest -it
sudo docker ps
sudo docker exec -it <container id> bash
sudo pihole -a -p

# HTTPS e.g. for pi-hole or pilight
https://github.com/texadactyl/diyca/blob/master/docs/preparation_notes.txt

