# RemoteXY Motor Control Project

This project controls two motors using a joystick interface provided by the RemoteXY library. The code is designed to work with Arduino, using software serial communication to connect the microcontroller with a RemoteXY app interface on a mobile device.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Circuit Diagram](#circuit-diagram)
- [Installation and Setup](#installation-and-setup)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [License](#license)

## Overview

The project uses the RemoteXY library to create a simple joystick interface for controlling two DC motors. The joystick input is used to control the speed and direction of the motors, enabling forward, backward, left, and right movement.

## Features

- Joystick control of two motors via the RemoteXY mobile interface.
- Adjustable speed and direction of motors.
- Real-time feedback on connection status.

## Hardware Requirements

- Arduino board (e.g., Uno, Nano)
- Two DC motors with H-Bridge motor drivers.
- Bluetooth module for wireless communication.
- Jumper wires.
- Power supply for the motors.

## Software Requirements

- [Arduino IDE](https://www.arduino.cc/en/software)
- [RemoteXY Library](https://remotexy.com/en/library/) installed in Arduino IDE.

## Circuit Diagram

The motors are connected to the defined pins of the Arduino, and the Bluetooth module is connected to the RX and TX pins specified in the code.

## Installation and Setup

1. Connect your hardware as per the circuit diagram.
2. Download and install the RemoteXY library in the Arduino IDE.
3. Upload the code to your Arduino board.

## Usage

1. Open the RemoteXY app on your mobile device.
2. Connect to the Arduino via Bluetooth.
3. Use the joystick on the app to control the motors.

## Code Explanation

### RemoteXY Configuration

- The `RemoteXY` library is configured to use software serial for communication with the Bluetooth module.
- `joystick_1_x` and `joystick_1_y` are used to read joystick inputs from the app, ranging from -100 to 100.

### Motor Control

- Motor control pins are defined, and each motor's direction and speed are controlled using the `Wheel()` function.
- The speed is adjusted by scaling the joystick input to a PWM value.

### Functions

- `Wheel(uint8_t *motor, int v)`: Adjusts the direction and speed of a motor based on joystick input.
- `setup()`: Initializes RemoteXY and motor pins.
- `loop()`: Continuously reads joystick inputs and updates motor speed and direction accordingly.

## License

This project is open-source and available under the MIT License.
