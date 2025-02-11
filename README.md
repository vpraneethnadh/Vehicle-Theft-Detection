# 🚗 Vehicle Theft Detection System 🔐

## 📌 Overview
The **Vehicle Theft Detection System** is a hardware-based security system designed to prevent unauthorized access to a vehicle. It leverages **face recognition technology** and **live location tracking** to identify unauthorized users and send alerts. The system can be implemented using hardware components such as a **WiFi module, Raspberry Pi, motor, and key module**, or it can be simulated on a local computer.

## 🎯 How It Works
1. 🔑 **Key Turned On** → The system captures an image of the user's face using a camera.
2. 📸 **Face Recognition** → The captured image is compared with a pre-stored authorized image.
3. ✅ **Authorized User (≥70%)** → The system starts the engine.
4. 🚨 **Unauthorized User (<70%)** → The system:
   - Captures an image of the unauthorized user.
   - Fetches the live location details.
   - Sends an **email alert** to the owner with the captured image and location details.

## 🛠️ Components Required
- 🖥️ **Raspberry Pi**
- 📶 **WiFi Module**
- ⚙️ **Motor (to simulate engine start/stop)**
- 🔑 **Key Module**
- 📷 **Camera Module**
- 🔋 **Power Supply**

## 🏗️ Technologies and Modules Used
### 1️⃣ **OpenCV (cv2)**
   - 🎥 Used for capturing images through the camera.
   - 📁 Handles image processing tasks like saving and displaying images.

### 2️⃣ **face_recognition**
   - 🧑‍💻 A Python library for facial recognition.
   - 🖼️ Used to encode facial features and compute similarity between stored and captured images.

### 3️⃣ **smtplib & email.mime**
   - 📩 Used for sending emails.
   - 📎 The captured image is attached to an email and sent to the owner if an unauthorized user is detected.

### 4️⃣ **os (Operating System Module)**
   - 📂 Used to check and create directories for storing images.

### 5️⃣ **geopy.geocoders (Nominatim API)**
   - 🌍 Fetches live location details of the vehicle.
   - 📌 Provides latitude, longitude, city, state, and country information.

## 🚀 Features
✅ **Face Recognition-Based Access Control**: Ensures that only authorized users can start the vehicle.  
📸 **Automated Image Capture**: Captures an image when the key is turned on.  
🔍 **Similarity Score Calculation**: Compares the captured image with the stored authorized image.  
📩 **Email Alert with Attachment**: Sends an email alert if unauthorized access is detected.  
🌍 **Live Location Tracking**: Fetches and sends real-time location data.  
🚗 **Engine Control Mechanism**: Starts the engine only if the user is authorized.  

## 🛠️ Installation & Setup
1️⃣ **Install Dependencies:**
   ```bash
   pip install opencv-python face-recognition geopy smtplib
   ```
2️⃣ **Set Up Email Configuration:**
   - ✏️ Update `fromaddr` with `your-email@example.com` (Sender's email ID).
   - ✏️ Update `toaddr` with `your-email@example.com` (Receiver's email ID).
   - 🔑 Replace the `password` with the email's app password.

3️⃣ **Run the Script:**
   ```bash
   python vehicle_theft_detection.py
   ```
