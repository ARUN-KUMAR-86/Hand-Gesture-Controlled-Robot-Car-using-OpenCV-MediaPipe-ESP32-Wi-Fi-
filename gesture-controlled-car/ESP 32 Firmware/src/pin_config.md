# ESP32 Pin Configuration – Gesture Controlled Car

This document describes the GPIO pin assignments used in the ESP32
for controlling the motor driver via UDP commands.

---

## Microcontroller
- Board: ESP32 Dev Module
- Operating Voltage: 3.3V logic
- Communication: Wi-Fi (UDP)

---

## Motor Driver
- Supported: L298N / L293D
- Control Method: Direction control via GPIO
- Speed Control: Not implemented (can be extended using PWM)

---

## GPIO Pin Mapping

| Motor Side | ESP32 GPIO | Motor Driver Pin | Function                  |
|------------|------------|------------------|---------------------------|
| Left Motor | GPIO 18    | IN1              | Left motor direction 1    |
| Left Motor | GPIO 19    | IN2              | Left motor direction 2    |
| Right Motor| GPIO 21    | IN3              | Right motor direction 1   |
| Right Motor| GPIO 22    | IN4              | Right motor direction 2   |

---

## Direction Logic Table

| Command   | L1 (18) | L2 (19) | R1 (21) | R2 (22) |
|-----------|---------|---------|---------|---------|
| FORWARD   | HIGH    | LOW     | HIGH    | LOW     |
| BACKWARD  | LOW     | HIGH    | LOW     | HIGH    |
| LEFT      | LOW     | HIGH    | HIGH    | LOW     |
| RIGHT     | HIGH    | LOW     | LOW     | HIGH    |
| STOP      | LOW     | LOW     | LOW     | LOW     |

---

## Power Connections (Important)

- ESP32 VIN / 5V  → Motor Driver 5V (if supported)
- ESP32 GND       → Motor Driver GND
- External Motor Supply (7–12V) → Motor Driver Motor Power
- **All grounds must be common**

---

## Notes & Best Practices

- Do NOT power motors directly from ESP32 3.3V
- Always use a motor driver IC
- Add a heat sink to L298N if motors draw high current
- For speed control, use ESP32 PWM (`ledcWrite`)

---

## Optional Enhancements

- Enable PWM on ENA / ENB pins
- Add current sensing
- Add emergency stop timeout
- Add direction confirmation over UDP

---

## File Reference
ESP32 firmware file:
