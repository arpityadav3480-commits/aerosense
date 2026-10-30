# AeroSense IoT – Cloud Dashboard

Live air quality dashboard for the AeroSense IoT monitor (ESP32 + BME680 + PMS7003).

**Live site:** https://arpityadav3480-commits.github.io/aerosense/

The ESP32 uploads a reading to ThingSpeak every ~20 seconds. This page reads that
data through the ThingSpeak API, so it works from any network with no server of its own.

## Public API

Base URL: `https://api.thingspeak.com`

| Request | Returns |
|---|---|
| `GET /channels/3462136/feeds/last.json` | Latest reading |
| `GET /channels/3462136/feeds.json?results=50` | Last N readings (max 8000) |
| `GET /channels/3462136/fields/5.json?results=100` | One field only |
| `GET /channels/3462136/feeds.csv?results=8000` | Readings as CSV |

| Key | Meaning | Unit |
|---|---|---|
| field1 | Temperature | °C |
| field2 | Humidity | % |
| field3 | Pressure | hPa |
| field4 | Gas resistance | kΩ |
| field5 | IAQ (estimated) | 0–500 |
| field6 | CO2 equivalent | ppm |
| field7 | PM2.5 | µg/m³ |
| field8 | PM10 | µg/m³ |
