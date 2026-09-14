# Aqara Cube T1 Pro (Scene Mode)

📋 Blueprint: [aqara-cube-t1-pro-scene-mode.yaml](aqara-cube-t1-pro-scene-mode.yaml)

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fe4t-home%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Faqara-cube-t1-pro-scene-mode%2Faqara-cube-t1-pro-scene-mode.yaml)

## Description

Automation for the Aqara Cube T1 Pro (CTP-R01) in **Scene Mode** via Zigbee2MQTT. Assign custom actions for each side landing face-up, rotate left/right, throw and shake.

See [aqara-cube-t1-pro-action-mode](../aqara-cube-t1-pro-action-mode/README.md) for the counterpart blueprint covering tap/slide/flip gestures in **Action Mode**.

Requires the Zigbee2MQTT "Home Assistant experimental event entities" setting to be enabled so the cube is exposed as an `event` entity, and the cube to be in Scene Mode (the default; press the LINK button 5x swiftly to toggle into Action Mode instead). The event entity does not carry the side number, so a separate sensor entity that reports the currently facing-up side is also required.

## Inputs

- **Cube Event Entity** - The event entity for the cube
- **Cube Side Sensor** - Sensor entity reporting the number (1-6) of the side currently facing up
- **Side 1 Up** through **Side 6 Up** - Action for when the corresponding side comes to rest facing up
- **Rotate Left** - Action for counter-clockwise rotation
- **Rotate Right** - Action for clockwise rotation
- **Throw** - Action for throwing the cube upward
- **Shake** - Action for shaking the cube
