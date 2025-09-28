KB2040-NeoPixel-Minitor-V:
trigger a series of NeoPixel RGBW LED lights using the Motorola V base station accessory ports and an Adafruit KB2040 Featherboard.
When the base station receives its tones a relay closes (pins 2 & 3 on the accessory port), it pulls the KB2040's D0 pin to ground, activating the NeoPixel LEDs connected to D10.

Features:
- Uses the dry contact relay on the Motorola Minitor V base station accessory port.
- Simple active-low trigger from D0 on the KB2040.
- Controls NeoPixel RGBW LEDs.
- Runs on circuitPython for easy cutomization.

Hardware Setup:
- Motorola Minitor V base station
  - accessory port relay: pins2 & 3
- Adafruit KB2040 Featherboard
  - D0 = Trigger input from relay
  - GND = Relay Ground
  - D10 = NeoPixel Data pin
  - 3.3v (USB-C) = NeoPixel V+
- NeoPixel RGBW LED

Note:
- The NeoPixels are powered from the Adafruit KB2040 USB-C 3.3V
- Relay closure = active LOW trigger on KB2040 pin D0
- (R,G,B,W) values can be modified to change color or brightness.
