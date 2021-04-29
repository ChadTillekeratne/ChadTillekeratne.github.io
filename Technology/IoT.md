# IoT - Internet of Things

## My Principles
As I look at IoT, it's a trendy market. It's yet another buzzword that companies are trying to duct tape to existing solutions.  It's a short term, not long term.

1. Stupid Smart
   1. shall not simply be an internet connected device, it shall provide useable functionality
1. Invisible
   1. Does not bring additional views that are not required.  It makes life easy, not harder
4. Temporary and Forever
   1. Shall have a long life, but also be able to be replaced.  Antipattern - intercoms built into old houses
5. Non-Proprietary
   1. Ability to switch between companies, no lockin
6. Secure
   1. Isolated
   2. Local Only Option
   3. 

## Standards


- Project: CHIP
  - Thread

- [Thread](https://www.threadgroup.org/What-is-Thread/Thread-Benefits) - _low-power wireless mesh networking protocol based on the universally supported Internet Protocol (IP), and built using open and proven standards._

- [CHIP (Connected Home over IP)](https://github.com/project-chip/connectedhomeip#connected-home-over-ip) - _Project Connected Home over IP is a_ new Working Group within the Zigbee Alliance. This Working Group plans to develop and promote the adoption of a new, royalty-free connectivity standard to increase compatibility among smart home products, with security as a fundamental design tenet._
    - Connected Home over IP is the latest effort to standardize on a protocol running over 6LoWPAN to enable home automation, by combining it with DTLS , CoAP and MQTT-SN
    - Datagram Transport Layer Security (DTLS) is a communications protocol that provides security for datagram-based applications by allowing them to communicate in a way that is designed[1][2] to prevent eavesdropping, tampering, or message forgery. The DTLS protocol is based on the stream-oriented Transport Layer Security (TLS) protocol and is intended to provide similar security guarantees. 
    - Constrained Application Protocol (CoAP) is a specialized Internet Application Protocol for constrained devices, as defined in RFC 7252. It enables those constrained devices called "nodes" to communicate with the wider Internet using similar protocols. CoAP is designed for use between devices on the same constrained network (e.g., low-power, lossy networks), between devices and general nodes on the Internet, and between devices on different constrained networks both joined by an internet. CoAP is also being used via other mechanisms, such as SMS on mobile communication networks.





## Communications Protocols

- Bluetooth
- Zigbee
- ZWave
- Wifi
  - Wi-Fi HaLow
  - Wi-Fi Direct
  - Wi-Fi EasyMesh

- 6LoWPAN (IPv6 over Low-Power Wireless Personal Area Networks)
  - Part of Thread

## Platforms and Ecosystems

|Name|Company(s)|Cloud or Local|Offline Options|Protocols|
|--|--|--|--|--|
|HomeKit|Apple|Cloud|Through Apple TV
|Alexa| Amazon
|SmartThings|Samsung
|[openHab (open Home Automation Bus)](https://www.openhab.org/docs/)| OSS|Local
|[HomeAssitance](https://www.home-assistant.io)|OSS|Local

- ecobee
- hue
- wemo
- Kodi
- IKEA Trådfri
- Sonos
- Zignee
- ZWave
- Plex
- [ESPHome](https://esphome.io) - ESPHome is a system to control your ESP8266/ESP32 by simple yet powerful configuration files and control them remotely through Home Automation systems.
- [Home Assistant > MQTT](https://github.com/home-assistant/core/tree/dev/homeassistant/components/mqtt) - (aka MQ Telemetry Transport) is a machine-to-machine or “Internet of Things” connectivity protocol on top of TCP/IP. It allows extremely lightweight publish/subscribe messaging transport.

# Use Cases

|Category|Use Case|Capabilities|Options|
|--|--|--|--|
|Power|Power Outlet|On/Off Power Outlet
|Lighting|Lights|On/Off, Change Color, Change Brightness
|Camera
|Security|Security System
||Door Lock
|Blinds
|Sensor|Air Quality
|Air Conditioning|Heating / Cooling, Thermometer
|Speakers|
|Media|Watching stored media
||Watching live media
|Cleaning|Vaccum|
|Cooking|Stove
||Sous Vide
|Automotive
|Health|Weight


## Inputs
- Phone App (iOS, Android)
- Watch App (Apple Watch)
- Computer App (Windows, Mac)
- Voice Control
- Toggle Switch
- Button
- 

## Sensors
- Motion
- Temperature
- Air Quality 
  - PM 2.5, 1.0
  - VOX
  - Humidity

## Displays

## Automation
- ITTT

