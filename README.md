# Raspberry Pi Zeek
## Deployment of Zeek on a Raspberry Pi 4B<BR />
This is some of my work deploying Zeek NSM on a Raspberry Pi<BR />
Zeek can be found here: https://github.com/zeek<BR />
<img alt="GitHub" src="https://img.shields.io/github/license/bvoris/RaspberryPiZeek">
<img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/m/bvoris/RaspberryPiZeek">
<img alt="GitHub All Releases" src="https://img.shields.io/github/downloads/bvoris/RaspberryPiZeek/total">
<img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/bvoris/RaspberryPiZeek">
<img alt="GitHub language count" src="https://img.shields.io/github/languages/count/bvoris/RaspberryPiZeek">
<img alt="GitHub issues" src="https://img.shields.io/github/issues/bvoris/RaspberryPiZeek">
<img alt="GitHub top language" src="https://img.shields.io/github/languages/top/bvoris/RaspberryPiZeek">

## Initial Deployment:
Install Raspbian Lite
https://www.raspberrypi.org/documentation/installation/installing-images/

## Management Configuration:
Majority of this can be completed via Raspi-config
  ```Bash
  sudo raspi-config
  ```
Change hostname
Change password
Enable SSH
Connect wifi 
  ```Bash
  sudo iwlist wlan0 scan
   ```
Expand file system

#Run Updates and Upgrades
  ```Bash
  sudo apt update && upgrade -y
   ```
  
Reboot


## Check/enable promiscuous mode
Force eth0 into promiscuous mode 
  ```Bash
  ifconfig eth0 promisc
  ```
Run netstat -i to determine if promiscuous mode has been enabled
 ```Bash
  netstat -i
  ```


## Install Pre-Reqs for Zeek
https://docs.zeek.org/en/current/install.html#

## Required Dependencies:
Install all required Zeek dependencies
  ```Bash
  sudo apt-get install cmake make gcc g++ flex bison libpcap-dev libssl-dev python3 python3-dev swig zlib1g-dev -y
  ```
## Optional Dependences:
Install optional dependencies
  ```Bash
	sudo apt-get install python3-git python3-semantic-version libkrb5-dev libjemalloc-dev google-perftools -y
	sudo apt-get install libgoogle-perftools4 perl curl libtcmalloc-minimal4 libgoogle-perftools-dev -y
	sudo apt-get install libtcmalloc-minimal4 -y
	sudo apt-get install libmaxminddb-dev -y 
	sudo apt-get install sendmail sendmail-cf m4 -y
  ```
  Instructions for Geo-IP: https://docs.zeek.org/en/current/frameworks/geoip.html#geolocation<BR />
  Instructions for SendMail: https://tecadmin.net/install-sendmail-on-debian-9-stretch/ 
  
## Install Zeek:
```Bash
git clone --recursive https://github.com/zeek/zeek
cd zeek
./configure --prefix=/opt/zeek --build-type=release
make
make install-aux
```
## Give the current user (pi) ownership of the Zeek binary
```Bash
sudo chown -R pi:pi /opt/zeek
sudo chmod 750 /opt/zeek
```
## Add the Zeek binary path to the bottom of the user profile file - PATH="/opt/zeek/bin:$PATH"
```Bash
nano ~/.profile

source ~/.profile
```
## Run Zeekctl to setup Zeek
```Bash
zeekctl
```
[zeekctl] install
[zeekctl] deploy
[zeekctl] status
[zeekctl] debug

## Connect with me at

<a href="https://twitter.com/HMInfoSecViking?ref_src=twsrc%5Etfw"><IMG SRC="https://github.com/bvoris/bvoris/blob/master/twitter.jpg" WIDTH=10% HEIGHT=10% ALIGN=LEFT></a>

<a href="https://www.linkedin.com/in/brad-voris" target="_blank"><IMG SRC="https://github.com/bvoris/bvoris/blob/master/linkedin.png" WIDTH=10% HEIGHT=4% ALIGN=RIGHT></a>

<BR /><BR />
<BR /><BR />

<A HREF="https://www.victimoftechnology.com">Victim Of Technology<A />
<BR /><BR />
<A HREF="https://www.cyberforgesecurity.com">Cyber Forge Security, Inc.<A />
<BR /><BR />
