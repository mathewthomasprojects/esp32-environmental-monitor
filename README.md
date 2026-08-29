# ESP32 Environmental Monitoring and Fault Detection System

An embedded-system simulation that uses an ESP32 and DHT22
sensor to monitor temperature and humidity. The system
activates a warning LED when an environmental measurement
exceeds its configured safety threshold.

## Demonstration

### Normal Operation

The LED remains off when temperature and humidity are within
their configured limits.

![Normal operation](images/normal-operation.png)

### Alert Condition

The warning LED activates when temperature reaches 30°C or
humidity reaches 70%.

![Alert demonstration](images/alert-demo.png)

## Live Simulation

[Run the project in Wokwi](PASTE_WOKWI_LINK_HERE)

## Features

- Reads temperature and humidity using a DHT22 sensor
- Samples environmental measurements every two seconds
- Streams telemetry through the ESP32 serial monitor
- Detects unsafe temperature and humidity conditions
- Activates a visual LED fault indicator
- Separates sensor input and warning-output logic

## Hardware

- ESP32 development board
- DHT22 temperature and humidity sensor
- Red LED
- 220-ohm resistor

## Pin Configuration

| Component | ESP32 connection |
|---|---|
| DHT22 VCC | 3V3 |
| DHT22 SDA | GPIO 15 |
| DHT22 GND | GND |
| Warning LED | GPIO 5 through 220-ohm resistor |

## Alert Thresholds

| Measurement | Alert threshold |
|---|---:|
| Temperature | 30°C or higher |
| Humidity | 70% or higher |

## Test Results

| Test case | Temperature | Humidity | Expected result |
|---|---:|---:|---|
| Normal operation | 24°C | 40% | LED off |
| High temperature | 35°C | 40% | LED on |
| High humidity | 24°C | 80% | LED on |

All three operating conditions were tested using Wokwi's
interactive DHT22 simulation controls.

## Project Files

- `esp32_environmental_monitor.ino` — ESP32 firmware
- `diagram.json` — Wokwi circuit configuration
- `libraries.txt` — required Arduino library
- `images/` — testing and demonstration screenshots

## Skills Demonstrated

- Embedded C++ programming
- Microcontroller GPIO configuration
- Digital sensor integration
- Threshold-based control logic
- Serial telemetry
- Circuit simulation
- System testing and documentation

## Future Improvements

- Add configurable upper and lower safety thresholds
- Display measurements on an OLED screen
- Send telemetry over Wi-Fi
- Store historical sensor readings
- Add audible warning and multiple operating states
