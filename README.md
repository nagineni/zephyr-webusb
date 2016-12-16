WebUSB for Zephyr OS
====================

This folder contains WebUSB-enabled Serial interface for Zephyr OS.

Compatible Hardware
-------------------

This code has been tested with the Arduino 101.

Getting Started
---------------

1. Make sure you are running the [latest dev-channel release of Google Chrome](https://www.google.com/chrome/browser/desktop/index.html?extra=devchannel).

2. Make sure "WebUSB" and "Experimental Web Platform Features" flags are enabled in chrome://flags/.

Build shell with WebUSB
-----------------------

1. Confirm the [Zephyr SDK] https://www.zephyrproject.org/doc/1.4.0/getting_started/installation_linux.html#zephyr-sdk) has been installed in your system.

2. Clone JavaScript* Runtime for Zephyr* OS (i.e zephyr.js) and make the initial setup.

    `https://github.com/nagineni/zephyr.js.git`

3. Check out the 'webusb_ashell' branch.
   This branch includes the changes that are required to build 'ashell' application with WebUSB support.

   `$ cd zephyr.js`

   `$ git checkout webusb_ashell`

4. Set up ZJS environment variables and get source dependencies

   `$ cd zephyr.js`

   `$ source zjs-env.sh 256`

   `$ make update`

    `$ source deps/zephyr/zephyr-env.sh 256`

5. Build the 'ashell' app

    `$ cd zephyr.js`

    `$ make DEV=ashell`

6. Flash the image: To flash the device with dfu-util, first press the Master Reset button on your Arduino 101, and about three seconds later type:

    make dfu

7. Stop `ModemManager` if it is running on your system:

    On Ubuntu: `sudo service modemmanager stop`

8. When the flashing is done press the Master Reset button one more time to boot your new image. Once the device is booted, you should see a notification from Chrome: "Go to webusb-ashell.appspot.com to connect.". Click on the notification and try the demo by connecting and uploading the JS code.
