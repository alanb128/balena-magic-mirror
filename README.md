# balena-magic-mirror
Simple balena implementation of MagicMirror

## Getting Started
Create a free balenaCloud account and the use the deploy button below to create a new MagicMirror application. Then add a new device (make sure to select "WiFi + Ethernet" if you want your mirror to use WiFi), burn the SD card with Etcher, insert in your Raspberry Pi and apply power. Make sure a display of some sort is connected to your device's HDMI port.


In your "Device Configuration" tab in the balenaCloud dashboard, click "activate" for "Define device GPU memory in megabytes." and add the value 192 (or higher). The device will reboot and the display should correct itself.
