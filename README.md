# homebridge-roborock
With this plugin can you control the xiaomi vacuum robots as fan in your Apple Home App (HomeKit).

This plugin use the new [miio](https://github.com/aholstenson/miio) version 0.15.6 or newer, not like the old ones 0.14.1. Timeouts and API errors are a thing of the past!

## Features
* **Fan** as On-/Off-Switch. When switching off, directly back to the charging station.
   * [Fanspeed levels](https://github.com/nicoh88/homebridge-xiaomi-roborock-vacuum/blob/master/models/speedmodes.js) adjustable via 3D Touch / Force Touch.
* Battery status and condition in the device details. Low battery alert.
* Pause switch (optional).
* Occupancy sensor (similar to motion sensor) for dock status (optional).
* Seconds Fan for water box modes (optional).

## Confiruration
- Example `config.json` with one vacuum and room cleaning:

```
"accessories": [
 {
  "accessory": "XiaomiRoborockVacuum",
  "name": "Xiaomi Mi Robot Vaccum 1st Generation",
  "ip": "192.168.1.150",
  "token": "abcdef1234567890abcdef1234567890",
  "pause": false,
  "dock": true,
  "waterBox": false,
  "cleanword": "cleaning",
  "rooms": [
    {
      "id": 16,
      "name": "Livingroom"
    },
    {
      "id": 17,
      "name": "Kitchen"
    }
  ]
 }
],
```

- Example `config.json` with two vacuums:

```
"accessories": [
 {
  "accessory": "XiaomiRoborockVacuum",
  "name": "Xiaomi Mi Robot Vaccum 1st Generation",
  "ip": "192.168.1.150",
  "token": "abcdef1234567890abcdef1234567890",
  "pause": false,
  "dock": true,
  "waterBox": false
 },
 {
  "accessory": "XiaomiRoborockVacuum",
  "name": "Xiaomi Roborock S50 Vaccum 2nd Generation",
  "ip": "192.168.1.151",
  "token": "1234567890abcdef1234567890abcdef",
  "pause": false,
  "dock": true,
  "waterBox": false
 }
],
```

## Optional parameters
| Name of parameter | Default value | Notes |
|---|---|---|
| `pause` | false | when set to true, HomeKit shows an additional switch for "pause" - switch is on, when pause is possible |
| `dock` | false |  when set to true, HomeKit shows an occupancy sensor, if robot is in the charging dock |
| `waterBox` | false | when set to true, HomeKit shows an additional slider to control the amount of water released by the robot (only selected models like S5-Max). Currently in a beta state. |
| `cleanword` | cleaning | used for autonaming the Roomselectors |
| `rooms` | false | Array of ID / Name for a single Room. If set you have another switch for cleaning only this room |
| `autoroom` | false | when set to true, Rooms will be generated from Robot. (only S6) |

## AutoRoom Generation
This feature seems to be working only on the S6 Model.
We figured out this is why the Api call only delivers the mapping when the Rooms are named in the Xioami / Roborock App.

So when you have an S6 but not named the Rooms in your App this function will not work! Thanks @domeOo

## Xiaomi Token
To use this plugin, you have to read the "token" of the xiaomi vacuum robots. Here are some detailed instructions:
- :us::gb: - [python-miio - Getting started](https://python-miio.readthedocs.io/en/latest/discovery.html)
- :de: - [Apple HomeKit Forum - HomeKit.Community](https://forum.smartapfel.de/forum/thread/370-xiaomi-token-auslesen/)
- :de: - [Homematic-Guru.de](https://homematic-guru.de/xiaomi-vacuum-staubsauger-roboter-mit-homematic-steuern)
