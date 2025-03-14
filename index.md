# GIF Display Project

This project allows users to search for and display GIFs on an **Adafruit OLED screen**, controlled via a **TV remote**. The system uses **AWS Lambda, S3, and GIPHY API**.

## Features
- **Search GIFs** using a remote control
- **Display GIFs** on OLED
- **Rotate the screen** using an accelerometer
- **Smooth GIF rendering** (Stretch Goal)

## How It Works
1. The user enters a search query via the TV remote.
2. The system fetches GIFs using **AWS Lambda & GIPHY API**.
3. The user selects a GIF to display.
4. The chosen GIF appears on the **Adafruit OLED screen**.
5. The accelerometer enables **screen rotation**.

## System Architecture
![Architecture Diagram](diagram.png)

## Contributors
- **Logain Abdelhafiz**
- **Pranav Rawat**

---
