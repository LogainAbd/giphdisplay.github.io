---
title: "GIF Display Project"
layout: default
---

# 🎥 GIF Display Project 
An interactive GIF display system using **AWS and Adafruit OLED**.

---

## 📌 Project Overview
Our final project is a **GIF Selector** that allows users to **search for GIFs online and display them on an Adafruit OLED screen**. 
The user interacts with the system using a **TV remote**, and the display **rotates** based on an **accelerometer**.

### 🌟 **Key Features**
✔️ **GIF Search via AWS Lambda & GIPHY API**  
✔️ **Remote-controlled selection**  
✔️ **GIF display on OLED screen**  
✔️ **Screen rotation with accelerometer**  

---

## 🎬 **Demo**
Watch our full **project demo** here:  
▶️ **[YouTube Link](https://youtu.be/G5EnyKVmVwM)**  

---

## 🏗 **System Architecture**
This diagram shows how different **components** interact in the project:

![System Architecture](assets/System Architecture.png)

- **TV Remote** → Sends signals via **IR Sensor**
- **CC3200 Launchpad** → Processes inputs & requests GIFs from **AWS**
- **AWS Lambda** → Fetches GIFs using **GIPHY API**
- **Adafruit OLED** → Displays GIFs
- **Accelerometer** → Controls **screen rotation**

---

## 🔄 **State Machine (How It Works)**
This flowchart illustrates the **user experience**:

![State Machine](assets/State Machine.png)

### **🛠 Step-by-Step Process**
1️⃣ **User enters a search query**  
2️⃣ **AWS fetches GIFs from GIPHY**  
3️⃣ **User selects a GIF from the results**  
4️⃣ **GIF is converted & displayed on OLED**  
5️⃣ **Accelerometer adjusts orientation**  

---

## 🔧 **Hardware Components**
The project was built using **these components**:
- 🎮 **TV Remote** (User input)
- 📡 **IR Sensor** (Receives signals)
- 🔢 **CC3200 Launchpad** (Processes data)
- 📺 **Adafruit OLED** (Displays GIFs)
- 🏎 **Accelerometer** (Screen rotation)
- ☁️ **AWS Lambda + GIPHY API** (Fetches GIFs)

---

## 📝 **Final Thoughts**
This project demonstrates **real-time GIF retrieval, image processing, and embedded systems integration**. 
We successfully achieved **smooth GIF playback and remote-controlled selection**.

### **👨‍💻 Created by:**
- **Logain Abdelhafiz**
- **Pranav Rawat**

---
