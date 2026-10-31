# Homematic Thermostat Window Control

📋 Blueprint: [homematic-thermostat-window.yaml](homematic-thermostat-window.yaml)

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fe4t-home%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fhomematic-thermostat-window%2Fhomematic-thermostat-window.yaml)

## Description

Connects one or more window contacts with a Homematic thermostat. When a window
has been open for the configured delay, the current state (mode and target
temperature) is saved and the thermostat is turned off. When **all** windows have
been closed for the configured delay, the saved state is restored.

## Inputs

| Input | Description |
| --- | --- |
| Thermostat | The Homematic (`homematicip_local`) climate entity |
| Window Contacts | One or more `binary_sensor` window contacts |
| Open Delay | Window must be open this long before the thermostat is turned off (default 1 min) |
| Close Delay | All windows must be closed this long before restoring (default 30 s) |

## Behaviour and limits

- The previous state is stored in a temporary scene (`scene.window_restore_<thermostat>`),
  created on open and deleted after restoring. It is **lost on a Home Assistant restart**;
  a thermostat that was off at that moment stays off.
- If the thermostat is already off when a window opens, nothing is saved or changed.
- If the thermostat is switched on manually while a window is open, it is not touched on close.
- Use one automation per thermostat. Do not use it on a thermostat that is controlled by
  Better Thermostat; use BT's own window sensor option there.
