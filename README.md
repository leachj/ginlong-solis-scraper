# ginlong-solis-scraper

Dockerized version of [ginlong-scraper](https://github.com/dkruyt/ginlong-scraper)

Scrapes PV statistics from the Ginlong monitor pages and outputs it to influxdb, pvoutput or mqtt.

There is a possibility it also works with the following inverters: Omnik Solar, Solarman and Trannergy Inverters

## Configuration

### Environment variables

| Environment variable      | Required | Description                                                                                          | Default value   |
|---------------------------|----------|------------------------------------------------------------------------------------------------------|-----------------|
| LOG_LEVEL                 | No       | Logging level (ERROR, INFO, DEBUG)                                                                   | `INFO`          |
| GINLONG_USERNAME          | Yes      | Ginlong Solis username                                                                               | *empty*         |
| GINLONG_PASSWORD          | Yes      | Ginlong Solis password                                                                               | *empty*         |
| GINLONG_DOMAIN            | No       | Ginlong Solis domain                                                                                 | `m.ginlong.com` |
| GINLONG_LANG              | No       | Ginlong Solis language                                                                               | `2` *(English)* |
| GINLONG_DEVICE_ID         | No       | Ginlong Solis device ID<br/>(only required if auto-detect fails or if you have more than one device) | *empty*         |
| USE_INFLUX                | No       | Set to true if you want to use InfluxDB as output                                                    | `false`         |
| INFLUX_DATABASE           | No       | InfluxDB DB name                                                                                     | `influxdb`      |
| INFLUX_SERVER             | No       | InfluxDB server                                                                                      | `localhost`     |
| INFLUX_PORT               | No       | InfluxDB server port                                                                                 | `8086`          |
| INFLUX_MEASUREMENT        | No       | InfluxDB measurement type                                                                            | `PV`            |
| USE_PVOUTPUT              | No       | Set to true if you want to use PvOutput as output                                                    | `false`         |
| PVOUTPUT_API_KEY          | No       | PvOutput API key                                                                                     | *empty*         |
| PVOUTPUT_SYSTEM_ID        | No       | PvOutput system ID                                                                                   | *empty*         |
| USE_MQTT                  | No       | Set to true if you want to use MQTT as output                                                        | `false`         |
| MQTT_CLIENT_ID            | No       | MQTT client ID                                                                                       | `pv`            |
| MQTT_SERVER               | No       | MQTT server                                                                                          | `localhost`     |
| MQTT_USERNAME             | No       | MQTT username                                                                                        | *empty*         |
| MQTT_PASSWORD             | No       | MQTT password                                                                                        | *empty*         |

## Bonus

The grafana-dashboard-example.json file you could import in to Grafana if you use the influx database. Then you can make a dashboard similar to this.

![grafana](https://github.com/dkruyt/resources/raw/master/grafana-dashboard-ginlong-small.png)
