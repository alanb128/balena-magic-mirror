# balena-magic-mirror
Simple balena implementation of MagicMirror.

Using balena makes MagicMirror super easy to set up and use when your Pi is less accessible/mounted behind a mirror:
- A captive portal for setting/resetting WiFi credentials via another device
- Remotely update the OS and MM application
- Easy remote ssh
- balenaCloud control of the device and environment variables

## Getting Started
Create a [free balenaCloud account](https://dashboard.balena-cloud.com/signup?) and the use the deploy button below to create a new MagicMirror application. Then add a new device (make sure to select "WiFi + Ethernet" if you want your mirror to use WiFi), burn the SD card with [Etcher](https://www.balena.io/etcher/), insert in your Raspberry Pi and apply power. Make sure a display of some sort is connected to your device's HDMI port.


Initially the display may be distorted because the GPU memory default is too low. In your "Device Configuration" tab in the balenaCloud dashboard, click "activate" for "Define device GPU memory in megabytes." and add the value 192 (or higher). The device will reboot and the display should correct itself.

## Configuration
At startup there will be no config do MM will display its startup message. You can enable the sample config by going to the balenaCloud terminal, selecting the magicmirror container, and initiating an ssh connection. Then type the following to enable the sample config file:
```
cd config
cp config.js.sample config.js
```
Restart the magicmirror container from the "services" area of the dashboard so the config changes can take effect.
Once the ssh reconnects, refresh the browser to view the new changes by typing:
```
curl -X POST http://localhost:5011/refresh
```

Power users will want to use the above method to change the contents of the config file to suit one's taste. The Nano text editor has been installed to ease that process somewhat. (The web terminal also supports copy and paste via the left click menu.) The following folders in MagicMirror are persisted between container restarts, so any changes should be maintained:
- `/opt/magic_mirror/config`
- `/opt/magic_mirror/modules`
- `/opt/magic_mirror/css`

