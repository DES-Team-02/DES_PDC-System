# DES_PDC-System
Collection of repositories for SEA:ME [DES_PDC-System](https://github.com/SEA-ME/DES_PDC-System) implementation

## Sensors
- acdc_sensor: Arduino code for ultrasonic sensor
- rmp_sensor: Arduino code for rpm sensor

## Vehicle
- car_control: Main process for driving controls, and receiving inputs from multiple sources
- can_transceiver: Processes CAN data received from multiple sensors
- battery_info: Provides vehicle's battery status informantion to other processes

## Front-end Applications
- Instrument cluster: Provides overview of the vehicle to the user
- Head unit: Provides multimedia features to the user

## Image Processing
- ad_perception: Image processing process for autonomous lane keeping drive mode
- pydbus_module: Acts as a bridge for python dbus and CommonAPI

## Yocto
- meta-dashboard: bitbake layer for instrument cluster
- meta-headunit: bitbake layer for head unit

## Others
- FrancaIDL: Collection of .fidl, .fdepl files used in this project

# Features
## Vehicle
- Controllerable by using gamepad
- Autonomous lane keeping drive mode
- Distance control using proximity sensor
- 2ch CAN bus interface for collection data from sensors
- Internal ethernet route for CommonAPI

## Instrument Cluster
![image](https://github.com/DES-Team-02/DES_PDC-System/assets/56917072/49d5927a-0b9b-4386-9190-76925834c916)
- Speedometer
- Battery Status
- Gear Indicator
- Proximity Indicator
- Turn Indicator
- Media Info
- Darkmode

## Head Unit
![image](https://github.com/DES-Team-02/DES_PDC-System/assets/56917072/e0aac6fc-7287-4013-9ed9-bd10bd7b4a6b)
- Gear Indicator
- Gear Selection
- Music Playback
- Video Playback
- Darkmode

# Hardware Setup
<img width="487" alt="image" src="https://github.com/DES-Team-02/DES_PDC-System/assets/56917072/87b00b24-2856-47f5-8e53-4ae855d66f94">
<img width="1108" alt="image" src="https://github.com/DES-Team-02/DES_PDC-System/assets/56917072/120b7267-f533-4257-a749-e0283cc8862d">

RPM sensor is installed on the rear wheel.
2 Ultrasonic sensors are installed on the front and rear side of the vehicle.
Extra powerbank was used to power up jetson nano, since it is impossible to run motors and 2 ECUs at the same time using single battery pack.
No ethernet cable was used, since all the boards have WLAN interface.

# Communication Diagram
<img width="616" alt="image" src="https://github.com/DES-Team-02/DES_PDC-System/assets/56917072/8ecc4ce0-889a-42b1-98b0-b8aa63c4df83">
CommonAPI-SOME/IP binding was used in this project as an inter process communication. Each application provides data or subscribes to other applications to get the data.

# See also
- [PiRacer](https://www.waveshare.com/wiki/PiRacer_AI_Kit)
- [DES_Instrument-Cluster](https://github.com/SEA-ME/DES_Instrument-Cluster)
- [DES_Head-Unit](https://github.com/SEA-ME/DES_Head-Unit)
- [DES_PDC](https://github.com/SEA-ME/DES_PDC-System)
- [vsomeip in 10 minutes](https://github.com/COVESA/vsomeip/wiki/vsomeip-in-10-minutes)
- [CommonAPI wiki](https://github.com/COVESA/capicxx-core-tools/wiki)
- [Flutter FFI](https://docs.flutter.dev/platform-integration/android/c-interop)
- [Yocto Project](https://docs.yoctoproject.org/overview-manual/yp-intro.html#introducing-the-yocto-project)