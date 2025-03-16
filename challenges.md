---
title: "Challenges"
layout: default
---

# 🚧 Challenges

The **main challenges** in this project revolved around **integrating AWS services** with the **CC3200 LaunchPad** and optimizing **GIF rendering**.

## ⚙️ **AWS Integration & HTTP Client Stability**
One of the most difficult aspects of this project was **ensuring smooth communication between the CC3200 board and AWS services**. We encountered:
- **Random HTTP client crashes**, causing unexpected failures.
- **Delays in AWS request handling**, affecting the response time.
- **Difficulties in configuring AWS Lambda and S3 storage**.

📌 **Solution**: We resolved these issues by **extensively testing API requests**, **debugging the HTTP client**, and **refining Lambda execution timings** to ensure smoother communication.

---

## 🎞 **GIF Rendering Speed Optimization**
A significant challenge was the **slow GIF playback speed**. Initially, rendering animations took **~4 seconds per frame**, making playback sluggish.

📌 **Problems Identified**:
- The **`drawPixel()`** function on the OLED screen was **too slow**.
- **GET requests for each frame** caused **network latency bottlenecks**.
- The **SPI buffer rate** was **not optimized** for rapid data transfer.

✅ **Solution Implemented**:
- Increased **SPI buffer speed** to **improve frame transfer rate**.
- Explored **DMA-based rendering** to **reduce processing overhead**.
- Adjusted **frame handling logic** to **minimize network delays**.

While the playback is now much smoother, further improvements **using a dedicated framebuffer and optimized DMA transfers** could make it **even faster**.

---

## 🔙 [⬅ Return to Main Page](/)
