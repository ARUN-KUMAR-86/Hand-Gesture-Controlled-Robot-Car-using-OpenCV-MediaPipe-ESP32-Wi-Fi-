# Hand-Gesture-Controlled-Robot-Car-using-OpenCV-MediaPipe-ESP32-Wi-Fi-
A vision-based robot car control system using OpenCV and MediaPipe for real-time hand gesture recognition. Finger-count gestures are mapped to movement commands and transmitted wirelessly via UDP to an ESP32, which drives the motors accordingly, enabling intuitive, contactless control over Wi-Fi.

https://drive.google.com/file/d/1E0bZfi2SpKBmTR6FHMIGMs22d0PndoiH/view?usp=drive_link

# Gesture Controlled Car using ESP32 and OpenCV

This project controls a robotic car using hand gestures detected via
OpenCV and MediaPipe. Commands are transmitted wirelessly to an ESP32
over UDP WiFi.

## Architecture
PC Camera → OpenCV + MediaPipe → UDP Commands → ESP32 → Motor Driver → Car

## Folder Structure
- esp32_firmware/ : ESP32 UDP motor control code
- pc_controller/  : Python hand gesture detection
- hardware/       : Motor driver and wiring
- docs/           : Architecture diagrams
- demo/           : Working video

## Commands Mapping
| Fingers | Action   |
|--------|----------|
| 1      | Forward  |
| 2      | Backward |
| 3      | Left     |
| 4      | Right    |
| 0 / 5  | Stop     |

## How to Run
1. Upload ESP32 code
2. Update ESP32 IP in Python script
3. Run:
