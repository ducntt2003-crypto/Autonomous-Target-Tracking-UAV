# Autonomous-Target-Tracking-UAV
Autonomous UAV for Real-time Surveillance and Target Tracking

This project implements an autonomous Quadcopter system capable of real-time target tracking and obstacle avoidance. The system utilizes a Master-Slave architecture, where an NVIDIA Jetson Nano handles high-level vision processing and a Pixhawk 4 flight controller manages flight stability.
Key Features

    Target Detection: Utilizes the MobileNet-SSD v2 Deep Learning model optimized with CUDA for high-speed human detection.

    Autonomous Tracking: Implements a Centroid Tracking algorithm to keep the target centered in the frame while maintaining a consistent safety distance.

    Obstacle Avoidance: Real-time depth map analysis using the Intel RealSense D455 camera to detect and navigate around obstacles in complex environments.

    Multi-axis PID Control: Three independent PID controllers for vertical velocity, horizontal velocity, and yaw rate to ensure smooth and precise movement.

    MAVLink Integration: Seamless communication between the Jetson Nano (Master) and Pixhawk (Slave) via the MAVLink protocol and DroneKit library.

Hardware Stack

    Flight Controller: Pixhawk 4

    Companion Computer: NVIDIA Jetson Nano Developer Kit

    Vision Sensor: Intel RealSense D455

    Telemetry: Micoair LR900-P LoRa Telemetry

    Frame: F450 Quadcopter

Software & Technologies

    Language: Python

    Computer Vision: OpenCV, PyRealsense2

    Flight Control: DroneKit, MAVLink, ArduPilot/PX4

    Inference: TensorFlow/TensorRT (MobileNet-SSD v2)

    Utilities: NumPy, Matplotlib (for data logging and analysis)

System Architecture

The system processes depth and RGB data from the RealSense camera. The Jetson Nano identifies the target's coordinates and calculates the required velocity vectors using PID loops. These commands are then sent to the Pixhawk flight controller to adjust the drone's position in real-time.
