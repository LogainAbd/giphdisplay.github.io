# 🎥 GIF Display Project  
📍 **University of California, Davis**  
👨‍🏫 **Professor:** Soheil Ghiasi  
🛠 **TA:** Randall Fowler  

👨‍💻 **Developed by:**  
- **Logain Abdelhafiz**  
- **Pranav Rawat**  

---

## **📌 Introduction**  
The **GIF Displayer Project** is an **embedded system application** that retrieves, processes, and displays **GIFs** using a **CC3200 LaunchPad** and an **Adafruit OLED Display**. The project was designed to **enhance user interaction** with animated media while working within **hardware constraints**.  

The system is **controlled via a TV remote and an IR sensor**, allowing users to **search for GIFs, select results, and display animations** on the **OLED screen**. To ensure smooth **real-time GIF retrieval and display**, the system **leverages AWS services**, including **AWS Lambda** and **S3 storage**. Additionally, an **accelerometer** enables **automatic screen rotation**, ensuring an **adaptive and user-friendly experience**.

This project showcases the **integration of cloud-based data management, efficient embedded processing, and interactive user control**, making it a novel **GIF display solution for resource-limited systems**.

---

## **🏗 System Overview**  
The **workflow** begins when a user enters a **search query** using the **TV remote**. This query is sent to the **CC3200 LaunchPad**, which processes the request and sends it to the **Giphy API** through **AWS Lambda**. The API returns a **list of GIF URLs**, which are stored in **AWS S3 Storage**. The user then **selects a GIF** from the menu, and the **LaunchPad fetches and displays the animation** on the **OLED display**.

To **improve performance and responsiveness**, the system utilizes **Direct Memory Access (DMA)** for **efficient frame rendering**, reducing latency and improving playback. Additionally, the **accelerometer** continuously monitors **device orientation** and **automatically rotates the display**, ensuring an optimal **viewing experience**.

---

## **🖥 System Architecture**  
The **system architecture** consists of several key components working together to ensure **seamless GIF retrieval and display**:

### **🔹 TV Remote & IR Sensor**  
- The **TV remote** acts as the primary user interface.  
- The **IR sensor** captures signals from the remote and sends them as **GPIO interrupts** to the **CC3200 LaunchPad**.

### **🔹 CC3200 LaunchPad**  
- Serves as the **central processing unit** for the system.  
- **Processes user input**, **sends API requests**, **retrieves GIF data**, and **renders animations** on the OLED display.  
- Communicates with the **Adafruit OLED via SPI** and with the **accelerometer via I2C**.

### **🔹 AWS Lambda & Giphy API**  
- AWS Lambda serves as the **middleware** between the **CC3200 LaunchPad and Giphy API**.  
- **Receives user queries**, **fetches relevant GIFs**, and **stores their URLs in S3**.  

### **🔹 Adafruit OLED Display**  
- The **primary output** where **selected GIFs** are **displayed**.  
- Works with **optimized frame rendering** to ensure smooth playback.

### **🔹 Accelerometer**  
- **Detects device orientation** and **adjusts the display** accordingly.  
- Enhances **user experience** by providing an **adaptive interface**.

### **📌 Architecture Diagram**
![System Architecture](assets/System_Architecture.png)

---

## **🔄 State Machine & Workflow**
The **state machine diagram** outlines the **step-by-step process** of how the system **retrieves and displays GIFs**:

### **🚀 Step 1: User Input**  
- The system **waits for user input** via the TV remote.  
- The user **enters a search query**.

### **🌐 Step 2: GIF Retrieval from AWS**  
- The **query is sent to AWS Lambda**, which **fetches relevant GIFs from Giphy**.  
- The GIF URLs are **stored in AWS S3 Storage**.

### **📄 Step 3: GIF Selection**  
- The system presents the **retrieved GIF URLs** in a **menu selection**.  
- The user navigates the menu and selects a **desired GIF**.

### **📲 Step 4: GIF Processing & Display**  
- AWS Lambda **processes the GIF**, converting it into **RGB565 format** for **optimal display**.  
- The CC3200 **renders the frames** and **displays the animation** on the OLED screen.

### **🔄 Step 5: Dynamic Screen Rotation**  
- The **accelerometer detects movement** and **adjusts the orientation dynamically**.

### **📌 State Machine Diagram**
![State Machine](assets/State_Machine.png)

---

## **🛠 Implementation & Challenges**
### **⚠️ Key Challenges & Solutions**
The system faced **several design and implementation challenges**, which were resolved with **carefully designed solutions**:

| **Challenge** | **Solution Implemented** |
|--------------|----------------------|
| **Efficient GIF Processing** | AWS Lambda **handles GIF retrieval & URL storage** |
| **Latency in GIF Rendering** | **DMA-based rendering** accelerates frame loading |
| **Remote Responsiveness** | **Interrupt-driven IR signal processing** improves UI responsiveness |
| **Screen Rotation Stability** | **Motion filtering algorithms** prevent erratic rotations |

---

## **🔮 Future Enhancements**
To **further enhance** the project, the following features could be integrated:

✨ **Voice Command Integration** – Enabling hands-free GIF search and selection.  
🎨 **UI Enhancements** – Adding categorized GIF browsing for improved user experience.  
⚡ **Optimized Animation Handling** – Further improving rendering efficiency to ensure smoother GIF playback.  

---

## **🧾 Bill of Materials**
The following **hardware components** were used in the project:

| **Component** | **Quantity** | **Source** |
|--------------|------------|-----------|
| CC3200 LaunchPad | 1 | Lab Kit |
| Adafruit OLED Display | 1 | Lab Kit |
| IR Sensor | 1 | Lab Kit |
| TV Remote | 1 | Lab Kit |
| AWS Services | N/A | AWS Account |
| Accelerometer | 1 | Lab Kit |

---

## **📢 Conclusion**
The **GIF Displayer Project** successfully integrates **real-time GIF retrieval, cloud-based processing, and embedded display rendering** within a **constrained hardware environment**. This project highlights the **effective combination of embedded systems with cloud services**, demonstrating how **AWS and real-time processing can enhance small-scale displays**.

This **professional solution** ensures **seamless GIF display and adaptive screen rotation**, providing a **smooth user experience**. The project serves as a strong foundation for **future embedded media display applications**.

---

### **🎓 Developed by:**
💻 **Pranav Rawat**  
💻 **Logain Abdelhafiz**  

---
