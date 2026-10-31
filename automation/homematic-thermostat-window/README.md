# Homematic Thermostat Window Control

📋 Blueprint: [homematic-thermostat-window.yaml](homematic-thermostat-window.yaml)

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fe4t-home%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fhomematic-thermostat-window%2Fhomematic-thermostat-window.yaml)

## Description

Connects one or more window contacts with a Homematic thermostat. When a window
has been open for the configured delay, the thermostat is set to `off`. When
**all** windows have been closed for the configured delay, it is set to `auto`.

## Inputs

| Input | Description |
| --- | --- |
| Thermostat | The Homematic (`homematicip_local`) climate entity |
| Window Contacts | One or more `binary_sensor` window contacts |
| Open Delay | Window must be open this long before the thermostat is turned off (default 1 min) |
| Close Delay | All windows must be closed this long before switching back to auto (default 30 s) |

## Behaviour and limits

- The thermostat is always switched to `auto` on close, regardless of its mode before
  the window opened.
- The thermostat must support the `off` and `auto` HVAC modes.
- Use one automation per thermostat. Do not use it on a thermostat that is controlled by
  Better Thermostat; use BT's own window sensor option there.
