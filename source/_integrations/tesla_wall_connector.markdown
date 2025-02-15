---
title: Tesla Wall Connector
description: Instructions on how to integrate Tesla Wall Connector (Gen 3) into Home Assistant.
ha_category:
  - Binary sensor
  - Energy
  - Sensor
ha_release: 2021.12
ha_iot_class: Local Polling
ha_config_flow: true
ha_codeowners:
  - '@einarhauks'
ha_domain: tesla_wall_connector
ha_dhcp: true
ha_platforms:
  - binary_sensor
  - sensor
ha_integration_type: integration
---

The Tesla Wall Connector integration allows you to integrate your Gen 3 [Tesla Wall Connector](https://www.tesla.com/support/home-charging-installation/wall-connector) with Wi-Fi into Home Assistant.

{% include integrations/config_flow.md %}

## Supported functionality

### Entities

The Tesla Wall Connector integration provides the following entities.

#### Sensors
- **Energy** - Running total of energy used by the Wall Connector.
- **Session energy** - Energy used during the current charging session.
- **Status** - Present status of the Wall Connector.
  - **Possible states** - booting, not_connected, connected, ready, negotiating, error, charging_finished, waiting_car, charging_reduced, charging
- **Contactor closed** - Binary sensor indicating if the Wall Connector is currently charging.
- **Grid frequency** - Sensor for grid frequency of the incoming AC power.
- **Grid voltage** - Sensor for grid voltage of the incoming AC power.
- **Handle temperature** - Sensor for temperature of the Wall Connector handle.
- **MCU temperature** - Sensor for temperature of the Wall Connector Main Computing Unit (MCU).
- **PCB temperature** - Sensor for temperature of the Wall Connector Power Control Board (PCB).
- **Phase current** - Sensor for the power current of each incoming AC electricity phase.
- **Phase voltage** - Sensor for the voltage of each incoming AC electricity phase.
- **Vehicle connected** - Binary sensor indicating if a vehicle is connected.
- **Status code** - Sensor for error codes generated by the Wall Connector.

## Energy dashboard

Energy usage can be easily added to the built-in [Energy dashboard](/docs/energy/) using the energy sensor.

To add the Tesla Wall Connector to your Energy dashboard:

1. Navigate to **Settings** > **Dashboards** > **Energy**.
2. In the **Electricity grid** section, select **Add consumption**.
3. Select the Tesla Wall Connector's "Energy" sensor.
4. Select **Save**.
