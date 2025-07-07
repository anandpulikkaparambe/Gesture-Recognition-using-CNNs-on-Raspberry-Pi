# Gesture-Recognition-using-CNNs-on-Raspberry-Pi

1 Introduction

This lab focused on creating a real-time hand gesture recognition system using Convolutional Neural Networks (CNNs) implemented on a Raspberry Pi. The primary objective
was to accurately classify simple hand gestures, such as ’thumbs up’, by processing image
data captured through the Pi Camera. A CNN model was trained on gesture images and
deployed to the Raspberry Pi, enabling real-time inference. Upon detecting a recognized
gesture, the system triggered an action—such as turning on or off an LED—via the Sense
HAT, demonstrating practical control based on visual input. This lab effectively combines computer vision, deep learning, and embedded systems to illustrate how AI can be
applied in edge computing environments. It also highlights the potential for gesture-based
interfaces in low-power, portable hardware setups.

2 Methodology

The system employs a CNN binary classifier trained to differentiate between two hand
gestures: ’thumbs up’ and ’no thumbs up.’ Training data was collected using the Raspberry Pi, Pi Camera module, capturing various gesture images for model development.
This data was then used to train a CNN model through transfer learning in Google Colab,
using the VGG 16 architecture, a 16-layer deep convolutional neural network known for
its effectiveness in image classification tasks.
After training, the model was converted to TensorFlow Lite format for efficient deployment on the Raspberry Pi. The Pi then used its camera to capture real-time video input,
processing each frame to detect gestures. Based on the classification result, the system
controlled the LED indicators on the Sense HAT: a green LED was activated when a
"thumbs up" was detected, and a red LED lit up for any other gesture. This implementation highlights the power of edge AI for real-time visual recognition and control of
embedded systems.

2.1 Software and Hardware Used

• Programming language: Python

• Libraries: TensorFlow, Keras, Picamera2, Numpy, PIL, Sense-HAT

• Hardware: Raspberry Pi 4, Raspberry Pi Camera, Sensor HAT,Main PC, WiFiRouter

• Software: Google Colab

2.2 Code Repository

The full source code for this project is available on GitHub at:

This repository includes:

• Source code files

• Installation instructions

• Example datasets (if applicable)

• Documentation and usage guidelines
