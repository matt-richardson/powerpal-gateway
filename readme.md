#ESPHome configs

```bash
brew install esphome
```

Create a `secrets.yaml` in the folder.

## Powerpal Gateway

Originally based on https://tatham.blog/2022/07/16/smart-home-energy-monitoring-in-melbourne-australia/.
Targets the [M5Stack ATOM Lite ESP32](https://shop.m5stack.com/products/atom-lite-esp32-development-kit).

This relies on the secrets:

* `wifi_ssid` - ssid of the wifi network to connect to
* `wifi_password` - password of the wifi network to connect to
* `esphome_encryption_key` - random string, needed for auth to home-assistant
* `esphome_ota_password` - random string, needed for ota updates
* `powerpal_mac_address` - mac address of the powerpal device.
* `powerpal_pairing_code` - pairing code from the powerpal paperwork 


The mac address of the powerpal device can be found by using an android device, and running nRF Connect.
(Note for Android 5.1, the latest app crashes. Version [4.26.1](https://www.apkmirror.com/?post_type=app_release&searchtype=apk&bundles%5B%5D=apkm_bundles&bundles%5B%5D=apk_files&s=nrf) from apkmirror.com works.)

To upload the image:

```bash
esphome run --upload_speed 115200 powerpal-gateway.yaml
```