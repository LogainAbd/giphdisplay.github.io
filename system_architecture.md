---
title: "System Architecture"
layout: default
---

# 🖥 System Architecture  

This **diagram** shows how all components interact within the system.

### **📌 System Architecture Diagram**
![System Architecture](assets/System%20Architecture.png)

The **system architecture** consists of several key components working together to ensure **seamless GIF retrieval and display**:

- **TV Remote & IR Sensor:** Captures user input and sends signals to the CC3200 LaunchPad.  
- **CC3200 LaunchPad:** Handles user input, API requests, and GIF display.  
- **AWS Lambda & Giphy API:** Fetches GIF URLs and processes the images.  
- **Adafruit OLED Display:** Displays the selected GIF.  
- **Accelerometer:** Adjusts the screen orientation dynamically.

---
## 🔙 Return to Main Page  
[🔙 Return to Home](index.md)

