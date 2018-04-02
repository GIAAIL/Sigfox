# NCTU Smart Campus Project - Sigfox

UnaBiz Taiwan sponsored NCTU with its Dev Kits to boost academic researches and applications with Sigfox.

Links:
* [UnaShield Documentation](https://unabiz.github.io/unashield/)
* [UnaShield Hardware Guide](https://unabiz.github.io/unashield/hardware.html)
* [Arduino library for connecting UnaShield to SIGFOX network](https://github.com/UnaBiz/unabiz-arduino)
  * [Activation](https://github.com/UnaBiz/unabiz-arduino/wiki/Activation)
* Know more about Sigfox

## Setup: Unboxing

You should find your UnaShield in a carton box marked "RCZ4" (Radio Configurations Zone 4, where Taiwan is located). This is very important to recognize your RC Zone, as Sigfox uses different radio frequency in different zones.

<p align="center"><img src="./images/unashield0.jpg" width="75%"></p>

# Activation

After unboxing, attaching antenna to your UnaShield. Later on we'll attach it onto the Arduino board. The version of the shields we have is UnaShield V2S.

<p align="center"><img src="./images/unashield1.jpg" width="75%"></p>

Scan the QR code on the board using your mobile phone, you'll get the Sigfox **Device ID** and **PAC** (Porting Authorization Code). You should also find the same Device ID next to the QR code sticker.

Then, follow [the instructions from step 1 to 7 on this page](https://github.com/UnaBiz/unabiz-arduino/wiki/Activation) to activate your UnaShield.

Brief steps of the activation process:

1. Go to the [Dev Kit Activation](https://backend.sigfox.com/activate/Unabiz) page.
1. Pick your country: Find "Taiwan" and click on the UnaBiz icon.
1. Device information: Enter the Device ID and PAC you just got on your mobile phone.
1. Account details: Enter your personal information if it's your first time registering a device.
   * Check your mailbox for the activation email. Click the link in the message to complete the activation process.
   * Type your password twice.
1. You may now login to the [Backend Portal](http://backend.sigfox.com).

# Attach to Arduino

Now it's time to attach your UnaShield to Arduino. Please note that UnaShield works best with **Arduino Uno**. It is not compatible with all variants of Arduino boards due to different pin definitions.

<p align="center"><img src="./images/unashield2.jpg" width="75%"></p>

UnaShield V2/V2S -- Arduino Uno pin mapping:

* Push-button &rarr; D6 Digital In
* Groove connector #1 &rarr; I2C Digital (SCL & SDA)
* Groove connector #2 &rarr; Analog In/Out (A2 & A3)

UnaShield sensor to Arduino I2C:

* Accelerometer (G-sensor) &rarr; I2C address 0x1C
* Temperature/Humidity/Pressure sensor &rarr; I2C address 0x76

# Test Sigfox transmission
