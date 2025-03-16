---
title: "Software Implementation"
layout: default
permalink: /software/
---

# 💻 Software Implementation

### **1. GIF Retrieval**
- The **Giphy API** fetches GIF URLs based on the **user’s query**.
- AWS **Lambda functions** process the response.

### **2. AWS Lambda Processing**
- Converts GIFs to **RGB565** format for OLED display.
- Saves converted files to **AWS S3 storage**.

### **3. OLED Display Code**
- The CC3200 sends **frame-by-frame GIF data** to the **Adafruit OLED**.
- Uses **SPI communication**.

## **Software Flowchart**
![Software Flowchart](assets/software-flowchart.png)

🔹 **Go back to [Home](index.md).**
