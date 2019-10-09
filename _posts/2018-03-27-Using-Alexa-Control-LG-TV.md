---
layout: post
title: "Using Alexa to Control LG TV"
categories:
  - Others
tags:
  - Alexa
  - LG
  - HomeBridge
---
install
[Homebridge](https://github.com/nfarina/homebridge)

install
[HomeBridge-Alexa](https://github.com/NorthernMan54/homebridge-alexa)

install
[HomeBridge-webos3](https://github.com/merdok/homebridge-webos3)

register
[https://homebridge.cloudwatch.net/](https://homebridge.cloudwatch.net/)

enable skill on Alexa App [HomeBridge](https://www.amazon.com/Northern-Man-54-Homebridge/dp/B07B9QMTFQ/ref=sr_1_1?s=digital-skills&ie=UTF8&qid=1522304390&sr=1-1&keywords=homebridge&dpID=61ZB%252BPB7UNL&preST=_SY300_QL70_&dpSrc=srch)

modify config.json

``` json
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

using iOS device HomeKit to add new device

using Alexa to discover new device

background exec
```
(exec homebridge -I &> /dev/null &)
```
