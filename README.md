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
https://matrix-io.github.io/matrix-documentation/matrix-lite/py-reference/alsa-mics/
Follow "option 1" and IGNORE the unknown PCM" errors

# VNC
sudo raspi-config --> Interfacing options --> VNC --> Enable
sudo apt-get install lxsession -y
Boot Options->Desktop / ClI-> Desktop Autologin
Advanced options --> Resolution --> 1080p

# Spotify
sudo apt install snapd -y && snap install spotify #Install snap, then Spotify

OR

https://pimylifeup.com/raspberry-pi-spotify/

# Speech 
https://hub.docker.com/r/superrobertwa/redfordspeech


# Pi-Hole

sudo docker pull pihole/pihole:latest
sudo docker run pihole/pihole:latest -it
sudo docker ps
sudo docker exec -it <container id> bash
sudo pihole -a -p
