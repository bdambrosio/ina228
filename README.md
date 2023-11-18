# INA228 micropython driver

## Copy of https://github.com/megalloid/INA228 modded for micropython for the PICO 

I don't claim to understand git well, so if this not being a formal fork offends anyone, my apologies.

My sincerest thanks to Megalloid - the 228 is the chip I've been waiting for to use in my homebrew off-grid 48V PV system

### Also thanks to Adafruit for making a breakout board! 

## Simple example:

```
from machine import I2C, Pin
import ina228
# address and shunt_ohms shown are default for Adafruit breakout
sensor = ina228.INA228(I2C(0, sda=Pin(4), scl=Pin(5)), address=64,shunt_ohms=0.015) 
sensor.reset_all()
print(sensor.get_current())
print(sensor.get_manufacturer_id())
```

Note there are many other methods, getting voltage and power, setting calibration and offsets, testing for alerts, etc.
