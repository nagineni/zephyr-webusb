Title: WebUSB Enabled Custom Driver and A Sample Application

This project includes:

1. WebUSB Enabled Custom Driver:
--------------------------------

This enables WebUSB support to the device via the platform capability
descriptors.

For a deeper dive into the WebUSB, refer to
https://github.com/WICG/webusb/blob/gh-pages/explainer.md

WebUSB API Specification:
https://wicg.github.io/webusb/

2. Sample Application:
----------------------

A simple echo application to demonstrate the WebUSB enabled custom
class driver.

This sample application receives the data and echoed back to the
WebUSB based web application (web page) running in the browser at
host.

This application is intended for testing purposes only. For running
real usecase, implement applications based on the WebUSB API:

Building and flashing:
----------------------

Refer to https://wiki.zephyrproject.org/view/Arduino_101 for details on
building and flashing the image into an Arduino 101.

Testing with latest Google Chrome on host
-----------------------------------------

This requires latest Google Chrome and a web application based on
WebUSB API to connect to the USB device. Follow below steps to run
the demo on host.

1. Run the latest dev-channel release of Google Chrome on host.
   https://www.google.com/chrome/browser/desktop/index.html?extra=devchannel

2. Enable "Experimental Web Platform Features" flag in
   chrome://flags/#enable-experimental-web-platform-features.

3. Run chrome with the --disable-webusb-security switch to disable
   WebUSB's CORS-like checks for origin device communication.

4. Implement a web app (web page) using WebUSB API and run
   it on localhost.

   See the sample at https://github.com/nagineni/webusb-serial

   This sample web page demonstrate how to create and use a WebUSB
   interface, as well as demonstrate the communication between browser
   and WebUSB enabled device.

   To host the demo page locally: Clone the repo and start a web server
   in the appropriate directory.
   $ python -m SimpleHTTPServer

5. Connect the board to a host.

6. Once the device is booted, you should see a notification from
   Chrome: "Go to localhost to connect.". Click on the notification
   to open demo page.

7. Click on Connect button to connect to the device.

8. Send some text to the device by clicking on Send button. The demo app
   will receive the same text from the device and display it in the textarea.
