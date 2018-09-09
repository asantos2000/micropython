## Flashing ESP32 with micropyhon

Install python 3 dependencies:

`pip install -r requirements.txt`

Test terminal

`python -m serial.tools.miniterm /dev/ttyUSB0 115200`

or with screen

`screen /dev/ttyUSB0 115200`
> Install screen: `sudo apt-get install screen`

## Flashing MicroPython & First Steps

Download micropython

`wget http://micropython.org/resources/firmware/esp8266-20180907-v1.9.4-494-ge814db592.bin`

Connect device and verify

`ls -l /dev/ttyUSB0 # Linux`

Connecting it to your computer via USB, and erasing its flash

`esptool.py --chip esp32 -p /dev/ttyUSB0 erase_flash`

Flashing

`esptool.py --chip esp32 -p /dev/ttyUSB0 write_flash -z 0x1000 ./esp32-20180909-v1.9.4-498-g5cd2c7f2e.bin`

## Tested

* Ubuntu Linux 18 with ESP32 with 4MB

## Refs

* [Miniterm](https://pythonhosted.org/pyserial/examples.html#miniterm)
* [Micropython](http://micropython.org/download)