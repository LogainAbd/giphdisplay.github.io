---
title: "State Machine & Workflow"
layout: default
---

# 🔄 State Machine & Workflow  

The **state machine** outlines how the system **retrieves and displays GIFs** step-by-step.

### **📌 State Machine Diagram**
![State Machine](assets/State%20Machine.png)

The system follows this structured workflow:
1️⃣ **User enters a search query via remote.**  
2️⃣ **CC3200 sends the query to AWS Lambda & Giphy API.**  
3️⃣ **GIF URLs are retrieved and displayed as options.**  
4️⃣ **User selects a GIF; AWS Lambda processes and stores it.**  
5️⃣ **LaunchPad fetches and displays the GIF on OLED.**  
6️⃣ **Accelerometer ensures dynamic screen rotation.**  

---

## 🔙 Return to Main Page  
[🔙 Return to Home](index.md)

