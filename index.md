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
- 📅 **Winter 2025 – University of California, Davis**   

---

## 📌 **Project Overview**  

The **GIF Displayer** is an **interactive embedded system** that allows users to search for and display **animated GIFs** on an **Adafruit OLED display** using **Amazon Web Services (AWS)**. Designed for a **seamless user experience**, this system integrates **IR remote navigation, AWS-based GIF retrieval, and real-time animation playback** on a resource-constrained embedded device.

---

## 🔹 **How It Works**
- Users **enter a search query** using a **TV remote** and **IR sensor**.
- The **CC3200 LaunchPad** processes the request and communicates with **AWS Lambda**, which fetches **five relevant GIFs** from the **Giphy API**.
- The retrieved **GIFs are displayed** as selectable options on the OLED screen.
- The user **chooses a GIF** by pressing its number and the “OK” button.

---

## 🔄 **User Interaction & Controls**
- After selecting a **GIF**, users can:
  - **🔁 Play through** the GIF **frame-by-frame**.
  - **🔙 Go back** to the search menu.
  - **🎬 Pick another GIF** from the list.
- The **accelerometer** detects **screen orientation**, allowing users to **rotate the display dynamically**.

---

This project demonstrates a **real-time multimedia experience on embedded hardware**, combining **efficient cloud-based data retrieval, responsive UI navigation, and smooth GIF rendering**.

---

## 🎬 **Project Demonstration**
Check out the full **video demo** of our project:  
🎥 [Watch the Demo](https://youtu.be/ePIa4oJOAQ0?si=5XlpDbn1atBiujxr)  

---

## 📌 **Project Sections**
🔹 Click on a section below to view details:

- 🏗 [**System Overview**](system_overview.md)  
- 🖥 [**System Architecture**](system_architecture.md)  
- 🔄 [**State Machine & Workflow**](state_machine.md)  
- 🛠 [**Implementation**](implementation.md)  
- ⚠️ [**Challenges**](challenges.md)  
- 🚀 [**Future Enhancements**](future_enhancements.md)  
- 🧾 [**Bill of Materials**](bill_of_materials.md)  
- 📢 [**Conclusion**](conclusion.md)  

---

### **📌 System Diagrams**
📊 **System Architecture Diagram**  
![System Architecture](assets/System%20Architecture.png)

📊 **State Machine Diagram**  
![State Machine](assets/State%20Machine.png)

---

## ✨ **Acknowledgements**

We would like to express our **sincere gratitude** to **Professor Soheil Ghiasi** for his guidance and expertise throughout the development of this project. A special thanks to **TA Randall Fowler** for providing valuable feedback and support during implementation.

Additionally, we appreciate the **resources and facilities** provided by the **University of California, Davis** that enabled us to bring this project to life.

---
