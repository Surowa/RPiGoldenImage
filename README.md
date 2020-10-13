# RPiGoldenImage

Download the latest torrent of Raspberry OS Lite from the official site.
Flash a fresh SD card with Etcher (BalenaEtcher)
Then copy the sideload files (ssh and the wireless conf file) to the boot partition. Wifi WPA password encryption: 
https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md

Start up the RPi and it will have ssh enabled and have the proper wifi settings.

nmap -sP 192.168.178.0/24 will give you a list of IP addresses, try to ssh to it using pi:raspberry

#Passwordless SSH towards RPi
ssh-copy-id pi@<ip address>

# Matrix
curl https://apt.matrix.one/doc/apt-key.gpg | sudo apt-key add -; echo "deb https://apt.matrix.one/raspbian $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/matrixlabs.list; sudo apt-get update;sudo apt-get upgrade -y; sudo apt install matrixio-creator-init -y; sudo apt-get -y install raspberrypi-kernel-headers raspberrypi-kernel git; sudo reboot

git clone https://github.com/matrix-io/matrixio-kernel-modules; cd matrixio-kernel-modules/src && make && make install

Add in /boot/config.txt:

dtoverlay=matrixio
Finally, load the remaining required modules

sudo cp ~/matrixio-kernel-modules/misc/matrixio.conf /etc/modules-load.d/
sudo cp ~/matrixio-kernel-modules/misc/asound.conf /etc/
sudo reboot

https://matrix-io.github.io/matrix-documentation/matrix-lite/py-reference/alsa-mics/
