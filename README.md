
# Grow Fingerprint Reader

The fingerprint_grow component allows you to use your R503 with ESPHome.

**Documentation:** https://esphome.io/components/fingerprint_grow

It is a copy of the original esphome fingerprint_grow component, with some refinement of sensing_pin logic and most important - the AuraLed issue fix.
About issue in short - after first AuraLed use, all fingers are Authorized. This issue affects only some sensors, most probably it depends on sensor firmware.  
More about the issue you can find here: https://github.com/esphome/issues/issues/2542  

This issue is somehow related to ESP UART receive buffer, fix is very simple - clear the buffer, before next read :)

## how to use:

Set external component in your fingerprint.yaml file:

```yaml
esp32:
  board: esp32-c3-devkitm-1
  framework:
    type: arduino

external_components:
  # use fingerprint_grow from git
  - source: github://fototakas/esphome-fingerprint
```
