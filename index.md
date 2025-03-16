---
title: "GIF Display Project"
layout: default
---

# 🎥 GIF Display Project  
📍 **University of California, Davis**  
👨‍🏫 **Professor:** Soheil Ghiasi  
🛠 **TA:** Randall Fowler  

👨‍💻 **Developed by:**  
- **Logain Abdelhafiz**  
- **Pranav Rawat**  

---

## 📌 **Table of Contents**
- [📜 Introduction](#introduction)
- [🏗 System Overview](#system-overview)
- [🖥 System Architecture](#system-architecture)
- [🔄 State Machine & Workflow](#state-machine--workflow)
- [🛠 Implementation & Challenges](#implementation--challenges)
- [🚀 Future Enhancements](#future-enhancements)
- [🧾 Bill of Materials](#bill-of-materials)
- [📢 Conclusion](#conclusion)
- [🎥 Video Demo](#video-demo)

---

## **📜 Introduction**
The **GIF Displayer Project** is an **embedded system application** that retrieves, processes, and displays **GIFs** using a **CC3200 LaunchPad** and an **Adafruit OLED Display**. The system is controlled via a **TV remote and IR sensor**, allowing users to search, select, and display GIFs. AWS services, including **AWS Lambda** and **S3 storage**, enable real-time GIF retrieval. The **accelerometer** dynamically rotates the display, ensuring an **adaptive user experience**.

---

## **🏗 System Overview**
The workflow begins when a user **searches for a GIF using the TV remote**. The **CC3200 LaunchPad** sends this query to **AWS Lambda**, which retrieves GIF URLs from the **Giphy API** and stores them in an **S3 bucket**. Users select a GIF, which is processed and displayed on the **OLED screen**.

For **smooth animations**, the system employs **Direct Memory Access (DMA)** for optimized frame rendering, reducing **latency and flickering**. The **accelerometer** detects orientation and adjusts the display in **real time**.

---

## **🖥 System Architecture**
The **system consists of multiple interconnected components**, as shown in the **architecture diagram**:

### **📌 Architecture Diagram**
![System Architecture](assets/System_Architecture.png)

**Key Components:**
- **TV Remote & IR Sensor**: Captures user input as GPIO interrupts.
- **CC3200 LaunchPad**: Manages processing, API requests, and OLED display rendering.
- **AWS Lambda & Giphy API**: Retrieves and processes GIFs.
- **Adafruit OLED Display**: Displays GIFs with optimized animation playback.
- **Accelerometer**: Enables automatic screen rotation.

---

## **🔄 State Machine & Workflow**
The system transitions between different states **based on user input**. The diagram below illustrates **step-by-step processing** of GIF retrieval and display.

### **📌 State Machine Diagram**
![State Machine](assets/State_Machine.png)

**How it Works:**
1. **User enters search query** via remote.
2. **AWS Lambda fetches GIFs** from the Giphy API.
3. **User selects a GIF**, which is **processed & optimized** for display.
4. **Frames are rendered on the OLED screen** using **DMA acceleration**.
5. **The accelerometer detects tilt**, adjusting the screen accordingly.

---

## **🛠 Implementation & Challenges**
### **⚠️ Key Challenges & Solutions**
The project faced **various technical challenges**, which were resolved through **optimization strategies**:

| **Challenge**                 | **Solution Implemented**                                     |
|-------------------------------|-------------------------------------------------------------|
| Efficient GIF Processing      | AWS Lambda **handles retrieval & URL storage**             |
| Latency in GIF Rendering      | **DMA-based rendering** improves frame loading speed       |
| Remote Responsiveness         | **Interrupt-driven IR processing** ensures smooth UI       |
| Screen Rotation Stability     | **Motion filtering algorithms** prevent erratic rotations  |

---

## **🚀 Future Enhancements**
To further improve the project, several features can be integrated:

### **🌟 Voice Command Integration (Alexa)**
Future iterations could incorporate **Alexa integration**, enabling users to **search for GIFs via voice commands**. Users could say,  
👉 **“Alexa, find me a cat GIF”**, and the system would **fetch and display the requested animation**.

Additionally, **GIFs could be wirelessly shared between multiple OLED screens**, allowing real-time **GIF broadcasting across different devices**.

### **🎨 UI Enhancements**
A **graphical user interface (GUI)** could be added to provide **GIF categories**, making navigation and selection **more intuitive**.

### **⚡ Optimized Animation Handling**
Further **enhancements to DMA rendering** could reduce **frame lag**, ensuring even **smoother playback** on embedded hardware.

---

## **🧾 Bill of Materials**
The **updated Bill of Materials** lists all required components:

| **Component**          | **Quantity** | **Source**          |
|-----------------------|------------|--------------------|
| CC3200 LaunchPad     | 1          | Lab Kit **($66)**  |
| Adafruit OLED Display| 1          | Lab Kit **($40)**  |
| IR Sensor            | 1          | Lab Kit **($2)**   |
| TV Remote           | 1          | Lab Kit **($10)**  |
| AWS Services         | N/A        | AWS Account        |

---

## **📢 Conclusion**
The **GIF Displayer Project** successfully integrates **real-time GIF retrieval, cloud processing, and embedded rendering** within a **constrained hardware environment**. By **leveraging AWS and efficient data handling**, the project provides **a seamless GIF browsing experience**.

With **enhanced animation playback, dynamic screen rotation, and cloud-based retrieval**, this project sets the foundation for **interactive embedded media solutions**.

---

## **🎥 Video Demo**
🎬 **Check out the project in action!**  
📺 **[Watch the Demo Here](https://youtu.be/ePIa4oJOAQ0?si=5XlpDbn1atBiujxr)**  

---

### **🎓 Developed by:**
💻 **Pranav Rawat**  
💻 **Logain Abdelhafiz**  
📅 **Winter 2025 – University of California, Davis**  

---
