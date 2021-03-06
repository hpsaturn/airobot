# AIRobot

ESP32 robot platform, the idea is join it with a [MaixPy RISC-V](https://maixpy.sipeed.com/en/) camera. For now the current development works with a M5StickC Joystick hat that controlling the robot via UDP using protobuf (nanopb). In the robot it use a simple ESP32 board.

## TODO

- [x] Platformio project (two sources)
- [x] UDP channel settings in preferences lib
- [x] nanopb (protocol buffers implementation) for joystick messages
- [x] separated OTA (joystick and robot)
- [ ] MQTT channel ?
- [ ] SPI connection to MaxiPy nano camera
- [ ] Push AI models via proto
- [ ] Auto navegation
- [ ] Seek and destroy objects

## Firmware

You can build it with Arduino IDE renaming the main files to .ino, but it is more easy if you use PlatformIO, with a simple command you upload both, Joystick and Robot. Connect first the robot board and then the joystick to the USB of your computer and run:

```bash
pio run --target upload
```

Please check the right USB ports on `platformio.ini` file.

### OTA (WiFi update)

After the first upload to both boards, you could comment the robot and joystick `default_envs` definition in platformio.ini and uncomment the OTA defaults line for upload via WiFi without USB. Also with VisualCode IDE, you can choose these default envs in the botom tool bar.

## Usage

Turn on the robot, then the joystick, when the joystick detect the robot, push the M5 button for some seconds for pair, after that it should show the sticks values and controlling the robot. For turn off the joystick press again the M5 button.

## DIY Robot

For the instructions and more details [here](https://www.thingiverse.com/thing:4705776).

[![Youtube demo](http://img.youtube.com/vi/GmQLIsL-Mts/0.jpg)](http://www.youtube.com/watch?v=GmQLIsL-Mts "Joystick WiFi using nanopb (protobuff) over a ESP32 caterpillar")
