# Esphome-smoker-fan-controller
Fan controller for charcoal smokers and grills using ESPHome 

This uses a fan to precisely control the temperature on a smoker or grill. So far this has only been tested on a kamado-style cermaic grill and has been set up with very conservative gains to avoid overshoots. On a metal grill and at higher temperatures there is less of a risk of overshoots so gains may need to be adjusted accordingly.

This usually holds the temperature to within +/- 4F and has been stable for many >8 hour cooks.

This uses an ESP32 microcontroller and can be used as a standalone device (via the webserver's IP) or integrated with home assistant. All the controls are processed on the device so internet access is not required. The goal of this is to keep costs low so it doesn't include any physical buttons or screens at the moment.

<h2>Hardware</h2>

This uses a 4 pin fan, a few thermometer probes (at least 1 for the grill temperature and multiple others for the meat), and a relay to turn off the fan at low PWM cycles. 

<h2>Features</h2>
This uses PID control with a few different [gain scheduling]([url](https://en.wikipedia.org/wiki/Gain_scheduling)) regions to ensure stability.

With the thermostat turned off, the fan can still be controlled manually by directly setting the fan speed.


