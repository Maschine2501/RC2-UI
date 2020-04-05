Inspired by: https://github.com/diehardsk/Volumio-OledUI

# OledUI-Remote

This code is a "remote"-version of [Maschine2501/Volumio-OledUI](https://github.com/Maschine2501/Volumio-OledUI).

The Idea behind it:

A wireless remote control with SSD1309 SPI Display (128x64) Display and a Raspberry Pi Zero W with a Battery-Pack.

The Project is in an early stage... so be patient ;)

### early scetches for the design of the remote:

![](https://github.com/Maschine2501/OledUI-Remote/blob/master/wiki/MR1%20Top.jpg)
![](https://github.com/Maschine2501/OledUI-Remote/blob/master/wiki/MR1%20Side.jpg)
![](https://github.com/Maschine2501/OledUI-Remote/blob/master/wiki/MR1%20Front.jpg)

![](https://github.com/Maschine2501/OledUI-Remote/blob/master/wiki/MR1%20Top%20C.jpg)
![](https://github.com/Maschine2501/OledUI-Remote/blob/master/wiki/MR1%20Side%20c.jpg)
![](https://github.com/Maschine2501/OledUI-Remote/blob/master/wiki/MR1%20Front%20c.jpg)

#### [Project on Volumio-Forum](https://forum.volumio.org/256x64-oled-ssd1322-spi-buttons-rotary-interface-t14098.html#p72945)



## installation steps (nightly build)


installation steps

Step 1:

sudo apt-get update
 
sudo apt-get install -y python-dev python-pip libfreetype6-dev libjpeg-dev build-essential python-rpi.gpio
 
sudo pip install --upgrade setuptools pip wheel
 
sudo pip install --upgrade socketIO-client-2 luma.oled

sudo apt-get install python-pycurl
 
### Step 1 need to be done once, not every time you want to update.

Step 2:

git clone https://github.com/Maschine2501/OledUI-Remote.git
 
chmod +x ~/OledUI-Remote/oledui-nightly.py
 
sudo cp ~/OledUI-Remote/oledui-nightly.service /lib/systemd/system/
 
sudo systemctl daemon-reload
 
sudo systemctl enable oledui-nightly.service

reboot

installation steps (Update)

### for nightly:

sudo systemctl disable oledui-nightly.service

sudo rm -r OledUI-Remote

### after the steps above, follow Step 2 from "installation steps"

## Log

for the nightly build:

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
