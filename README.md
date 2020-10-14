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
