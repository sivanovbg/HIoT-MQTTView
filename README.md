<p>
	<img src="https://github.com/sivanovbg/MQTT-SN_GW_802154_V1/blob/master/HIoT%20GW%20Pictures/HobbyIoT%20Logo.png?raw=true" width="10%" align="right"/>
</p>

# HobbyIoT MQTTView

## Summary

HobbyIoT MQTTView is a practical device capable to display data from an MQTT broker on an LCD display by subscribing to the corresponding topics.

Version 1 (V1) implements 2 MQTT topics to display on the LCD

<p align="center">
	<img src="https://github.com/sivanovbg/HIoT-MQTTView/blob/master/HIoT%20MQTTView%20Pictures/HIoT%20MQTTView%20-%20Main%201.jpg?raw=true" width="40%" />
</p>

Version 2 (V2) upgrades to 4 topics together with a simple automation to display " -- " when data from the corresponding sensor is not available (for example - when sensor returns -127).

<p align="center">
	<img src="https://github.com/sivanovbg/HIoT-MQTTView/blob/master/HIoT%20MQTTView%20Pictures/HIoT_MQTTView_v2_2_temps.jpg?raw=true" width="40%" />
</p>



## Resources

HobbyIoT NET website: https://www.hobbyiot.net/

GitHub: https://github.com/sivanovbg/HIoT-MQTTView

Schematics (by circuitdigest.com): https://circuitdigest.com/fullimage?i=inlineimages/u/Interfacing-circuit-diagram-of-LCD-with-ESP12-without-using-Shift-Register.png

Twitter: https://twitter.com/hobbyiot

## Introduction

The HobbyIoT MQTTView subscribes to a number of topics on an MQTT broker and displays them on an LCD display. It uses a small portion of Arduino code to connect to the broker and subscribe to selected topics. Once a data is transmitted from the broker to the device it is displayed on the LCD display. The device is usable to display for example temperature and humidity of a given area without a need of any computer with browser or specific application to display a dashboard.

## Schematics

The HobbyIoT MQTTView device is based on ESP8266 NodeMCU module. It connects to an LCD 1602A display over a standard 4-wire bus and several control signals together with powering. Since the power coming from the ESP8266 is 3.3V the LCD should require to populate an additional DC/DC converter. The footprint for the converter together with two caps are present onto the back side of the LCD. Details and picture: https://www.codrey.com/electronic-circuits/hack-your-16x2-lcd/

<p align="center">
	<img src="https://www.codrey.com/wp-content/uploads/2018/06/5V-to-3V3-LCD-Hack-1.jpg" width="50%" />
</p>

The connection schematic (by circuitdigest.com): https://circuitdigest.com/sites/default/files/inlineimages/u/Interfacing-circuit-diagram-of-LCD-with-ESP12-without-using-Shift-Register.png

<p align="center">
	<img src="https://circuitdigest.com/sites/default/files/inlineimages/u/Interfacing-circuit-diagram-of-LCD-with-ESP12-without-using-Shift-Register.png" width="50%" />
</p>


## Operation

The HobbyIoT MQTTView device needs a small configuration for WiFi credentials, MQTT broker and topics to display data from. Once it's powered on an MQTT connection to the predefined broker is attempted. Once connected, the topics are being subscribed and the device waiting for further data. Other tunning could be required is related with the data nature to be displayed. The exact type, position and unit could be also predefined within the code. All the settings are currently hardcoded into device.

<p align="center">
	<img src="https://github.com/sivanovbg/HIoT-MQTTView/blob/master/HIoT%20MQTTView%20Pictures/HIoT%20MQTTView%20-%20ESP-L.jpg?raw=true" width="50%" />
</p>

<p align="center">
	<img src="https://github.com/sivanovbg/HIoT-MQTTView/blob/master/HIoT%20MQTTView%20Pictures/HIoT_MQTTView_v2_start.jpg" width="50%" />
</p>

<p align="center">
	<img src="https://github.com/sivanovbg/HIoT-MQTTView/blob/master/HIoT%20MQTTView%20Pictures/HIoT_MQTTView_v2_2_temps.jpg" width="50%" />
</p>

## Versions

Current version is V2.
