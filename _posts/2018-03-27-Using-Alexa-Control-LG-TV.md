---
layout: post
title: "Using Alexa to Control LG TV"
categories:
  - Alexa
tags:
  - Alexa
  - LG
  - HomeBridge
---
## Using Alexa to Control LG TV
install
[Homebridge](https://github.com/nfarina/homebridge)

install
[HomeBridge-Alexa](https://github.com/NorthernMan54/homebridge-alexa)

install
[HomeBridge-webos3](https://github.com/merdok/homebridge-webos3)

register
[https://homebridge.cloudwatch.net/](https://homebridge.cloudwatch.net/)

enable skill Alexa homebridge

config.json

``` JSON
{
    "bridge": {
        "name": "Homebridge",
        "username": "CC:22:3D:E3:CE:30",
        "port": 51826,
        "pin": "031-45-154",
        "ssdp": 1900
    },

    "description": "test",

     "accessories": [
      {
      "accessory": "webos3",
      "name": "My webOS tv",
      "ip": "192.168.1.105",
      "mac": "12:34:56:78:90:AB",
      "keyFile": "Auth key File",
      "pollingEnabled": true,
      "appSwitch":[
         "youtube.leanback.v4",
         "com.webos.app.hdmi2",
         "netflix"
      ]

      }
    ],

    "platforms": [
        {
            "platform": "Alexa",
            "name": "Alexa",
            "username": "username registered on cloudwatch",
            "password": "password registered on cloudwatch"
        }
    ]
}
```

background exec
```
(exec homebridge -I &> /dev/null &)
```
