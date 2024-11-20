SparkX Qwiic ADC ADS1219 - 24-Bit 4-Channel
========================================

[![Qwiic ADC ADS1219](URL for picture of part)](URL for product on Sparkfun.com)

[*Qwiic ADC ADS1219 (SKU)*](URL for product on Sparkfun.com)

A lot of the time you just need to add more analog inputs to solve a problem. It happens. The SparkX Qwiic 24-Bit ADC can provide four channels of I2C controlled ADC input to your Qwiic enabled project. These channels can be used as single-ended inputs, or in pairs for differential inputs, running at sample rates of up to 1kHz. What makes this ADC even more powerful is that it has a programmable x1 or x4 gain amplifier that lets you "zoom in" on a very small change in analog voltage (but will still effect your input range and resolution). Utilizing our handy Qwiic system, it is easy to connect it to the rest of your system. However, we have broken out 0.1"-spaced pads too in case you prefer to use a breadboard. The analog inputs and reference pins are all broken out on 0.1"-spaced pads too. This board does not have screw terminals - there was not enough room!

The ADS1219 can use its own internal 2.048V voltage reference for measurements, or you can provide your own reference via the REFP and REFN breakout pads. You can also provide your own VDDA (AVDD) by opening the jumper and connecting a voltage to the VDDA pad. This ADC board has eight address jumpers that let you choose one of sixteen unique addresses (0x40 to 0x4F). With these, you can connect up to sixteen of these on the same I2C bus and have 64 channels of ADC. The maximum resolution of the converter is 24-bits, corresponding to 244.14nV per count at a gain of x1. At a gain of x4, the resolution is 61.04nV per count. Note: the effective resolution is limited to 20-bits.

Repository Contents
-------------------

* **/Documentation** - TI datasheet 
* **/Hardware** - KiCad design files (_pcb, _sch), Schematic (PDF)
* **/Production** - Production panel files (_pcb, gerbers)

Documentation
--------------
* [**Arduino Library**](https://github.com/sparkfun/SparkFun_ADS1219_Arduino_Library) - Arduino library for the ADS1219.

License Information
-------------------

This product is _**open source**_! 

Please review the LICENSE.md file for license information. 

If you have any questions or concerns on licensing, please contact technical support on our [SparkFun forums](https://forum.sparkfun.com/viewforum.php?f=152).

Distributed as-is; no warranty is given.

- Your friends at SparkFun.
