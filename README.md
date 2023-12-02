# Creating a Handwritten Digit Classification System with Raspberry Pi Pico

## Project Overview

In this project, we aim to develop a system that uses a Raspberry Pi Pico to run a machine learning model. This model will analyze images captured by an OV7670 camera module and predict the handwritten digit present in the image. The result will be displayed on a 128x160 TFT LCD screen. The entire process, from image capture to digit classification, will be self-contained on the Raspberry Pi Pico.

## Project Inspiration

This project drew inspiration from [Handwritten digit classification using Raspberry Pi Pico and Machine Learning](https://ashishware.com/2022/09/03/pipico_digit_classification/). While the core idea remains similar, several necessary changes and enhancements have been made to adapt it to our specific requirements and goals.

## Required Hardware

1. **Raspberry Pi Pico**: This project is designed for the Raspberry Pi Pico, but it may work on other boards that support CircuitPython with some modifications. Ensure your board has sufficient GPIO pins, as almost 80% of the Pi Pico's GPIOs are used.

2. **128x160 TFT LCD**: You'll need a compatible LCD display. Other displays may work with code adjustments, but an LCD is essential for practical alignment of handwritten digits with the camera's view.

3. **OV7670 Camera Module**: This camera module is used for capturing images. It's an affordable option for this project.

4. **Full-sized breadboard (highly recommended)**: A breadboard facilitates connections between components.

5. **Jumper Cables**: You'll need male-to-female (M-F) and male-to-male (M-M) jumper cables for making various connections.

6. **4.7k ohm resistor (2)**: These resistors are part of the project's electronic setup.

## Required Software

1. **Any text editor**: You'll need a text editor for editing the code if necessary.

2. **A full Python distribution and pip**: These are required for training and exporting the machine learning model.

3. **Patience**: Building and fine-tuning this system may require some patience.

The project aims to display the classification results on the 128x160 TFT LCD, making it a practical and interactive solution. It leverages CircuitPython for its versatility, ensuring compatibility with various boards supporting CircuitPython.

## Installation and Setup

1. **Install CircuitPython on Your Board**: Start by installing CircuitPython on your Raspberry Pi Pico board.

2. **Download Necessary Library Files**: Visit the CircuitPython website to download the necessary library files. Alternatively, you can obtain these files from the website and paste them into the "lib" folder on your board.

3. **Copy Code Files**: Copy and paste the following files into your board:
   - `code.py`
   - `svm_min.py`

## Running and Debugging

To run and debug your code, follow these steps:

1. Use an Integrated Development Environment (IDE), preferably Thonny IDE.

2. Ensure that your Raspberry Pi Pico is connected to your computer.

3. Refer to the connection details provided below for proper setup and debugging.

Please note that you'll need to configure your IDE to work with your Raspberry Pi Pico for effective code development and debugging.

## Wiring

For this project, a substantial amount of wiring is required. It is highly recommended to use breadboards and jumper cables for a clean and organized setup.

### LCD Connections

| Display Pin Number | Display Pin Name | Pi Pico Pins |
|-------------------|------------------|--------------|
| 2                 | VCC              | 5V           |
| 1                 | GND              | GND          |
| 10                | CS               | GP18         |
| 6                 | RESET            | GP17         |
| 7                 | A0               | GP16         |
| 8                 | SDA              | GP11         |
| 9                 | SCL              | GP10         |
| 15                | LED              | 3.3V         |

### OV7670 Module Connections

| OV7670 Pin Name | Pi Pico Pin Name                    |
|-----------------|------------------------------------|
| D0              | GP0                                |
| D1              | GP1                                |
| D2              | GP2                                |
| D3              | GP3                                |
| D4              | GP4                                |
| D5              | GP5                                |
| D6              | GP6                                |
| D7              | GP7                                |
| PCLK            | GP8                                |
| MCLK            | GP9                                |
| HS              | GP12                               |
| VS              | GP13                               |
| PDWN            | GP15                               |
| RESET           | GP14                               |
| SCL             | GP21 (via 4.7k external pull-up resistor) |
| SDA             | GP20 (via 4.7k external pull-up resistor) |
