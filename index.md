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

## **📂 Project Overview**
The **GIF Displayer Project** is an **embedded system application** that retrieves, processes, and displays **GIFs** using a **CC3200 LaunchPad** and an **Adafruit OLED Display**. The system is controlled via a **TV remote and IR sensor**, allowing users to **search for GIFs, select results, and display animations** on the **OLED screen**. To ensure smooth **real-time GIF retrieval and display**, the system **leverages AWS services**, including **AWS Lambda** and **S3 storage**. Additionally, an **accelerometer** enables **automatic screen rotation**, ensuring an **adaptive and user-friendly experience**.

---

## **📑 Table of Contents**
Click on any section below to navigate:

- [📜 Project Description](#project-description)
- [🎥 Video Demo](#video-demo)
- [🖥 System Architecture](#system-architecture)
- [🔄 State Machine & Workflow](#state-machine--workflow)
- [🛠 Implementation & Challenges](#implementation--challenges)
- [🔮 Future Enhancements](#future-enhancements)
- [🧾 Bill of Materials](#bill-of-materials)
- [📢 Conclusion](#conclusion)

---

## **📜 Project Description**
The **GIF Displayer Project** integrates **cloud computing and embedded systems** to enable **real-time GIF retrieval, processing, and display** on an **OLED screen**. By leveraging **AWS services**, the system efficiently **fetches GIFs from Giphy, stores them in S3, and processes them through AWS Lambda**, ensuring optimized playback. The **CC3200 LaunchPad** is the main processing unit, interacting with the **IR sensor, TV remote, accelerometer, and Adafruit OLED Display**.

---

## **🎥 Video Demo**
Click below to watch the **full demonstration** of our project:

📌 **[Watch the Demo](https://youtu.be/G5EnyKVmVwM)**

---

## **🖥 System Architecture**
The **system architecture** consists of several key components working together to ensure **seamless GIF retrieval and display**:

### **🔹 TV Remote & IR Sensor**  
- The **TV remote** allows users to control the system.  
- The **IR sensor** captures signals and sends them to the **CC3200 LaunchPad** via **GPIO interrupts**.

### **🔹 CC3200 LaunchPad**  
- Acts as the **central processing unit**.  
- **Processes user input**, **sends API requests**, **retrieves GIF data**, and **renders animations** on the OLED display.  
- Communicates with the **Adafruit OLED via SPI** and with the **accelerometer via I2C**.

### **🔹 AWS Lambda & Giphy API**  
- AWS Lambda serves as the **middleware** between the **CC3200 LaunchPad and Giphy API**.  
- **Receives user queries**, **fetches relevant GIFs**, and **stores their URLs in AWS S3 Storage**.  

### **🔹 Adafruit OLED Display**  
- Displays **selected GIFs**, using **optimized frame rendering** for smooth playback.

### **🔹 Accelerometer**  
- **Detects device orientation** and **adjusts the display** dynamically.  
- Enhances **user experience** by providing an **adaptive interface**.

### **📌 System Architecture Diagram**
![System Architecture](assets/System_Architecture.png)

---

## **🔄 State Machine & Workflow**
The **state machine diagram** outlines the **step-by-step process** of how the system **retrieves and displays GIFs**:

1️⃣ **User Input**: The system **waits for user input** via the TV remote.  
2️⃣ **GIF Retrieval from AWS**: The **query is sent to AWS Lambda**, which **fetches relevant GIFs from Giphy**.  
3️⃣ **GIF Selection**: The system presents the **retrieved GIF URLs** in a **menu selection**.  
4️⃣ **GIF Processing & Display**: AWS Lambda **processes the GIF** into **RGB565 format** for **optimal OLED display**.  
5️⃣ **Dynamic Screen Rotation**: The **accelerometer detects movement** and **adjusts the orientation dynamically**.

### **📌 State Machine Diagram**
![State Machine](assets/State_Machine.png)

---

## **🛠 Implementation & Challenges**
### **⚠️ Key Challenges & Solutions**
| **Challenge** | **Solution Implemented** |
|--------------|----------------------|
| **Efficient GIF Processing** | AWS Lambda **handles GIF retrieval & URL storage** |
| **Latency in GIF Rendering** | **DMA-based rendering** accelerates frame loading |
| **Remote Responsiveness** | **Interrupt-driven IR signal processing** improves UI responsiveness |
| **Screen Rotation Stability** | **Motion filtering algorithms** prevent erratic rotations |

---

## **🔮 Future Enhancements**
To further **enhance** the GIF Displayer Project, we propose several **cutting-edge improvements**:

### **🔊 Voice Command with Alexa**  
We plan to **integrate Amazon Alexa voice commands**, allowing users to **search for GIFs, select results, and display them hands-free**. This feature would make the system more **accessible, convenient, and interactive**.

### **📡 GIF Sharing Between Devices**  
Instead of just displaying GIFs **locally**, the system could be expanded to **send GIFs to other OLED screens**. Using **AWS IoT communication**, multiple embedded devices could **synchronize animations in real-time**.

### **⚡ DMA Optimization for Animation Rendering**  
To further **improve GIF playback**, **advanced DMA techniques** will be implemented, ensuring **high-speed frame buffering, smooth animations, and minimal lag**.

### **🌍 Multi-Device Synchronization**  
With AWS Lambda and S3 storage, we can **synchronize playback** across **multiple embedded OLED devices**, allowing users to experience GIFs in a shared environment.

---

## **🧾 Bill of Materials**
| **Component** | **Quantity** | **Source** |
|--------------|------------|-----------|
| CC3200 LaunchPad | 1 | Lab Kit ($66) |
| Adafruit OLED Display | 1 | Lab Kit ($40) |
| IR Sensor | 1 | Lab Kit ($2) |
| TV Remote | 1 | Lab Kit ($10) |
| AWS Services | N/A | AWS Account |

---

## **📢 Conclusion**
The **GIF Displayer Project** successfully demonstrates **real-time GIF retrieval, cloud-based processing, and embedded display rendering** within a **constrained hardware environment**. The combination of **efficient hardware-software interaction, cloud-based data management, and real-time processing** makes this system a **novel and effective solution for GIF display**.

This project serves as a foundation for **future embedded media display applications**, with potential enhancements such as **voice integration, cross-device GIF sharing, and optimized DMA-based rendering**.

---

### **🎓 Developed by:**
💻 **Pranav Rawat**  
💻 **Logain Abdelhafiz**  

---
