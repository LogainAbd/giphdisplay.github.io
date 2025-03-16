---
title: "System Architecture"
layout: default
permalink: /architecture/
---

# 🖥️ System Architecture

## **System Workflow**
1. **User enters a search query** using the **TV Remote**.
2. The **CC3200 LaunchPad** sends the query to **AWS Lambda**, which interacts with the **Giphy API**.
3. **GIF links are retrieved** and sent to the user.
4. The user **selects a GIF**, and the **AWS Lambda function** converts it into an OLED-compatible format.
5. The **GIF is displayed** on the **Adafruit OLED** screen.
6. The **accelerometer** allows **rotation of the screen**.

# System Architecture 🏗️

This diagram explains the architecture of our project.

![System Architecture](assets/System%20Architecture.png)


# State Machine 🌀

The state machine of our project works as follows:

![State Machine](assets/State%20Machine.png)

🔹 **Go back to [Home](index.md).**
