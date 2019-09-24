# homebridge-roborock

## Homebridge plugin for Xiaomi / Roborock Vacuum Cleaner's
With this [homebridge](https://github.com/nfarina/homebridge) plugin can you control the xiaomi vacuum robots as fan in your Apple Home App (HomeKit).

Thus plugin use the new [miio](https://github.com/aholstenson/miio) version 0.15.6 or newer, not like the old ones 0.14.1. Timeouts and API errors are a thing of the past!

## Features
* **Fan** as On-/Off-Switch. When switching off, directly back to the charging station.
* Fanspeed levels adjustable via 3D Touch / Force Touch.
  * Xiaomi Mi Robot 1st Generation (Roborock Vacuum V1), Roborock S6/T6 3nd Generation (Roborock Vacuum S6/T6) and Xiaowa Lite C10
    * Off (0%)
    * Quiet (1-38%)
    * Balanced (39-60%)
    * Turbo (61-77%)
    * Max Speed (78-100%)
  * Roborock S50 2nd Generation and S55 2nd Generation
    * Off (0%)
    * Mopping (1-15%)
    * Quiet (16-38%)
    * Balanced (39-60%)
    * Turbo (61-75%)
    * Max Speed (76-100%)
* Battery status and condition in the device details. Low battery alert.
* Pause switch (optional).
* Occupancy sensor (similar to motion sensor) for dock status (optional).

## Xiaomi Token
To use this plugin, you have to read the "token" of the xiaomi vacuum robots. Here are some detailed instructions:
- :us::gb: - [python-miio - Getting started](https://python-miio.readthedocs.io/en/latest/discovery.html)
- :de: - [Apple HomeKit Forum - HomeKit.Community](https://forum.smartapfel.de/forum/thread/370-xiaomi-token-auslesen/)
- :de: - [Homematic-Guru.de](https://homematic-guru.de/xiaomi-vacuum-staubsauger-roboter-mit-homematic-steuern)
