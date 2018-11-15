# Setting up a drone for manual flight

### Updated November 15, 2018

#### Required components:

* Pixhawk 2
* Spektrum Radio Receiver
* PPM RC Encoder
* Safety Switch
* Motors (DJI e305)
* Motor Controllers (DJI 430 Lite ESC)
* LiPo battery

#### Introduction

This guide will show you how to configure a custom drone for manual flight with an RC Controller

#### Assemble Drone Hardware

We typically use a [Quadrotor X configuration], but there are more options [here]


#### Wire electrical components

Follow [Pixhawk wiring guide] to connect components to flight controller


#### Set up radio transmitter

1. Remove rotors from the drone if installed, motors may spin unpredictably during bind
2. Insert bind plug into radio receiver on drone (if bind plug is missing, [create your own])
```
Note: The Spektrum Bind button in QGroundControl does not have the same effect, you need a physical bind plug
```  
3. Turn on radio transmitter while holding down bind button (or use bind command on transmitter after powered on)
4. Enter System Setup on radio transmitter and set model type to your vehicle config
5. Enter Channel Assign and make sure all channels match the wirings on the [PPM Encoder]

#### Set Up Ground Control Station

1. [Install QGroundControl]
2. Launch QGroundControl and plug usb cable into Pixhawk
3. Click the setup gears in the top left and update firmware to the most recent version of PX4
4. Unplug and replug Pixhawk to restart

#### Calibrate Pixhawk Sensors

1. Navigate to vehicle setup in QGroundControl
2. Select airframe and choose the one that matches your configuration
3. Navigate to Sensors and follow the instructions to calibrate each
4. Navigate to Radio and turn on transmitter, then click calibrate
5. Choose the DSMX 7 channels or less option and follow on screen instructions to calibrate

#### Arm drone and fly

1. Unplug the usb cable and plug in the battery
2. Press and hold safety switch for a few seconds, then release
3. Move the throttle on the transmitter to the bottom right, hold a few seconds to arm
```
The drone should now be able to fly, try to lift it barely off the ground 
and tune trims to achieve stability
```
3. When finished, move the throttle to the bottom left, hold a few seconds to disarm

If the drone will not arm, plug it back into the computer with QGroundControl running and check the HUD messages
Most likely the drone failed a [preflight check]

[Quadrotor X configuration]: <Hardware Guide.md>
[here]: <https://docs.px4.io/en/airframes/airframe_reference.html>
[Pixhawk wiring guide]: <https://docs.px4.io/en/assembly/quick_start_cube.html>
[create your own]: <https://www.youtube.com/watch?v=FD5Fq62wWj4>
[PPM encoder]: <http://ardupilot.org/copter/docs/common-ppm-encoder.html>
[Install QGroundControl]: https://docs.qgroundcontrol.com/en/getting_started/download_and_install.html>
[preflight check]: <https://docs.px4.io/en/flying/pre_flight_checks.html>
