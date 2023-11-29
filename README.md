# ESP32C3 BH1749NUC Color Sensor Calibration

![BH1749NUC Color Sensor](https://fscdn.rohm.com/en/products/databook/package/3d_image/ic/WSON008X2120.jpg)

## Overview

This repository contains code for calibrating the BH1749NUC RGB color sensor integrated into our custom ESP32C3-based PCB. The calibration process involves gathering min/max RGB values and generating dynamic RGB hex color codes.

## Quick Start

1. Connect your ESP32 programmer (e.g., FTDI programmer) to the designated programming headers on our custom PCB.
2. Clone or download this repository.
3. Upload the code to your PCB using your preferred development environment (e.g., Arduino IDE).
4. Disconnect the programmer.

## Calibration Process

1. Power on your custom PCB.
2. Open the serial monitor and follow the on-screen instructions to calibrate each color (RED, GREEN, BLUE).

## Configuration

Adjust the `minColorValues` and `maxColorValues` arrays based on your specific calibration needs. The default values are provided as a starting point.

```cpp
uint16_t minColorValues[NUM_COLORS] = { 500, 1700, 800 }; // custom
uint16_t maxColorValues[NUM_COLORS] = { 2750, 8000, 5000}; // custom

```


## Usage
- Press any key to sample a color and view the RGB values in the serial monitor.
- Use serial commands to set brightness (B), calibrate all colors (C), or manually set min/max values (M).

```cpp
B255   // Set brightness to 255 (0-255).
C      // Calibrate all colors.
M10 20 30   // Manually set new minColorValues (RED 10, GREEN 20, BLUE 30).
```

## License
This code is provided under the Beerware License. If you find it useful, buy the developer a beer if you ever meet them.

## Support
If you appreciate this work, consider supporting SparkFun Electronics by purchasing a board: SparkFun RGB Sensor - BH1749NUC