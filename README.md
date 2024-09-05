# ESP32 LED Control Project

## Overview

This project involves controlling 8 WS2812 LED strips, each containing 300 LEDs, using an ESP32 TTGO board. The ESP32’s RMT (Remote Control) module is utilized to manage the LED strips efficiently. The project demonstrates the ability to handle high frame rates and large datasets with real-time LED control.

## Features

- **LED Control:** Manages 8 WS2812 LED strips with a total of 2400 LEDs.
- **High Frame Rate:** Supports up to 20 frames per second (50 ms per frame).
- **Dual-Core Processing:** Utilizes both cores of the ESP32 for parallel processing.
- **Data Handling:** Reads data from an SD card, decompresses it from zlib format, and processes it for LED control.
- **Circular Buffer Management:** Implements intricate circular buffer management for efficient LED data handling.
- **PSRAM Usage:** Enables PSRAM to handle large frame sizes and prevent memory overflow.

## Components

- **ESP32 TTGO Board**
- **WS2812 LED Strips (8 strips, 300 LEDs each)**
- **SD Card**

## Software

- **xLights:** Used to create LED sequences.
- **ESP-IDF:** The ESP32 development framework used for programming the board.

## Installation

1. **Setup Environment:**
   - Install ESP-IDF by following the [official guide](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/).
   - Install any necessary dependencies for ESP32 development.

2. **Prepare the SD Card:**
   - Format the SD card and copy the .fseq file generated by xLights to the SD card.

3. **Upload Code:**
   - Clone this repository to your local machine.
   - Open the project in your ESP-IDF environment.
   - Configure the project settings as needed.
   - Build and upload the code to the ESP32 board using the ESP-IDF tools.

## Usage

1. **Power the ESP32 Board:**
   - Connect the ESP32 TTGO board to a power source suitable for driving the LED strips.

2. **Run the Project:**
   - Once the code is uploaded, the ESP32 will begin reading the .fseq file from the SD card.
   - The data will be decompressed and processed in parallel tasks: one core for decompression and the other for driving the LEDs.

3. **Observe the LEDs:**
   - The LEDs will display the sequence as defined in the .fseq file, running at 20 frames per second.

## Code Structure

- **main.c:** Contains the main logic for initializing the ESP32, reading from the SD card, decompressing the data, and controlling the LEDs.
- **led_glow.c:** Handles the LED control and updates the LED strips.
- **extractor.c:** Manages data decompression and buffering.

## Acknowledgments

- **xLights:** For providing the sequence creation software.
- **ESP-IDF:** For the ESP32 development framework.
- **WS2812 LED Strips:** For the LED hardware used in the project.


## Development Status

This project is still under development.