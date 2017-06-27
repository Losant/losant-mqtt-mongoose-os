# Losant + Mongoose OS Example

This is an example Mongoose OS app that connects to Losant via MQTT. 

## Tested Hardware
- ESP8266
- ESP32

## Configuration

Mongoose OS has support for [run-time multi-layer configuration](https://mongoose-os.com/docs/overview/configuration.html). In this app, we provide `conf1.json`. 

You must replace the following values:

- LOSANT_CLIENT_ID
- LOSANT_ACCESS_KEY
- LOSANT_ACCESS_SECRET 
- WIFI_SSID
- WIFI_PASSWORD

You obtain the `LOSANT_CLIENT_ID`, `LOSANT_ACCESS_KEY`, and `LOSANT_ACCESS_SECRET` values from [Losant](www.losant.com). 

```
{
    "wifi": {
        "sta": {
            "enable": true,
            "ssid": "WIFI_SSID",
            "pass": "WIFI_PASSWORD"
        }
    },
    "device": {
        "id": "LOSANT_CLIENT_ID"
    },
    "debug": {
        "stdout_topic": "",
        "stderr_topic": ""
    },
    "mqtt": {
        "enable": true,
        "client_id": "LOSANT_CLIENT_ID",
        "user": "LOSANT_ACCESS_KEY",
        "pass": "LOSANT_ACCESS_SECRET",
        "ssl_ca_cert": "ca.pem"
    }
}
```

## Installation & Flashing

Before beginning, you must have the `mos` tool installed. For more info, see the mos [installation instructions](https://mongoose-os.com/docs/quickstart/setup.html). 

1. First, clone the losant app

```
$ git clone https://github.com/Losant/losant-mqtt-mongoose-os.git
```

2. **IMPORTANT** Update the configuration

3. Building the firmware: (esp8266 or esp32)

```
$ mos build --arch esp8266 
```

4. To flash the device: (esp8266 or esp32)

```
$ mos flash esp8266 
```

5. To stream logs to the terminal: 

```
$ mos console
```

6. To open up the Web UI:

```
$ mos
```