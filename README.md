# Code Library for the Y-Board

To import it to your Platform IO project, add the following line to your `platformio.ini` file:

```ini
lib_deps = 
    https://github.com/y-board/y-board-v4
```

Here is an example of a full project configuration:

```ini
; PlatformIO Project Configuration File
;
;   Build options: build flags, source filter
;   Upload options: custom upload port, speed and extra flags
;   Library options: dependencies, extra library storages
;   Advanced options: extra scripting
;
; Please visit documentation for the other options and examples
; https://docs.platformio.org/page/projectconf.html

[env:esp32]
platform = espressif32
board = esp32-s3-devkitc-1
framework = arduino

build_flags =   
     -DARDUINO_USB_MODE=1
     -DARDUINO_USB_CDC_ON_BOOT=1
     -DBOARD_HAS_PSRAM

lib_deps =
     https://github.com/y-board/y-board-v4
```

Note: the `-DBOARD_HAS_PSRAM` build flag is required for recording audio to
memory (`start_recording()` with no filename), which stores the recording in
the board's PSRAM.
