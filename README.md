# 🛩️ DIY RC Plane with Arduino UNO

## 📌 Project Overview
This project is a custom-built RC plane controlled via Arduino UNO microcontrollers for both transmitter and receiver. The system is designed for efficient remote flight and payload deployment using low-latency communication and modular hardware components.

---

## 🎯 Mission Objectives
- Deploy a 50g payload (golf ball) to a predefined target
- Maintain stable flight during takeoff, cruise, and payload drop
- Enable smooth control over all surfaces and components
- Include safety and recovery mechanisms in case of signal issues

---

## 🧰 Hardware Components

### 🔭 Transmitter
- Arduino UNO microcontroller
- 2x Dual-axis Joysticks
- 2x Push Buttons
- NRF24L01 Wireless Module
- 9V or 12V Power Supply

### ✈️ Receiver (on Plane)
- Arduino UNO microcontroller
- NRF24L01 Wireless Module
- Servo Motors:
  - Elevator
  - Rudder
  - Ailerons (or Left/Right Wings)
  - Payload Drop Servo
- 1000KV BLDC Motor + ESC
- 12V 2200mAh LiPo Battery
- 10-inch Propeller
- Lightweight Frame
- Golf Ball Payload Mechanism

---

## 🎮 Control Mapping

| Input        | Function                            |
|--------------|-------------------------------------|
| Left Joystick - Y | Throttle / Motor Speed Control     |
| Left Joystick - X | Rudder Control                    |
| Right Joystick - Y | Elevator (Pitch) Control           |
| Right Joystick - X | Ailerons / Wing Control           |
| Left Button    | Trigger Payload Drop Mechanism    |
| Right Button   | Enable Stabilized Mode (Optional) |

---

## 🧠 Special Features
- **Payload Drop Mechanism** triggered via button press
- **Failsafe Mode**: Return controls to neutral & stop motor on signal loss
- **Input Smoothing**: Avoids jitter & improves precision
- **Gradual Throttle Changes**: Enhances flight safety
- **Simple Calibration Routine** for ESC and Servos

---

## 📶 Communication Setup
- **Protocol**: NRF24L01 (2.4GHz)
- **Update Rate**: ~40–50 Hz
- **Packet Structure**: Lightweight, efficient
- **Range**: Up to 100 meters (line-of-sight)
- **Failsafe Trigger**: >1s signal loss

---

## 🛠️ Setup Instructions
1. Upload the `transmitter.ino` to your Arduino UNO (TX side)
2. Upload the `receiver.ino` to your Arduino UNO (RX side)
3. Power on both devices
4. Test all servos, throttle, and payload functions
5. Calibrate ESC (see below) before first flight

---

## 🧪 ESC Calibration Steps
1. Power off both Arduino + ESC
2. Move throttle joystick to maximum
3. Power on receiver — ESC will beep (max throttle detected)
4. Wait 2 seconds
5. Move throttle joystick to minimum — ESC will beep again
6. Calibration is complete!

---

## 📊 Control Ranges

| Control      | Min Angle | Neutral | Max Angle |
|--------------|-----------|---------|-----------|
| Elevator     | 80°       | 115°    | 150°      |
| Rudder       | 70°       | 105°    | 130°      |
| Left Wing    | 30°       | 70°     | 110°      |
| Right Wing   | 20°       | 68°     | 100°      |

---

## 📦 Payload Drop
- Triggered by pressing the **left button** on transmitter.
- A dedicated servo moves the mechanism to release the golf ball.
- Align and stabilize before triggering for best accuracy.

---

## ⚙️ Development Notes
- Input smoothing and deadzone filtering applied
- Motor and servo safety: No sudden jumps or glitches
- Serial Monitor logs available (transmitter side)
- Modular codebase for easy tuning and extension

---

## 🧯 Troubleshooting

| Issue                        | Solution                                                       |
|-----------------------------|----------------------------------------------------------------|
| No motor response           | Verify ESC calibration and motor connections                   |
| Servos not moving properly  | Recheck pin mappings and angle limits                          |
| Signal not received         | Ensure NRF24L01 modules are powered and wired correctly        |
| Inverted controls           | Swap joystick axis or reverse mapping in code                  |

---

## 🚀 Future Upgrades
- Battery voltage monitoring
- GPS & Return-to-Home functionality
- Autonomous payload drop via coordinates
- PID stabilization for smoother flight
- OLED screen for telemetry on transmitter

---

## 📁 Media

Check out **photos and a demo video** of our RC Plane in action:

🔗 [View Media Folder on Google Drive]((https://drive.google.com/drive/folders/1p52yfGMgNG2yOnZ-6FqaJbEAEQVLFnDp?usp=sharing))

---
