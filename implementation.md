---
title: "Implementation"
layout: default
---

# 🛠 Implementation

## 📡 TV Remote and IR Sensor
The TV remote was programmed with a specific TV code so that we could uniquely identify each button with our specific remote. By using our **Saleae Digital Logic Analyzer**, we were able to test and record each button’s corresponding output as a waveform and transform it into hexadecimal. This way, we could map each button to a **hexadecimal waveform** that can be identified by our **CC3200 board**.

The **IR sensor** was built in accordance with the **circuit diagram** provided by the manufacturer. The output of the sensor was connected to a **GPIO pin on the CC3200** in order to detect the waveforms as read by the Saleae. To detect these waveforms on the CC3200, we used a **GPIO interrupt handler**, which triggered on falling edges, and the **SysTick timer** to recognize whether a trigger corresponded to a **zero, one, or clear signal**. All other complexities were handled by the **CC3200 in button recognition**.

---

## ☁️ AWS Integration  
AWS served as the backbone of our prototype, handling interactions with the **GIPHY API** for storing and processing GIFs. Since the **TI CC3200** lacks the resources to process GIFs efficiently, we relied on **AWS services** like:

- **AWS IoT Core (Things)**
- **AWS S3 Buckets**
- **AWS Lambda Functions**  

### 🔹 **AWS IoT Core**
AWS IoT Core was used to **detect when users made search queries or selected GIFs**. We created a **device shadow** and set up **message routing rules** to trigger different events based on the user’s input.

- A **POST request** sent to our shadow contained **JSON-formatted search data**.  
- **SQL-based message routing** forwarded this information to an **AWS Lambda function**.  
- A **binary-encoded variable `getURL`** distinguished between **retrieving GIF URLs** (1) and **fetching the selected GIF** (0).  

### 🔹 **AWS S3 Buckets**
AWS S3 **stored** important data such as GIF URLs and **RGB565 frames**. To enable direct access from the **CC3200**, we **modified bucket permissions** to be **publicly accessible** via **HTTP GET requests**.

**Example S3 Bucket Policy:**
![S3 Bucket Policy](assets/image1.png)

To enable the **bucket policy**, we **disabled public access restrictions** and changed the **object ownership settings** to **"bucket owner preferred."**

---

## 🖥 AWS Lambda Functions
**AWS Lambda** managed **event-triggered processing** that the **CC3200** could not handle. We designed **three primary Lambda functions**:

- **`findGifs_Giphy`** – Searches GIFs based on user queries.  
- **`selectGIFfromGIPHY`** – Fetches the selected GIF for processing.  
- **`gifConverter`** – Converts GIF frames into the **RGB565 format** for display.

![AWS Lambda Functions](assets/image2.png)

### 🔹 **findGifs_Giphy**
This function **retrieves GIF URLs** from the **GIPHY API** after a **POST request** is made to AWS IoT Core with `getURL = 1`.  
Example event payload from **CC3200**:
![findGifs_Giphy Event](assets/image3.png)

### 🔹 **selectGIFfromGIPHY**
When the user **selects a GIF**, this function **downloads the GIF** from the web and stores it in **AWS S3**.  
Example event payload:
![selectGIFfromGIPHY Event](assets/image4.png)

### 🔹 **gifConverter**
Once a GIF is uploaded, **gifConverter** is triggered, processing each **GIF frame** and converting it into **RGB565 format** through **bit shifting**. The processed frames are then stored in **another S3 bucket**.  
Example JSON input to Lambda:
![gifConverter Event](assets/image5.png)

The **Pillow library** was used to **resize and convert images to RGB565** while ensuring **Big Endian byte ordering**, which is required for the **Adafruit OLED Display**.

---

## 🎛 **TI CC3200 Board Implementation**  

### 📡 **HTTP Request Handling**
The **CC3200 board** sends **GET and POST requests** via **secure sockets** and an **HTTP client library**.  
- **Secure Sockets**: Used for AWS IoT Core interactions.  
- **HTTP Client Library**: Adapted from **TI SDK v1.5** for **GIF retrieval**.  
- **GET Requests** were optimized to retrieve **byte/octet-stream** data from **AWS S3 buckets**.

**Key optimizations:**
- Used **snprintf** for JSON message formatting.  
- Limited **buffer size** to **2800 bytes** to handle large responses.  
- **Reconnected to the WiFi access point** before every request to prevent **timeouts**.

---

## 📟 **User Interface & Menu Navigation**
A **one-hot state machine** was implemented with the following states:
- **MENU** – User enters a search query.
- **SEND** – Query is sent to AWS Lambda.
- **DISPLAY** – Selected GIF is displayed.

To prevent **timing issues**, the **OLED display** was **updated only when necessary**, improving performance.

---

## 📱 **Accelerometer & OLED Display**
The **Adafruit OLED display** renders **RGB565 GIF frames** retrieved via **HTTP GET requests**.  
- **Each frame** is stored in a **data buffer** before being drawn to the screen.  
- **Pixels are bit-shifted** into **16-bit RGB565 format**.  
- **Screen orientation** is dynamically adjusted using **accelerometer readings**.  

### 🔹 **Optimizations**
- **Limited GIF size** to **65x65 pixels** to reduce memory overhead.  
- **Hard capped GIF frames at 25** to ensure smooth playback.

---

## 🔙 Return to Main Page  
[🔙 Return to Home](index.md)
