# ESP32-C3 Internet Clock

A Wi-Fi-enabled digital clock powered by an ESP32-C3 Super Mini and a 128×64 SSD1306 OLED display. The clock synchronizes time over the internet using NTP and displays the local time in Turkey (UTC+3).

## Features

- Browser-based firmware installation
- No Arduino IDE required for end users
- Wi-Fi configuration over USB serial
- Automatic time synchronization using NTP
- Automatic synchronization every 4 hours
- OLED clock display with date and weekday
- Reduced OLED brightness during nighttime hours
- Wi-Fi credentials stored locally on the ESP32-C3

## Hardware Requirements

- ESP32-C3 Super Mini
- 128×64 SSD1306 I²C OLED display
- USB data cable
- 2.4 GHz Wi-Fi network with internet access

**Supported configuration:** This firmware is designed for the ESP32-C3 Super Mini with an SSD1306 OLED at I²C address `0x3C`.

## OLED Wiring

| OLED Pin | ESP32-C3 Super Mini |
|---|---|
| VCC | 3.3V |
| GND | GND |
| SDA | GPIO 8 |
| SCL | GPIO 9 |

Check your board's pin labels before connecting the display.

## Installation

1. Open the [ESP32-C3 Internet Clock Installer](https://clock.rue-tr.site) in Google Chrome or Microsoft Edge on a computer.
2. Connect the ESP32-C3 Super Mini using a USB data cable.
3. Click **Install Firmware**.
4. Select the ESP32-C3 serial port.
5. Confirm the installation and wait until flashing is complete.
6. Enter your Wi-Fi network name (SSID) and password.
7. Click **Configure Wi-Fi** and select the device's serial port if prompted.
8. Wait for the message **Time synchronized successfully! Your clock is ready.**

The first synchronization requires a working Wi-Fi connection and internet access.

## Privacy

Wi-Fi credentials are sent from the browser to the ESP32-C3 over USB serial. The installer page does not intentionally upload these credentials to a web server. The ESP32-C3 stores the credentials locally so it can reconnect after restarting.

Use the installer only if you trust the firmware and source code.

## Troubleshooting

### The Install Firmware button is missing

- Open the installer over HTTPS.
- Use a supported desktop browser such as Chrome or Edge.
- Make sure the page has finished loading.

### The ESP32-C3 serial port is not listed

- Use a USB data cable, not a charge-only cable.
- Try another USB port.
- Close other applications that may be using the serial port.

### Wi-Fi configuration fails

- Check the SSID and password.
- Use a 2.4 GHz Wi-Fi network.
- Keep the USB connection connected while configuration is running.
- Ensure the network has internet access for NTP synchronization.

### The OLED remains blank

- Check the 3.3V and GND connections.
- Verify SDA is connected to GPIO 8 and SCL to GPIO 9.
- Confirm the display uses I²C address `0x3C`.

## Time Configuration

The firmware uses the `TRT-3` time zone (UTC+3) and synchronizes with NTP servers. A working internet connection is required for initial synchronization and periodic updates.

## Source Code

Browse the project source and firmware files in this repository:

https://github.com/rugur78tr/esp32c3-internet-clock

## License

Add a license file before redistributing the project or its firmware.
