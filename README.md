# 🤖 ESP32 Line Following Robot using PID Control

An autonomous **ESP32-based Line Following Robot** that uses a **5-channel Infrared Sensor Array** and a **PID (Proportional-Integral-Derivative) Controller** for accurate real-time line tracking. The project is built using **Arduino IDE** and **FreeRTOS**, enabling multitasking for efficient sensor processing and motor control.

---

## 📌 Project Overview

This project demonstrates the implementation of a **closed-loop control system** for an autonomous line-following robot.

The robot continuously reads the position of a black line using a **5-IR sensor array**, calculates the tracking error, and applies a **PID controller** to adjust the speed of both motors independently. By utilizing **FreeRTOS**, sensor acquisition and motor control run as separate tasks, resulting in smoother and more responsive movement.

The system is capable of navigating:

- ✅ Straight paths
- ✅ Smooth curves
- ✅ Sharp turns
- ✅ High-speed line tracking

---

## ✨ Features

- 🚀 ESP32-based high-performance controller
- 📡 5-channel IR sensor array
- 🎯 Real-time PID control
- ⚡ FreeRTOS multitasking
- 🔄 Weighted average line position calculation
- 🔒 Locked-turn logic for sharp turns
- 🛞 Differential motor speed control
- 📈 Easily tunable PID parameters

---

## 🛠 Hardware Components

| Component | Description |
|-----------|-------------|
| ESP32 | Main Microcontroller |
| 5x IR Sensors | Line Detection |
| L298N | Dual H-Bridge Motor Driver |
| DC Motors | 4-Wheel Robot Chassis |
| 12V Battery | Power Supply |

---

## 💻 Software Stack

- Arduino IDE
- C++
- ESP32 Arduino Framework
- FreeRTOS

---

## ⚙️ Control Algorithm

The robot determines the position of the line using a weighted average of the five IR sensors.

### Error Calculation

```text
Error = Desired Position − Measured Position
```

### PID Control Law

```text
u(t) = Kp·e(t) + Ki∫e(t)dt + Kd(de(t)/dt)
```

where

- **Kp** → Proportional Gain
- **Ki** → Integral Gain
- **Kd** → Derivative Gain

The calculated correction value adjusts the left and right motor speeds independently to keep the robot centered on the line.

---

## 🎛 PID Parameters

| Parameter | Value |
|-----------|------:|
| Kp | 1.20 |
| Ki | 0.01 |
| Kd | 0.80 |

> These values were experimentally tuned for stable and responsive line tracking.

---

## 📂 Project Structure

```
Line-Following-Robot-ESP32/
│
├── src/
│   ├── main.cpp
│   ├── PID.cpp
│   ├── PID.h
│   ├── Sensors.cpp
│   ├── Sensors.h
│   ├── Motors.cpp
│   └── Motors.h
│
├── images/
│   ├── robot.jpg
│   └── circuit.png
│
├── docs/
│   └── report.pdf
│
├── README.md
└── LICENSE
```

*(Modify according to your repository structure.)*

---

## 🔄 System Workflow

```text
IR Sensors
      │
      ▼
Read Sensor Values
      │
      ▼
Calculate Line Position
      │
      ▼
Compute Error
      │
      ▼
PID Controller
      │
      ▼
Motor Speed Correction
      │
      ▼
Robot Movement
```

---

## 🧠 FreeRTOS Tasks

The application is divided into independent tasks:

| Task | Function |
|------|----------|
| Sensor Task | Reads IR sensor values |
| PID Task | Calculates PID correction |
| Motor Task | Updates motor PWM outputs |

This separation improves responsiveness and maintains consistent control timing.

---

## 📸 Project Images

### Robot

```
images/robot.jpg
```

### Circuit Diagram

```
images/circuit.png
```

*(Upload images inside the `images` folder and GitHub will display them.)*

Example:

```markdown
![Robot](images/robot.jpg)

![Circuit](images/circuit.png)
```

---

## 🚀 Getting Started

### Clone Repository

```bash
git clone https://github.com/MuhammadTalha988516/Line-Following-Robot-using-ESP32.git
```

### Open Project

Open the project in **Arduino IDE**.

### Install Required Libraries

- ESP32 Board Package
- FreeRTOS (included with ESP32)
- Arduino Core for ESP32

### Upload

1. Select your ESP32 board.
2. Connect via USB.
3. Upload the code.
4. Power the robot with a 12V battery.

---

## 📊 Future Improvements

- Bluetooth parameter tuning
- Wi-Fi telemetry dashboard
- OLED status display
- Auto PID tuning
- Maze solving
- Junction detection
- Encoder-based speed feedback

---

## 🤝 Contributing

Contributions are welcome!

If you have suggestions or improvements, feel free to open an issue.

---


## 👨‍💻 Author

**Muhammad Talha Ali Butt**

GitHub: https://github.com/MuhammadTalha988516

---

⭐ If you found this project useful, consider giving it a **Star** on GitHub!
