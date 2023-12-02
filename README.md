# Building a Handwritten Digit Classification System with Raspberry Pi Pico, OV7670 Camera, TFT LCD Display, and Machine Learning

In this project, I'll guide you through the process of creating a handwritten digit classification system using a Raspberry Pi Pico, an OV7670 camera module, a 128x160 TFT LCD display, and machine learning techniques. Please keep in mind that this code is highly experimental, and even after following all the recommended steps in this article, some tinkering may still be necessary to get it to work. So, let's dive in and start exploring!
## Project Overview

We intend to run a machine learning model on our Raspberry Pi Pico that analyzes photos received from a camera and tries to infer what digit was present in the image. An image of the project in action is shown below:

![Predicted value displayed on LCD](image_link_here)

It is important to note that our machine learning model can be executed entirely on a Raspberry Pi Pico; a connected computer or cloud are not required. Therefore, creating compact machine learning models that fit in Pi Pico’s RAM and are accurate enough for our work is a major challenge we are aiming to overcome. This is no easy task, and I will discuss this in more detail in a later part of this article.


### Required Hardware

- Raspberry Pi Pico: This project has only been tested on the Raspberry Pi Pico. Hopefully, it won’t require any code modifications to run on the Raspberry Pi Pico W. As the code is written in CircuitPython, it is expected to work on most boards that support CircuitPython. Almost 80% of the GPIOs on the Pi Pico are used by the project, so make sure you have enough GPIOs on your board. You will need to change the code for the project to work with any other boards.

- 128x160 TFT LCD: Similar to [this one](lcd_link_here). Other options might be workable but may call for code changes. Theoretically, an LCD might not even be necessary; data could be written to a serial console instead. But practically speaking, this project might be difficult to implement without an LCD. The placement of the camera and the subject has a significant impact on the output. With an LCD, it is easy to align your handwritten numbers with the camera as you can constantly see what your camera is seeing.

- OV7670 Camera Module: I purchased this for Rs. 155 (approx USD 2), can you believe it! Much cheaper than some color sensors!

- Full-sized breadboard (highly recommended)

- Jumper Cables: May 20 each of M-F and M-M. There are lots of connections to be made!
- 4.7k ohm resistor (2)

### Required Software

- Any text editor for editing the code if you plan to make any changes.
- A full Python distribution and pip for training and exporting the machine learning model.
- And of course, lots of patience.


We also want to show our results on an LCD screen. So, we use a 120x160 TFT LCD display to show the output to the user.

Lastly, everything needs to be done using CircuitPython. In my personal opinion, CircuitPython is easy and fun to work with. The biggest advantage is that your code will work with a variety of 300+ boards supporting CircuitPython.


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
