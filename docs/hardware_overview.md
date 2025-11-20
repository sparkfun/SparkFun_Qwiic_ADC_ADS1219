Let's take closer look at the ADS1219 ADC and other hardware on this Qwiic breakout. Refer to the annotated image below as you read through.

<figure markdown>
[![Annotated photo of the Qwiic ADC - AS1219](./assets/img/Qwiic_ADC_AS1219-Annotated.jpg){ width="600"}](./assets/img/Qwiic_ADC_AS1219-Annotated.jpg "Click to enlarge")
</figure>

## ADS1219 Analog-to-Digital Converter

The ADS1219 is a high-precision, 24-bit analog-to-digital converter that communicates over I<sup>2</sup>C. It has two differential or four single-ended inputs managed by an internal input multiplexer, programmable gain settings of 1 or 4, rail-to-rail input buffers to allow connecting high-impedence devices directly to the ADS1219 and has 16 available I<sup>2</sup>C addresses so if you really need it, you can connect 16 of these to have up to 64 single-ended (or 32 differential) analog inputs on a single I<sup>2</sup>C bus! It also features an internal 2.048-V voltage reference and oscillator. Users can provide their own reference voltage throuh the REFN and REFP PTH pins on the board.

The ADS1219 has a supply voltage range of <b>2.3</b> to <b>5.5V</b>. The I<sup>2</sup>C address is configured via connecting the two address select pins (A0 and A1) to four pins on the ADS1219; Ground, DVDD, SDA and SCL. The board includes eight solder jumpers to set the ADS1219's address. Read on to the "Solder Jumpers" section on this page for information on adjusting the ADS1219's I<sup>2</sup>C address.

## Connectors

### Qwiic Connectors

As you'd expect, this breakout includes a pair of Qwiic connectors to easily integrate it into a Qwiic circuit. They connect to the ADS1219's I<sup>2</sup>C signals (SDA/SCL) and also power the ADC with <b>3.3V</b>.

### PTHs

The board breaks out all of the ADS1219's pins to three 0.1"-spaced PTH headers. On one side there is a 6-pin PTH header that routes the ADS1219's data and power pins including the I<sup>2</sup>C signals, reset and data ready pins. The other side of the board has a pair of 6-pin PTH headers. The outer header includes the ADS1219's four analog inputs as well as the positive and negative external reference voltage inputs. The inner header breaks out the ADS1219's analog voltage input (VDDA) along with five ground pins for the analog inputs and analog voltage input. Make sure to open the 3V3/VDDA solder jumper before connecting an external analog voltage input.

## LED

The sole LED on this board is a red power status LED to indicate when the board has power.

## Solder Jumpers

The board has eleven solder jumpers. The list below outlines the functionality of the three solder jumpers not related to setting the device's I<sup>2</sup>C address:

* <b>LED</b> - The LED jumper completes the red power LED circuit and is CLOSED by default. Open this jumper to disable the power LED.
* <b>I<sup>2</sup>C - The I<sup>2</sup>C jumper pulls the SDA and SCL signals to <b>3.3V</b> through a pair of <b>2.2K&ohm;</b> resistors. Open the three-way jumper completely to remove the pull-ups from the bus if needed.
* <b>3V3-VDDA</b>  - The 3V3-VDDA jumper nets the ADS1219's digital and analog supply voltages together to both operate at <b>3.3V</b> and is CLOSED by default. Open this jumper to isolate the two voltages if you're supplying separate voltages for the analog and digital supplies.
 
The other eight jumpers control the ADS1219's I<sup>2</sup>C address and are grouped into labels <b>A1</b> and <b>A0</b>. Each group has solder jumpers labeled <b>G</b> (Ground), <b>V</b> (3.3V), <b>D</b> (SDA) and <b>C</b> (SCL). By default, the board connects both A1 and A0 to Ground and sets the address to <b>0x40</b>. The table below outlines all available configurations and the resulting addresses.

<table>
    <tr>
        <th>A1</th>
        <th>A0</th>
        <th>Address (Unshifted)</th>
    </tr>
        <td>GND</td>
        <td>GND</td>
        <td>0x40 (Default)</td>
    </tr>
    <tr>
        <td>GND</td>
        <td>3.3V</td>
        <td>0x41</td>
    </tr>
    <tr>
        <td>GND</td>
        <td>SDA</td>
        <td>0x42</td>
    </tr>
    <tr>
        <td>GND</td>
        <td>SCL</td>
        <td>0x43</td>
    </tr>
    <tr>
        <td>3.3V</td>
        <td>GND</td>
        <td>0x44</td>
    </tr>
    <tr>
        <td>3.3V</td>
        <td>3.3V</td>
        <td>0x45</td>
    </tr>
    <tr>
        <td>3.3V</td>
        <td>SDA</td>
        <td>0x46</td>
    </tr>
    <tr>
        <td>3.3V</td>
        <td>SCL</td>
        <td>0x47</td>
    </tr>
    <tr>
        <td>SDA</td>
        <td>GND</td>
        <td>0x48</td>
    </tr>
    <tr>
        <td>SDA</td>
        <td>3.3V</td>
        <td>0x49</td>
    </tr>
    <tr>
        <td>SDA</td>
        <td>SDA</td>
        <td>0x4A</td>
    </tr>
    <tr>
        <td>SDA</td>
        <td>SCL</td>
        <td>0x4B</td>
    </tr>
    <tr>
        <td>SCL</td>
        <td>GND</td>
        <td>0x4C</td>
    </tr>
    <tr>
        <td>SCL</td>
        <td>3.3V</td>
        <td>0x4D</td>
    </tr>
    <tr>
        <td>SCL</td>
        <td>SDA</td>
        <td>0x4E</td>
    </tr>
    <tr>
        <td>SCL</td>
        <td>SCL</td>
        <td>0x4F</td>
    </tr>
</table>

## Board Dimensions

The Qwiic ADC - ADS1219 is a standard 1"x1" Qwiic breakout with four mounting holes that fit a 4-40 screw.