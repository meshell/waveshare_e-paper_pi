# waveshare E-Paper Controll

A modified example to work with the [5.83inch e-Paper HAT](https://www.waveshare.com/wiki/5.83inch_e-Paper_HAT) by [waveshare](https://www.waveshare.com). The library is taken from [https://github.com/waveshare/e-Paper](https://github.com/waveshare/e-Paper) however ecerything not needed for the 5.83inch E-Paper to work on a Respberry Pi Zero is removed.

## Prerequisites
###  Enable SPI

To enable hardware SPI on the Pi we need to make a modification to a system file :

```bash
sudo nano /boot/config.txt
```
Add the following line:
```bash
dtparam=spi=on
```

#### Check If SPI Is Enabled
To check if the SPI module is loaded by the system run the following command :

```bash
lsmod | grep spi_
```

You should see `spi_bcm2835` listed in the output.

### Install python libraries
#### Python 3

```bash
sudo apt-get update
sudo apt-get install python3 python3-pip python3-pil python3-numpy
sudo pip3 install RPi.GPIO
sudo pip3 install spidev
```


## Pin connections
Pin connections can also be viewed in `\lib\waveshare\epdconfig.py` (see also [pinout.xyz](https://pinout.xyz/https://pinout.xyz/)):

| e-Paper HAT  | Broadcom pin | Raspberry Pi Connector |
|:------------:|:------------:|:----------------------:|  
|  VCC         |  3.3 V       |             1          |
|  GND         |  GND         |             6          |
|  DIN         |  MOSI        |            19          |
|  CLK         |  SCLK        |            23          |
|  CS          |  CE0         |            24          |
|  DS          |  25          |            22          |
|  RST         |  17          |            11          |
|  BUSY        |  24          |            18          |





