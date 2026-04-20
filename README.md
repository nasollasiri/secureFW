# 🔐 SecureFW Dashboard

### Secure OTA Firmware Update System for IoT Devices

---

## 📌 Overview

SecureFW is a complete **secure OTA (Over-the-Air) firmware update system** designed for IoT devices. It integrates **firmware management, device monitoring, and security mechanisms** into a single connected workflow using a React frontend and Flask backend.

The system ensures **secure firmware delivery**, **real-time monitoring**, and **attack detection**, making it ideal for academic projects, demos, and practical IoT security implementations.

---

## 🚀 Features

* 📦 **Firmware Management**

  * Upload firmware files
  * Store in version-controlled repository
  * Track deployment history

* 🔐 **Security Mechanisms**

  * Ed25519 digital signature for firmware signing
  * SHA-256 hashing for integrity verification
  * Secure verification before deployment

* 📡 **OTA Deployment**

  * Deploy firmware updates to IoT devices
  * Track update status in real-time

* 📊 **Interactive Dashboard (React UI)**

  * Device monitoring (status, version, verification)
  * Visual OTA pipeline
  * Clean and user-friendly interface

* ⚡ **Real-Time Communication**

  * MQTT-based device communication
  * Live update tracking and logs

* 🚨 **Attack Simulation**

  * Firmware tampering detection
  * Rollback attack simulation
  * MITM (Man-in-the-Middle) attack simulation

* 📢 **Alerts & Audit Logs**

  * Real-time alerts for threats
  * Detailed logs for:

    * Uploads
    * Signing
    * Deployments
    * Security incidents

* 🔄 **Rollback Mechanism**

  * Restore devices to safe firmware version

* 🧪 **Demo Mode**

  * Simulate successful/failed updates for presentation

---

## 🏗️ Architecture

```
Frontend (React Dashboard)
        ↓
Flask Backend (Kali Linux VM)
        ↓
MQTT Broker (Mosquitto)
        ↓
IoT Devices (ESP32 / Simulated)
```

* **Frontend:** React (App.js / kali_secureFW.js)
* **Backend:** Flask (app.py)
* **Communication:** REST API + WebSockets + MQTT
* **Ports Used:**

  * `5000` → Flask API
  * `1883` → MQTT Broker

---

## ⚙️ Setup Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/secureFW.git
cd secureFW
```

---

### 2️⃣ Backend Setup (Kali Linux)

```bash
pip3 install flask flask-socketio flask-cors paho-mqtt cryptography requests eventlet --break-system-packages

sudo apt install mosquitto mosquitto-clients -y
sudo systemctl start mosquitto
```

Run backend:

```bash
cd server
python3 app.py
```

---

### 3️⃣ Frontend Setup

```bash
cd secureFW-frontend
npm install
npm start
```

---

### 4️⃣ Configure IP (IMPORTANT)

Edit in `App.js`:

```js
const KALI_IP = 'YOUR_KALI_IP';
```

---

### 5️⃣ VMware Network (IMPORTANT)

* Set **Network Mode → Bridged**
* Ensure Kali has its own IP
* Open ports:

```bash
sudo ufw allow 5000
sudo ufw allow 1883
```

---

## 🧪 API Endpoints

| Endpoint       | Description                   |
| -------------- | ----------------------------- |
| `/api/status`  | Check backend & broker status |
| `/api/devices` | Get device list               |
| `/api/upload`  | Upload firmware               |
| `/api/sign`    | Sign firmware                 |
| `/api/deploy`  | Deploy firmware               |

---

## 📊 Dashboard Features

* Device Status Monitoring
* Firmware Upload & Signing
* Deployment Tracking
* MQTT Live Feed
* Attack Simulation Panel
* Alerts & Logs

---

## 🔐 Security Highlights

* ✔ Digital Signature (Ed25519)
* ✔ Integrity Check (SHA-256)
* ✔ Secure OTA Pipeline
* ✔ Attack Detection & Alerts
* ✔ Rollback Protection

---

## 🧑‍💻 Tech Stack

* **Frontend:** React.js
* **Backend:** Flask (Python)
* **Messaging:** MQTT (Mosquitto)
* **Security:** Ed25519, SHA-256
* **Environment:** Kali Linux (VMware)

---

## 📸 Demo Flow

1. Upload Firmware
2. Sign Firmware
3. Deploy to Device
4. Verify Integrity
5. Monitor via Dashboard
6. Simulate Attack → View Alerts

---

## 📁 Project Structure

```
secureFW/
│
├── server/
│   └── app.py
│
├── secureFW-frontend/
│   ├── src/
│   │   └── App.js
│
├── keys/
│   ├── private_ed25519.pem
│   └── public_ed25519.pem
```

---

## 🎯 Use Cases

* IoT Security Projects
* Firmware Update Systems
* Cybersecurity Demonstrations
* Academic Final Year Projects

---

## 🏁 Conclusion

SecureFW provides a **secure, practical, and demo-ready OTA system** with real-time monitoring, attack simulation, and strong security mechanisms, making it a powerful solution for modern IoT environments.

