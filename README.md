
[![Arduino CI](https://github.com/RobTillaart/74HC590/workflows/Arduino%20CI/badge.svg)](https://github.com/marketplace/actions/arduino_ci)
[![Arduino-lint](https://github.com/RobTillaart/74HC590/actions/workflows/arduino-lint.yml/badge.svg)](https://github.com/RobTillaart/74HC590/actions/workflows/arduino-lint.yml)
[![JSON check](https://github.com/RobTillaart/74HC590/actions/workflows/jsoncheck.yml/badge.svg)](https://github.com/RobTillaart/74HC590/actions/workflows/jsoncheck.yml)
[![GitHub issues](https://img.shields.io/github/issues/RobTillaart/74HC590.svg)](https://github.com/RobTillaart/74HC590/issues)

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/RobTillaart/74HC590/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/release/RobTillaart/74HC590.svg?maxAge=3600)](https://github.com/RobTillaart/74HC590/releases)
[![PlatformIO Registry](https://badges.registry.platformio.org/packages/robtillaart/library/74HC590.svg)](https://registry.platformio.org/libraries/robtillaart/74HC590)


# 74HC590

Arduino library for the 74HC590 8 bit binary counter.


## Description

**Experimental**

This library is to use 74HC590 / 54HV590.

The device is a 8 bit binary counter, so the 8 output lines can show
the values 0x00 to 0xFF. 
The counter can only count up, or reset to zero.
Furthermore the device can control if the internal counter is copied
to the output lines or not.

The library was written to get a better understanding of the possibilities 
the device has to offer.

Read datasheet for details.

As always feedback is welcome. 


### Related

unknown

## Interface

```cpp
#include "74HC590.h"
```

### Constructor

- **74HC590(uint8_t OE, uint8_t CCLR, uint8_t CCKEN, uint8_t CCLK, uint8_t RCLK = 255, uint8_t RCO = 255)**
  - OE    = output enable
  - CCLR  = counter clear
  - CCKEN = counter clock enable
  - CCLK  = counter clock
  - RCLK  = register clock (if 255 ==> RCLK == CCLK)
  - RCO   = register clock OUT (if 255 ==>  no RCO)

### Control

- **void enableOutput()** idem.
- **void disableOutput()** idem.
- **void clearCounter()** set the internal counter to zero.
- **void enableCounter()** enable the increment the internal counter on the RISING edge of CCLK.
- **void disableCounter()** disable the increment the internal counter on the RISING edge of CCLK.


### Pulse

- **void pulseCounter()** increment the internal counter.
- **void pulseRegister()** copy internal counter to output register.


### Cascading

- **uint8_t readRCO()** read back the value of the RCO pin.


## Future

#### Must

- improve documentation
- get hardware to test

#### Should

- investigate applications 
  - counter for external pulses? (how)
  - control a DAC / R2R network?
  - examples.
- CCLK optional / extern?
- derived class 54HC590?

#### Could

- optimize pulseCounter() for AVR (most used).
- optimize pulseRegister() for AVR (most used).


#### Wont


## Support

If you appreciate my libraries, you can support the development and maintenance.
Improve the quality of the libraries by providing issues and Pull Requests, or
donate through PayPal or GitHub sponsors.

Thank you,


