# Raspberry Pi Zeek
Deployment of Zeek on a Raspberry Pi 4B
This is some of my work deploying Zeek NSM on a Raspberry Pi
Zeek can be found here: https://github.com/zeek

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
  sudo raspi config

Change hostname
Change password
Enable SSH
Connect wifi 
  sudo iwlist wlan0 scan
Expand file system

#Run Updates and Upgrades
  sudo apt update && upgrade -y
  
Reboot


## Check/enable promiscuous mode
Force eth0 into promiscuous mode 
  ifconfig eth0 promisc

Run netstat -i to determine if promiscuous mode has been enabled
  netstat -i



## Install Pre-Reqs for Zeek
https://docs.zeek.org/en/current/install.html#

## Required Dependencies:
Install all required Zeek dependencies
  sudo apt-get install cmake make gcc g++ flex bison libpcap-dev libssl-dev python3 python3-dev swig zlib1g-dev -y

## Optional Dependences:
Install option dependencies
	sudo apt-get install python3-git python3-semantic-version libkrb5-dev libjemalloc-dev google-perftools -y
	sudo apt-get install libgoogle-perftools4 perl curl libtcmalloc-minimal4 libgoogle-perftools-dev -y
	sudo apt-get install libtcmalloc-minimal4 -y
	sudo apt-get install libmaxminddb-dev -y 
		(instructions: https://docs.zeek.org/en/current/frameworks/geoip.html#geolocation)
	sudo apt-get install sendmail sendmail-cf m4 -y
		(Instructions: https://tecadmin.net/install-sendmail-on-debian-9-stretch/ sudo sendmailconfig to config later )

## Install Zeek:
git clone --recursive https://github.com/zeek/zeek
cd zeek
./configure
make
make install

## Run Zeekctl to setup Zeek
/usr/local/zeek/bin $ sudo python3 zeekctl
install

## Connect with me at

<a href="https://twitter.com/HMInfoSecViking?ref_src=twsrc%5Etfw"><IMG SRC="https://github.com/bvoris/bvoris/blob/master/twitter.jpg" WIDTH=10% HEIGHT=10% ALIGN=LEFT></a>

<a href="https://www.linkedin.com/in/brad-voris" target="_blank"><IMG SRC="https://github.com/bvoris/bvoris/blob/master/linkedin.png" WIDTH=10% HEIGHT=4% ALIGN=RIGHT></a>

<BR /><BR />
<BR /><BR />

<A HREF="https://www.victimoftechnology.com">Victim Of Technology<A />
<BR /><BR />
<A HREF="https://www.cyberforgesecurity.com">Cyber Forge Security, Inc.<A />
<BR /><BR />
