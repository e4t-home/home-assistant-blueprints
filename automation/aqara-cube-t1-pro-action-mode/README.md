# Aqara Cube T1 Pro (Action Mode)

📋 Blueprint: [aqara-cube-t1-pro-action-mode.yaml](aqara-cube-t1-pro-action-mode.yaml)

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fe4t-home%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Faqara-cube-t1-pro-action-mode%2Faqara-cube-t1-pro-action-mode.yaml)

## Description

Automation for the Aqara Cube T1 Pro (CTP-R01) in **Action Mode** via Zigbee2MQTT. Assign custom actions for tap, slide, flip90, flip180, rotate left/right, throw and shake.

See [aqara-cube-t1-pro-scene-mode](../aqara-cube-t1-pro-scene-mode/README.md) for the counterpart blueprint covering per-side actions in **Scene Mode**.

Requires the Zigbee2MQTT "Home Assistant experimental event entities" setting to be enabled so the cube is exposed as an `event` entity, and the cube to be switched into Action Mode (press the LINK button 5x swiftly).

## Inputs

- **Cube Event Entity** - The event entity for the cube
- **Tap** - Action for tapping the cube while it lies on a side
- **Slide** - Action for sliding the cube across a surface
- **Flip 90°** - Action for flipping the cube 90 degrees onto an adjacent side
- **Flip 180°** - Action for flipping the cube 180 degrees onto the opposite side
- **Rotate Left** - Action for counter-clockwise rotation
- **Rotate Right** - Action for clockwise rotation
- **Throw** - Action for throwing the cube upward
- **Shake** - Action for shaking the cube
