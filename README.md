Inspired by: https://github.com/diehardsk/Volumio-OledUI

# OledUI-Remote
---

This code is a "remote"-version of [Maschine2501/NR1-UI](https://github.com/Maschine2501/NR1-UI).

The Idea behind it:

A wireless remote control with SSD1309 SPI Display (128x64) Display and a Raspberry Pi Zero W with a Battery-Pack.

The Project is in an early stage... so be patient ;)

#### [Project on Volumio-Forum](https://forum.volumio.org/256x64-oled-ssd1322-spi-buttons-rotary-interface-t14098.html#p72945)
---

##installation steps
---

#### Make an SD-Card with an "Raspbian Buster Lite" Image ready:

1st - Download Image:
[Raspbian Images](https://www.raspberrypi.org/downloads/raspbian/)

2nd - flash it to the SD-Card:
Use "Win32Diskimager"

3rd - Go to the "root" folder of the SD Card

- Open "config.txt"
  -> remove the "#" before "dtparam=spi=on" to activate SPI

- make a new textfile called "ssh" -> no .txt at the end!

- Make a new textfile called "wpa_supplicant.conf"
  -> put this text in it, and edit it for your case:
```  
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="NETWORK-NAME"
    psk="NETWORK-PASSWORD"
}
```

## 1st step:
---
### configure time(-zone) and update the package list
```
sudo dpkg-reconfigure tzdata

sudo apt-get update
```
## 2nd step:
---
### Update your default pip installation with:
```
sudo apt install python3-pip

sudo pip3 install -U pip

sudo pip3 install -U setuptools
```

## 3th step:
---
### install all dependencies
```
sudo apt-get install -y python3-dev python3-setuptools python3-pip libfreetype6-dev libjpeg-dev build-essential python-rpi.gpio

sudo apt-get install -y python3-rpi.gpio  

sudo apt-get install libopenjp2-7-dev

sudo apt install libtiff5

sudo pip3 install --upgrade setuptools pip wheel

sudo pip3 install socketIO-client

pip3 install luma.oled

sudo apt install libcurl4-openssl-dev libssl-dev

sudo pip3 install pycurl

sudo apt-get install git

```

## 4th step:
---
### install RC2-UI
```
git clone https://github.com/Maschine2501/RC2-UI.git
 
chmod +x ~/RC2-UI/rc2ui.py
 
sudo cp ~/RC2-UI/rc2ui.service /lib/systemd/system/
 
sudo systemctl daemon-reload
 
sudo systemctl enable rc2ui.service

sudo reboot
```


## If something is wrong:
### check the journal!
```
sudo journalctl -fu rc2ui.service
```
## Uninstall
---
```
cd

sudo rm -r RC2-UI

sudo systemctl disable rc2ui.service
```

## Prototype:

![](https://i.ibb.co/C053NSG/20200405-124556.jpg)
![](https://i.ibb.co/qWpqB0M/20200405-124431.jpg)
![](https://i.ibb.co/6JZHbvZ/20200405-124443.jpg)
![](https://i.ibb.co/LNbkMD7/20200405-124453.jpg)
![](https://i.ibb.co/qC3RsWC/20200405-124459.jpg)
![](https://i.ibb.co/Tgk9jLx/20200405-124516.jpg)
![](https://i.ibb.co/3pCNf5G/20200405-124525.jpg)
![](https://i.ibb.co/sFCwjWP/20200405-124529.jpg)
