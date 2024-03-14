# MBot Codebase Guide

## Overview
- Public:
  - mbot_sys_utils
  - mbot_lcm_base
  - [mbot_firmware](#mbot_firmware)
  - rplidar_lcm_driver
  - mbot_web_app
  - mbot_gui
  - mbot_bridge
  - mbot_autonomy_template
  - mbot_apriltag
  - mbot_hardware
- Private:
  - mbot_autonomy

## mbot_firmware
Can modify:
- `/python` - test scripts written in python
- `/src` - C files related to specific robots

Should not modify:
- `comms`
- `lib`
- `mbot`
- `rc`
- `tests`
