---
title: "System Overview"
layout: default
---

# 🏗 System Overview  

The **workflow** begins when a user enters a **search query** using the **TV remote**. This query is sent to the **CC3200 LaunchPad**, which processes the request and sends it to the **Giphy API** through **AWS Lambda**. The API returns a **list of GIF URLs**, which are stored in **AWS S3 Storage**. The user then **selects a GIF** from the menu, and the **LaunchPad fetches and displays the animation** on the **OLED display**.

To **improve performance and responsiveness**, the system utilizes **Direct Memory Access (DMA)** for **efficient frame rendering**, reducing latency and improving playback. Additionally, the **accelerometer** continuously monitors **device orientation** and **automatically rotates the display**, ensuring an optimal **viewing experience**.

---

## 🔙 Return to Main Page  
<a href="index.md" style="display:inline-block; padding:10px 15px; background:#007bff; color:#fff; text-decoration:none; border-radius:5px;">⬅️ Go Back to Homepage</a>
