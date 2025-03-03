# myPyllant Home Assistant Component

[![GitHub Release](https://img.shields.io/github/release/signalkraft/mypyllant-component.svg)](https://github.com/signalkraft/mypyllant-component/releases)
[![License](https://img.shields.io/github/license/signalkraft/mypyllant-component.svg)](LICENSE)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/signalkraft/mypyllant-component/build-test.yaml)

Home Assistant component that interfacts with the myVAILLANT API using the [myPyllant library](https://github.com/signalkraft/mypyllant).

![myPyllant](https://raw.githubusercontent.com/signalkraft/myPyllant/main/logo.png)

**Alpha, tested on an aroTHERM plus heatpump, sensoCOMFORT VRC 720, and sensoNET VR 921.**

Not affiliated with Vaillant, the developers take no responsibility for anything that happens to your Vaillant devices because of this library.

## Features

![Screenshot](https://raw.githubusercontent.com/signalkraft/mypyllant-component/main/screenshot.png)

* Supports climate & hot water controls, as well as sensor information
* Control operating modes, target temperature, and presets such as holiday more or quick veto
* Track sensor information of devices, such as temperature, humidity, operating mode, energy usage, or energy efficiency
* See diagnostic information, such as the current heating curve, flow temperature, or water pressure

## Entities

You can expect these entities, although names may vary based on your installed devices (in this example "aroTHERM plus" and "Hydraulic Station") or the naming of your heating zones (in this case "Zone 1"):

| Entity                       | Unit   | Class   | Sample   |
|------------------------------|--------|---------|----------|
| Cooling Allowed in Circuit 0 |        |         | off      |
| Error sensoCOMFORT         |  | problem      | off |
| Online Status sensoCOMFORT |  | connectivity | on  |
| Cooling Allowed in Circuit 0 |  |  | off |
| Zone 1 |  |  | auto |
| aroTHERM plus Consumed Electrical Energy Domestic Hot Water | Wh | energy |   0   |
| aroTHERM plus Consumed Electrical Energy Heating            | Wh | energy |   0   |
| aroTHERM plus Earned Environment Energy Domestic Hot Water  | Wh | energy |   0   |
| aroTHERM plus Earned Environment Energy Heating             | Wh | energy | 334.5 |
| aroTHERM plus Heat Generated Heating                        | Wh | energy | 334.5 |
| aroTHERM plus Heat Generated Domestic Hot Water             | Wh | energy |   0   |
| Hydraulic Station Consumed Electrical Energy Domestic Hot Water | Wh | energy | 0 |
| Heating Energy Efficiency |  |  | 4 |
| Cooling Allowed in Circuit 0               |    |             | off     |
| Current Flow Temperature in Circuit 0      | °C | temperature | 22.0    |
| Heating Curve in Circuit 0                 |    |             | 0.8     |
| Min Flow Temperature Setpoint in Circuit 0 | °C | temperature | 35.0    |
| State in Circuit 0                         |    |             | STANDBY |
| Desired Temperature in Zone 1      | °C | temperature | 0.0             |
| Current Temperature in Zone 1      | °C | temperature | 18.5            |
| Humidity in Zone 1                 | %  | humidity    | 60.0            |
| Heating Operating Mode in Zone 1   |    |             | Time Controlled |
| Heating State in Zone 1            |    |             | Idle            |
| Current Special Function in Zone 1 |    |             | None            |
| Tank Temperature Domestic Hot Water 255         | °C | temperature | 47.0            |
| Setpoint Domestic Hot Water 255                 | °C | temperature | 49.0            |
| Operation Mode Domestic Hot Water 255           |    |             | Time Controlled |
| Current Special Function Domestic Hot Water 255 |    |             | Regular         |
| Domestic Hot Water 0 |  |  | Time Controlled |
| Outdoor Temperature | °C | temperature | 2.29 |
| System Mode |  |  | REGULAR |
| Water Pressure | bar | pressure | 1.4 |

## Installation

### HACS

1. [Install HACS](https://hacs.xyz/docs/setup/download)
2. Search for the myVAILLANT integration in HACS and install it
3. Restart Home Assistant
4. [Add myVaillant integration](https://my.home-assistant.io/redirect/config_flow_start/?domain=mypyllant)
5. Sign in with the email & password you use in the myVAILLANT app

### Manual

1. Download [the latest release](https://github.com/signalkraft/mypyllant-component/releases/tag/v0.0.10)
2. Extract the `custom_components` folder to your Home Assistant's config folder, the resulting folder structure should be `config/custom_components/mypyllant`
3. Restart Home Assistant
4. [Add myVaillant integration](https://my.home-assistant.io/redirect/config_flow_start/?domain=mypyllant), or go to Settings > Integrations and add myVAILLANT
5. Sign in with the email & password you use in the myVAILLANT app

## Contributing

> **Warning**
> 
> You need at least Python 3.10

Fork and clone this repo, then from the root directory run:

```shell
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.test.txt
pre-commit install
# Make your changes
pytest
git commit ...
```
