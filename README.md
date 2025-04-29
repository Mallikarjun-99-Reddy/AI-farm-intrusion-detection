# 🛡️ AI Farm Surveillance System

An AI-powered surveillance system to detect animal intrusions in farmland and send real-time SMS alerts using Twilio.

---

## ✨ Features
- **Animal Detection** using YOLOv8 (Nano version).
- **Image Preprocessing**: Grayscale conversion, histogram equalization, and sharpening.
- **Intrusion Alerts**: Sends SMS notifications via Twilio.
- **Real-time Image Upload and Processing** using Google Colab.

---

## 🛠️ Tech Stack
- **Language**: Python
- **Frameworks/Libraries**:
  - YOLOv8 (`ultralytics`)
  - OpenCV
  - NumPy
  - Matplotlib
  - Twilio
- **Tools**: Google Colab, Kaggle Datasets

---

## 🚀 How It Works
1. Upload images through Google Colab.
2. Preprocessing improves image quality for better detection.
3. YOLOv8 model detects animals like elephants, bears, horses, and sheep.
4. If an intrusion is confirmed, an SMS alert is sent to the farm owner's phone.

---

## ⚙️ Prerequisites
- Python 3.7+
- Google Colab account
- Twilio account (for SMS service)

---

## 📦 Installation

Install required libraries:

```bash
pip install ultralytics opencv-python-headless matplotlib twilio
```

Download dataset (in Colab):

```python
import kagglehub
path = kagglehub.dataset_download("awsaf49/coco-2017-dataset")
```

---

## 🧹 Usage
1. Open the Colab Notebook.
2. Upload farm surveillance images:
   ```python
   from google.colab import files
   uploaded = files.upload()
   ```
3. Automatically detects intrusions and sends SMS alerts.

---

## 🔧 Configuration
- **Model**:
  ```python
  model = YOLO('yolov8n.pt')
  ```
- **Twilio Credentials** (Update these with your own details):
  ```python
  account_sid = 'YOUR_TWILIO_ACCOUNT_SID'
  auth_token = 'YOUR_TWILIO_AUTH_TOKEN'
  from_number = 'YOUR_TWILIO_PHONE_NUMBER'
  to_number = 'YOUR_PHONE_NUMBER'
  ```

---

## 📤 Sample Output
- **Console Output**:
  ```
  Intrusion Detected!
  Class: 21, Confidence: 0.85, Box: (50, 30, 200, 180)
  SMS sent: SMXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
  ```
- **SMS Notification**:
  > "Alert: Animal intrusion detected in your farmland!"

---

## 📚 Dataset
- Dataset used: [COCO 2017 Dataset](https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset)

---

## ⚠️ Limitations
- Detection accuracy depends on input image quality.
- Animal categories are limited to specific classes by default.
- Requires internet connectivity for Twilio API usage.

---

## 🚀 Future Enhancements
- Live CCTV/video surveillance integration.
- Extended detection for more animal classes.
- Web dashboard for alert monitoring and statistics.



