# MQTT-Plugin in for MQTT.

This Plugin will automatically create MQTT-Topics for the following signal-types in the Simulation:
- `StringSignal`
- `BooleanSignal`
- `RealSignal`
- `IntegerSignal`

Every singal can be externally subscribed under: `VC/Outputs/#`. The Simulation uses valid JSON.

## Install the Plugin 
Please execute the Installer provided in `Setup\Install`. The Installer tries to defaultly install the content into the Visual Components root (default: `C:\Program Files\Visual Components Premium 4.2`)

## Uninstall the Plugin
Please execute the Installer provided in `Setup\Install` and select `remove`

# Use the Plugin
1. Enable the Panel:

   ![](Docu\EnablePanel.PNG)

2. Typin the MQTT-Broker Address (IP or URI) and Press `connect`. You can only connect to 1 Broker. if the address will be changed, the Client will disconnect from the Broker and connect to the other one.

   ![](Docu\Panel.PNG)

## Topic generation

Every singal can be externally subscribed under: `VC/Outputs/#`. The Simulation uses valid JSON.

The Topics are generated, based on the Structure of the Simulation and uses the Names of the `Components` of the Simulation. For compatibility, the name of the name o the componenten is adapted as follows: `replace every ' ' with '_'` and `replace every '#' with '_'`.

The current Value of the Signal will be available using topic `VC/Outputs/`***topic_of_signal***
The current Value of the Signal can be set by publishing on `VC/Inputs/`***topic_of_signal*** 

## Data Formats:

Internally the Simulation uses the following format for the Signals:

- `StringSignal` = `string`
- `BooleanSignal` = `true` or `fase`
- `RealSignal` = `double`
- `IntegerSignal` = `Int16`