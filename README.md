# RotaryEncoder

This library allows you to attach a quadrature encoder to pins 2 and 3 of an Arduino.  It uses the Arduino-library
pin-change interrupt callbacks to monitor movement of the encoder.  The quadrature-common pin should be wired to 
ground so that when each axis of the encoder is in-contact it will pull the relevant arduino pin low.

From the main thread, you can poll at leisure to discover the total number of steps (signed) that have 
occurred since the last poll, even if there were many steps.

It's used for implementing simple user interfaces, menu selections, value-adjusters, etc.  Don't use this to monitor
motion on a machine shaft unless you know it's moving slowly and the Arduino interrupts can keep up.
