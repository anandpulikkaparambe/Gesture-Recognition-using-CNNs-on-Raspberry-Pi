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

3 Results

After training the convolutional neural network (CNN) using transfer learning with the
VGG16 architecture, the model achieved a strong classification accuracy on the test
dataset. The trained model was successfully deployed on the Raspberry Pi, enabling
real-time gesture recognition.
During testing, the system correctly identified the gesture ’thumbs up’, which activated
the green LED indicator. Other recognized gestures activated the red LED, providing
immediate visual feedback. This real-time response demonstrated the effective integration
of the deep learning model with embedded hardware components.
In general, the results validate the system’s capability to perform accurate gesture classification and control hardware outputs efficiently under real-world conditions.

4 Challenges, Limitations, and Error Analysis

During the implementation of this project, several challenges and errors were encountered.
Below are some key points:

4.1 Challenges Faced

• File and Path Management: Ensuring the script files such as predict.py and
model files were correctly located and accessible on the Raspberry Pi, avoiding
confusion between directories like /build and /home/pi.

• Dependency Installation: Installing TensorFlow, Pillow, and other Python packages proved difficult due to hardware constraints of the Pi and missing system libraries (e.g., libcap-dev for python-prctl).

• Hardware Configuration: Enabling and verifying the camera module faced issues
such as unregistered commands and hardware detection failures, requiring firmware
updates and careful hardware checks.

• Custom Library Dependencies: Integrating the Sense HAT was complicated by
the need for RTIMULib, which often failed to build or install, leading to fallback
implementations in the code.

4.2 limitations affected the overall process and results:

• Hardware Constraints: The Raspberry Pi’s limited computing resources restricted the ability to install full TensorFlow, necessitating alternatives like tflite-runtime.

• Dependency Compatibility: Some packages required specific versions or system libraries that were not readily available or compatible with the Pi’s OS version.

• Incomplete Hardware Support: Despite software configuration, hardware components such as the camera or Sense HAT sometimes failed to respond due to connection issues or firmware mismatches.

• Script Execution Environment: Running scripts from incorrect directories caused runtime errors, highlighting the need for careful environment setup.

4.3 Error Analysis

The errors encountered were analyzed to identify root causes and potential mitigations:

• ModuleNotFoundError: Frequently due to missing Python packages like TensorFlow or Pillow. Mitigated by creating isolated virtual environments and explicitly installing packages.

• Build Failures: For RTIMULib, errors arose from incorrect directory navigation or missing dependencies, addressed by precise cloning and build commands.

• Camera Detection Failures: Indicated by commands like vcgencmd get_camera returning errors. Resolved by re-enabling camera interfaces, rebooting, and updating firmware.

• Permission Warnings: Using sudo pip caused installation warnings and sometimes conflicts. Avoided by relying on user-level virtual environments.

5 Discussion

This project demonstrated the feasibility of deploying a deep learning model on embedded hardware by implementing a full pipeline from data collection to real-time inference. The use of transfer learning proved to be a practical approach to overcome the challenge of limited dataset size, significantly reducing training time and computational requirements. The results highlight the critical role of data preprocessing in ensuring model accuracy and stability during inference. Additionally, the seamless integration between hardware components (such as the Raspberry Pi, camera module, and Sense HAT) and software frameworks (TensorFlow Lite, Python libraries) was essential for achieving real-time performance. Despite these successes, challenges such as hardware limitations, dependency conflicts, and configuration issues reveal areas for improvement. Future work could focus on optimizing model efficiency further, exploring more robust hardware platforms, and automating setup processes to enhance reproducibility. Overall, this project contributes valuable insights into deploying AI models on resourceconstrained devices, which is increasingly relevant in robotics and IoT applications.

6 Conclusion

This project successfully established a pipeline for deploying a deep learning model on embedded hardware, demonstrating real-time gesture recognition capabilities. By leveraging transfer learning and effective preprocessing, the need for large datasets was minimized, enabling efficient model training and deployment on resource-constrained devices. The integration of hardware and software components proved critical to the system’s overall performance. While challenges related to dependencies and hardware configuration were encountered, the solutions implemented provided a stable and functional system. These findings highlight the potential of embedded AI applications in robotics and pave the way for further enhancements in model optimization and system integration.

7 References

• Course Material: Prof. Tobias Schaffer, TH Deggendorf, Campus Cham


