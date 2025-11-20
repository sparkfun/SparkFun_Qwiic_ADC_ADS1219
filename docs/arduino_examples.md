Let's take a look at a few of the examples included in the SparkFun ADS1219 Arduino Library.

## Example 01 - Single Shot

The first example shows how to take single-shot measurements of a differential input on channels A0 and A1. Open the example by navigating to **File** > **Examples** > **SparkFun ADS1219 Arduino Library** > **Example01_SingleShot**. Select your Board and Port and click the Upload button. After the code finishes uploading, open the [serial monitor](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-serial-monitor/) with the baud set to **115200** and you should see some setup messages print out followed by readings in millivolts.

The example initializes the ADS1219 on the I<sup>2</sup>C bus with default settings and then attempts to take single-shot readings from the ADC. 

## Example 02 - Continuous

The second example shows how to take continuous measurements of a differential input on channels A0 and A1. This example is very similar to the previous one but instead of requesting for a single-shot synched readings, requests continuous readings every 10ms. Open the example from the SparkFun ADS1219 Arduino Library and upload it.

With the serial monitor open and set to **115200**, you should see an initialization message print followed by differential voltage readings from A0 and A1 in millivolts.

## Example 03 - Input Multiplexer

The third example shows how to configure the ADS1219's input multiplexer feature. This adjustable setting lets users set the ADS1219's input multiplexer to one of eight options using the `myADC.setInputMultiplexer();` function. Available settings are:

``` c++
  ADS1219_CONFIG_MUX_DIFF_P0_N1 //(Default)
  ADS1219_CONFIG_MUX_DIFF_P2_N3
  ADS1219_CONFIG_MUX_DIFF_P1_N2
  ADS1219_CONFIG_MUX_SINGLE_0
  ADS1219_CONFIG_MUX_SINGLE_1
  ADS1219_CONFIG_MUX_SINGLE_2
  ADS1219_CONFIG_MUX_SINGLE_3
  ADS1219_CONFIG_MUX_SHORTED
```

## Example 04 - Data Ready Interrupt

The fourth example demonstrates how to use the ADS1219's data ready pin to trigger an interrupt on a connected microcontroller. For this example, you'll need to connect the Data Ready (DRDY) pin to an [interrupt-capable I/O pin](https://docs.arduino.cc/language-reference/en/functions/external-interrupts/attachInterrupt/) on your development board. 

The code defaults to use D4 for the interrupt pin so if you need to switch to another pin, adjust this line:

``` c++
const int interruptPin = 4;
```

The example's setup sets the I<sup>2</sup>C clock speed to 400kHz for better performance and initializes the ADS1219 to read the voltage between AIN0 and Ground, adjusts the gain to x4 and configure the data rate to 1000 samples per second. Lastly, it configures the interrupt to go LOW when data is ready. The main loop just checks to see if the interrupt is seen, clears the flag and then prints readings in millivolts.


