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

1. Set the LEDs brighness via Serial monitor.
    ```cpp
    B255   // Set brightness to 255 (0-255).
    ```
2. Calibrate the sensor's RGB values realtime using Serial monitor.
    ```cpp
    C     // Calibrate all colors.
    ```
3. Set the RGB calibration min/max values directly without calibration using Serial monitor.
    ```cpp
    M     // Manually set new minColorValues & maxColorValues.
    ```
    After sending the **M**, you will see this ouput in Serial monitor.
    ```c
    Enter new minColorValues (e.g., 'M 10 20 30'):
    ``` 
    Now send the new values via serial monitor as shown below:
   1. Send the minColorValues(RED 10, GREEN 20, BLUE 30) first,
        ```cpp
        Min 10 20 30
        ```
   2. Send the maxColorValues(RED 100, GREEN 200, BLUE 300).
        ```cpp
        Max 100 200 300
        ```

## License
This code is provided under the Beerware License. If you find it useful, buy the developer a beer if you ever meet them.

## Support
If you appreciate this work, consider supporting SparkFun Electronics by purchasing a board: SparkFun RGB Sensor - BH1749NUC