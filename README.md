# Building a Handwritten Digit Classification System with Raspberry Pi Pico, OV7670 Camera, TFT LCD Display, and Machine Learning

In this project, I'll guide you through the process of creating a handwritten digit classification system using a Raspberry Pi Pico, an OV7670 camera module, a 128x160 TFT LCD display, and machine learning techniques. Please keep in mind that this code is highly experimental, and even after following all the recommended steps in this article, some tinkering may still be necessary to get it to work. So, let's dive in and start exploring!
## Project Overview

We intend to run a machine learning model on our Raspberry Pi Pico that analyzes photos received from a camera and tries to infer what digit was present in the image. An image of the project in action is shown below:

![Predicted value displayed on LCD](image_link_here)

It is important to note that our machine learning model can be executed entirely on a Raspberry Pi Pico; a connected computer or cloud are not required. Therefore, creating compact machine learning models that fit in Pi Pico’s RAM and are accurate enough for our work is a major challenge we are aiming to overcome. This is no easy task, and I will discuss this in more detail in a later part of this article.

We also want to show our results on an LCD screen. So, we use a 120x160 TFT LCD display to show the output to the user.

Lastly, everything needs to be done using CircuitPython. In my personal opinion, CircuitPython is easy and fun to work with. The biggest advantage is that your code will work with a variety of 300+ boards supporting CircuitPython.
