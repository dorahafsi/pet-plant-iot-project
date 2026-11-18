# pet-plant-iot-project
an iot project for smart devices course. measure a plant's needs and track them on a dashboard using esp32

# Smart Plant Pet

ESP32 device that monitors a plant (soil moisture, temperature,
humidity, light), shows its "mood", logs data, and sleeps to save power.

## Features
- Reads soil moisture, DHT22 and LDR
- Mood logic: happy / thirsty / hot / dark (and their opposites maybe)
- History and config stored in Flash (SPIFFS)
- Remote access: MQTT + config web page
- Deep sleep with timer wake
- Alexa voice command (via MQTT)

## Hardware
1*ESP32 DevKit
1*Capacitive soil moisture sensor
1*DHT22
1*(LDR + 10k resistor)
3*LEDs + 1*buzzer

## Wiring
soil sensor->34
ldr->35
dht22->4
leds green->25 yellow->26 red->27
buzzer->14
wake button->33

## How to run
**Wokwi:** open <this will be the link to the  wokwi circuit(idk if it works tho)>, press Start.
**Real board:**
1. Install Arduino IDE + ESP32 board package
2. Install libraries: DHT, PubSubClient, ESPAsyncWebServer
3. Copy `secrets.example.h` to `secrets.h` and fill in WiFi/MQTT
4. Upload the `data/` folder to SPIFFS, then upload the sketch

## How it works
1. Wake (timer) -> read sensors -> compute mood
2. Log to SPIFFS -> publish to MQTT -> deep sleep
3. Press the button to open the config web page for 2 minutes

## Project structure
`src/` code, `data/` SPIFFS files, `docs/` diagrams and report

## Team
none of your business (rt3-2 grp1)
