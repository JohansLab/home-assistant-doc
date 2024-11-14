---
title: "Victron Venus OS Integration"
description: "Documentation for the Victron Venus integration"
ha_release: "next"
ha_category: Sensor
ha_iot_class: "Local Push"
ha_config_flow: true
ha_codeowners:
  - '@JohansLab'
ha_domain: victronvenus

---

The Victron Venus OS integration allows connection to a Venus Victron OS device
 that has local MQTT enabled. This add-on will automatically configure the
  integration through UPnP/Simple Service Discovery Protocol if possible.

### List of exposes sensors

#### Grid Sensors

- The number of grid phases e.g. 1 for single-phase, or 3 for three-phase.
If there is a grid failure then the number of phases will be 0. This can be used
detect grid failure.
- The AC voltage, current and power for each of the available grid phases.
- The combined voltage, current and power for the combined grid input.
- The lifetime running total of all energy consumed from the grid, or fed back
to the grid. These figures generally only makes sense as delta values.

#### Solar Panels

- The DC voltage, current and power of the solar panels.
- The lifetime running total yield of the solar panels. These figures generally
only makes sense as delta values.
- The maximum power produced by the solar panels for the current day.

#### Batteries

- The DC voltage, current and power of the batteries.
- The temperature of the battery.
- The lifetime running total of energy charged and discharged from the battery.
These figures generally only makes sense as delta values.
- The current capacity and installed capacity of the batteries in Ampere-Hours (Ah).
- The state of charge of the batteries.

#### Consumption

- The AC Load in watts on the inverter input.
- The Critical Loads in watts on the inverter output.

### Enabling local MQTT on a Victron Venus device

If your Victron Venus device is not automatically detected ensure that MQTT on
LAN is enabled. To enable MQTT on your device the following instructions can be
followed (as tested on a Cerbo GX):

- Connect to your device using a browser. By default the device should be
 available at [http://venus.local.](http://venus.local./).
- In the menu navigate to Settings > Services and ensure MQTT on LAN is switched
 on.

### Limitations

The integration currently has the following limitations:

- The integration was built and tested against an installation consisting of a
single-phase grid-tied Multiplus Inverter, with a single MPPT Solar Charger and
a battery that contains its own BMS. Your installation might have a different
configuration.
- The integration does not currently support generators and other configuration
 options.
- The integration currently only exposes sensors, it does not yet allow changing
settings from Home Assistant.
- This integration was not tested with MQTT with SSL.
