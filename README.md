#  PID-Based Voltage Regulator using Arduino

## Overview

This project implements a **closed-loop voltage regulation system** using a PID (Proportional–Integral–Derivative) controller. The system maintains a stable output voltage (~5V) from a 12V DC input by dynamically adjusting PWM through a MOSFET.

Unlike simple regulators, this system continuously monitors the output and corrects deviations in real time.

---

##  Key Concept

The controller works based on error correction:

Error = Vset − Vout

* **Proportional (P):** reacts to present error
* **Integral (I):** removes steady-state error
* **Derivative (D):** reduces overshoot and stabilizes

---

##  Components Used

* Arduino Uno
* IRFZ44N MOSFET
* 10Ω (10W) Load Resistor
* Resistors: 10kΩ, 4.7kΩ, 220Ω
* Capacitor (100µF)
* 12V DC Power Supply
* Breadboard & Jumper Wires

---

##  Circuit Diagram

![Circuit Diagram](circuit_diagram.png)

---

##  Working Principle

1. Output voltage is taken from the MOSFET drain (Vout)
2. A voltage divider scales it down for Arduino input
3. Arduino reads voltage using analog pin (A0)
4. PID algorithm calculates correction
5. PWM signal is updated accordingly
6. MOSFET adjusts voltage across load
7. System stabilizes near the setpoint

---

## 💻 Code

The Arduino PID implementation is available in the `/code` folder.

---

## Results

* Output stabilizes around **5V**
* System automatically corrects disturbances
* Stability improves significantly with capacitor filtering

---

##  Challenges Faced

* Incorrect voltage divider connection
* PWM causing noisy voltage readings
* Unexpected readings (~15V) due to sampling peaks
* PID instability due to improper tuning
* Need for base PWM (feedforward control)

---

## 🧠 Key Learnings

* Importance of **closed-loop control systems**
* Real-world difference between theory and implementation
* Noise handling in measurement systems
* PID tuning in practical systems
* Role of filtering (capacitors) in power electronics

---

## 🚀 Future Improvements

* Add LC filter for better smoothing
* Convert into a buck converter
* Implement advanced PID tuning methods
* Add display (LCD/OLED) for real-time monitoring
---

## 👨‍💻 Author

Borish Dowerah 
(Electrical Engineering)
