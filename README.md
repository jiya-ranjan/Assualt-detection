# 🚨 Real-Time Assault Detection and Alert System Using Deep Learning

A deep learning based real-time surveillance system that automatically detects violent activities in CCTV footage and instantly alerts the concerned authorities via Telegram.

---

## 📌 Project Description

This system monitors live video feeds from surveillance cameras and uses **MobileNet V2** to classify video frames as violent or non-violent. When sustained violence is detected across 30 consecutive frames, an automated alert is sent to authorities via a **Telegram Bot** containing the captured image, timestamp, and camera location — all without any manual monitoring.

---

## ✨ Features

- 🎥 **Real-Time Video Processing** — Continuously monitors live CCTV footage
- 🧍 **Human Detection** — Uses pre-trained Faster R-CNN to filter frames with humans only
- 🧠 **Violence Detection** — MobileNet V2 classifies frames as Violent or Non-Violent
- 🔔 **Automated Alert System** — Sends Telegram notification with image, time and location
- ✅ **False Alarm Prevention** — Counter-based mechanism (30 consecutive frames) to avoid false alerts
- ⚡ **Lightweight & Efficient** — Runs on standard hardware without expensive GPU

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Deep Learning Framework | TensorFlow / Keras |
| Violence Detection Model | MobileNet V2 (Pre-trained) |
| Human Detection Model | Faster R-CNN (Pre-trained) |
| Video Processing | OpenCV |
| Image Enhancement | Python Imaging Library (PIL) |
| Alert System | Telegram Bot API |
| Training Platform | Google Colaboratory |

---

## 📊 Model Performance

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| Non-Violence | 0.92 | 0.91 | 0.92 | 1778 |
| Violence | 0.93 | 0.94 | 0.94 | 2416 |
| **Overall Accuracy** | **0.93** | **0.93** | **0.93** | **4194** |

---

## 🗂️ Project Structure

```
├── dataset/
│   ├── violence/
│   └── non_violence/
├── model/
│   └── mobilenetv2_violence.h5
├── detection/
│   ├── human_detection.py
│   └── violence_detection.py
├── alert/
│   └── telegram_alert.py
├── main.py
└── README.md
```

---

## ⚙️ How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install Dependencies
```bash
pip install tensorflow opencv-python pillow requests python-telegram-bot
```

### 3. Set Up Telegram Bot
- Create a Telegram Bot using **@BotFather**
- Get your **Bot Token** and **Chat ID**
- Update these in `alert/telegram_alert.py`
```python
BOT_TOKEN = "your-bot-token-here"
CHAT_ID = "your-chat-id-here"
```

### 4. Set Camera Location
Update your camera location in `main.py`
```python
CAMERA_LOCATION = "Your Location Name"
```

### 5. Run the System
```bash
python main.py
```

---

## 🔄 System Pipeline

```
CCTV Camera
    ↓
Frame Extraction
    ↓
Faster R-CNN → Human Detected?
    ↓ No  → Discard Frame
    ↓ Yes
MobileNet V2 → Violence Detected?
    ↓ No  → Discard Frame
    ↓ Yes
Counter = 30 Consecutive Frames?
    ↓ Yes
Telegram Alert → (Image + Timestamp + Location)
```

---

## 📦 Dataset

- **Total Videos:** 1000 clips (Violence + Non-Violence)
- **Average Duration:** ~5 seconds per clip
- **Source:** Majority from real CCTV footage
- **Training Split:** 350 videos per class per epoch

---



## 📚 References

- H. Khan et al., "Violence Detection From Industrial Surveillance Videos Using Deep Learning," IEEE Access, 2025.
- P. Negre et al., "Literature Review of Deep-Learning-Based Detection of Violence in Video," Sensors, 2024.
- L. Hsairi et al., "Violence Detection Using Deep Learning," Arabian Journal for Science and Engineering, 2024.

---

## 👨‍💻 Team

| Name | Roll No |
|---|---|
| JIYA RANJAN| 2021256 |
| SNEHA | 2021468 |


---

## 📄 License

This project is submitted as part of B.Tech Major Project requirements.
