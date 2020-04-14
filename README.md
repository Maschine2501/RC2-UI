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

## 1st step:
---
### configure time(-zone) and update the package list
```
sudo dpkg-reconfigure tzdata

sudo apt-get update
```
## 2nd step:
---
### install Python 3.5.2
```
sudo apt-get install build-essential libc6-dev

sudo apt-get install libncurses5-dev libncursesw5-dev libreadline6-dev

sudo apt-get install libdb5.3-dev libgdbm-dev libsqlite3-dev libssl-dev

sudo apt-get install libbz2-dev libexpat1-dev liblzma-dev zlib1g-dev

wget https://www.python.org/ftp/python/3.5.2/Python-3.5.2.tgz

tar -zxvf Python-3.5.2.tgz

cd Python-3.5.2

./configure

make -j4

sudo make install

cd

sudo rm -fr ./Python-3.5.2*
```

#### Check Python Version:
```
python3 --version

pip3 -v
```
#### If python3 != 3.5.2, set symlink:
```
alias python3=python3.5
```

## 3rd step:
---
### Update your default pip installation with:
```
sudo pip3 install -U pip

sudo pip3 install -U setuptools
```

## 4th step:
---
### install all dependencies
```
sudo apt-get install -y python3-dev python3-setuptools python3-pip libfreetype6-dev libjpeg-dev build-essential python-rpi.gpio

sudo pip3 install --upgrade setuptools pip wheel

sudo pip3 install socketIO-client

sudo pip3 install --upgrade luma.oled

sudo apt install libcurl4-openssl-dev libssl-dev

sudo pip3 install pycurl
```

## 5th step:
---
### install RC2-UI
```
git clone https://github.com/Maschine2501/RC2-UI.git
 
chmod +x ~/NR1-UI/rc2ui.py
 
sudo cp ~/NR1-UI/rc2ui.service /lib/systemd/system/
 
sudo systemctl daemon-reload
 
sudo systemctl enable rc2ui.service

reboot
```


## If something is wrong:
### check the journal!
```
sudo journalctl -fu rc2ui.service
```

sudo journalctl -fu oledui-nightly.service

## Prototype:

![](https://i.ibb.co/C053NSG/20200405-124556.jpg)
![](https://i.ibb.co/qWpqB0M/20200405-124431.jpg)
![](https://i.ibb.co/6JZHbvZ/20200405-124443.jpg)
![](https://i.ibb.co/LNbkMD7/20200405-124453.jpg)
![](https://i.ibb.co/qC3RsWC/20200405-124459.jpg)
![](https://i.ibb.co/Tgk9jLx/20200405-124516.jpg)
![](https://i.ibb.co/3pCNf5G/20200405-124525.jpg)
![](https://i.ibb.co/sFCwjWP/20200405-124529.jpg)
