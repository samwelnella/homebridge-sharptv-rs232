homebridge-sharptv-rs232
=
Introduction
-
This is a Homebridge plugin to control your Sharp TV via the rs232 port. This plugin can turn the TV on/off, change between HDMI inputs 1-5, and toggle game mode. This plugin has only been tested with a Sharp LC-70UH30U. Game mode toggles between "game" and "movie THX" picture modes, which is only supported by a few Sharp TV models. Change the "AVMD17" command in the code to your desired picture mode if you want game mode to work with Sharp TVs that don't support "movie THX" mode.

Example Configuration
-

'''json
{
    "bridge": {
        "name": "Homebridge",
        "username": "XX:XX:XX:XX:XX:XX",
        "port": 51826,
        "pin": "YYY-YY-YYY"
    },

    "description": "This is an example configuration file for homebridge-sharptv-rs232",

    "accessories": [
        {
            "accessory": "SharpTVRS232",
            "name": "Sharp TV",
            "path": "/dev/ttyUSB0",
            "timeout": 1000
        }
    ],

    "platforms": [
    ]
}
'''

Accessory Configuration Keys
-
| key             | description                                                                  | example        | default               |
|-----------------|------------------------------------------------------------------------------|----------------|-----------------------|
| name            | A descriptor for the accessory that will show in HomeKit apps.               | "TV"           | "Sharp TV"            |
| manufacturer    | A descriptor for the accessory manufacturer that will show in HomeKit apps.  | "Sharp"        | "Sharp"               |
| model           | A descriptor for the accessory model that will show in HomeKit apps.         | "LC-70UH30U"   | "Model not available" |
| serial          | A descriptor for the accessory serial number that will show in HomeKit apps. | "99327435"     | "Non-defined serial"  |
| path (required) | The path for your serial port.                                               | "/dev/ttyUSB0" |                       |
| timeout         | Amount of time to wait in between commands.                                  | 1000           | 1000                  |