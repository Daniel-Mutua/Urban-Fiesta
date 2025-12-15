[README.md](https://github.com/user-attachments/files/24168450/README.md)
# Arduino Motor Control with AFMotor Library

## Overview
This project demonstrates a simple Arduino motor control system using the **Adafruit Motor Shield (AFMotor library)** and a **single digital sensor** connected to pin **A0**.

The system reads input from a left sensor:
- If the sensor detects a signal (HIGH), all four DC motors move **forward**.
- If the sensor detects no signal (LOW), all motors **stop**.

This setup is commonly used in **line-following robots**, **obstacle detection**, or **basic robotic motion control**.

---

## Hardware Requirements
- Arduino Uno / Mega
- Adafruit Motor Shield (v1)
- 4 DC Motors
- Digital Sensor (IR / line sensor / switch)
- Jumper wires
- External motor power supply (recommended)

---

## Software Requirements
- Arduino IDE
- AFMotor library  
  Install from:
  **Arduino IDE → Sketch → Include Library → Manage Libraries → Search “AFMotor”**

---

## Pin Configuration
| Component | Arduino Pin |
|---------|-------------|
| Left Sensor | A0 |
| Motor 1 | M1 |
| Motor 2 | M2 |
| Motor 3 | M3 |
| Motor 4 | M4 |

---

## Code Explanation
### Sensor Reading
```cpp
int leftSensor = digitalRead(left);
```
- Reads the sensor value from pin A0.
- HIGH (1) means detected.
- LOW (0) means not detected.

---

### Motor Movement Logic
#### When Sensor is HIGH
- All motors move forward at speed **150**.

#### When Sensor is LOW
- All motors stop using `RELEASE`.

---

## Motor Speed
```cpp
motor.setSpeed(150);
```
- Speed range: **0 – 255**
- Adjust for slower or faster movement.

---

## Applications
- Line-following robot
- Simple autonomous robot
- Sensor-triggered motion system
- Educational robotics projects

---

## Notes
- Use an **external power supply** for motors to avoid Arduino resets.
- Ensure proper grounding between Arduino and motor power source.
- Sensor pin A0 is used as a **digital input**.

---

## License
This project is open-source and free to use for educational and personal projects.
