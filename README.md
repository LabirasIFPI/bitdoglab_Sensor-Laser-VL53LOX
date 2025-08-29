# VL53L0X Laser Distance Sensor with Raspberry Pi Pico

This repository contains a C example for using the VL53L0X Time-of-Flight (ToF) laser distance sensor with the Raspberry Pi Pico board.

## 📋 Table of Contents

- [Features](#-features)
- [Hardware Required](#-hardware-required)
- [Software and Dependencies](#-software-and-dependencies)
- [Connections](#-connections)
- [How to Compile and Run](#-how-to-compile-and-run)
  - [Using VS Code with the Raspberry Pi Pico Extension (Recommended)](#using-vs-code-with-the-raspberry-pi-pico-extension-recommended)
  - [Using the Command Line](#using-the-command-line)
- [Project Structure](#-project-structure)
- [Author](#-author)
- [License](#-license)

## ✨ Features

-   Integration with the VL53L0X laser distance sensor.
-   Continuous distance reading in millimeters.
-   Communication via I2C with the Raspberry Pi Pico.
-   Sensor model and revision check to ensure a correct connection.
-   Project configured for easy compilation with the Raspberry Pi Pico SDK and CMake.

## 🛠️ Hardware Required

-   **Raspberry Pi Pico** or **Pico W**
-   **VL53L0X Laser Distance Sensor**
-   **Jumper Wires** for connection

## 📦 Software and Dependencies

-   **Visual Studio Code**
-   **Raspberry Pi Pico/W Extension for VS Code**
-   **Raspberry Pi Pico SDK**, **ARM GCC Compiler**, and **CMake**

## 🔌 Connections

Connect the VL53L0X sensor to the Raspberry Pi Pico using the I2C0 interface, as defined in the `src/sensor-distancia-laser.c` file:

| VL53L0X Pin | Raspberry Pi Pico Pin | Description |
| :---------- | :-------------------- | :---------- |
| **VIN** | **3.3V (OUT)** | Power       |
| **GND** | **GND** | Ground      |
| **SCL** | **GP1 (I2C0 SCL)** | I2C Clock   |
| **SDA** | **GP0 (I2C0 SDA)** | I2C Data    |

## 🚀 How to Compile and Run

### Using VS Code with the Raspberry Pi Pico Extension (Recommended)

This project is already configured for the official extension, making the process very simple.

1.  **Open Project:** Open the project's root folder in Visual Studio Code.
2.  **Prepare the Board:** Put the Raspberry Pi Pico into **BOOTSEL** mode (press and hold the BOOTSEL button while connecting the USB cable).
3.  **Upload the Code:** Click the **`Run`** button on the status bar. The extension will compile the code and automatically upload it to the board using `picotool`.
4.  **View the Output:** Open the integrated serial monitor in VS Code to see the distance measurements.

### Using the Command Line

If you prefer not to use VS Code, you can compile manually.

1.  **Clone the repository:**
    ```bash
    git clone <YOUR_REPOSITORY_URL>
    cd <FOLDER_NAME>
    ```
2.  **Create and configure the build:**
    * Make sure the `PICO_SDK_PATH` environment variable points to your SDK directory.
    ```bash
    mkdir build
    cd build
    cmake ..
    ```
3.  **Compile:**
    ```bash
    make
    ```
4.  **Upload the firmware (`.uf2`):**
    -   Put the Pico in **BOOTSEL** mode.
    -   Copy the `build/sensor-distancia-laser.uf2` file to the drive that the Pico mounted on your system.

## 📂 Project Structure
