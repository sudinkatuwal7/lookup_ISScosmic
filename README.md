# 🚀 lookup_ISScosmic — ISS Overhead Notifier

lookup_ISScosmic is a Python program that monitors the position of the **International Space Station (ISS)** and sends you an **email notification** when the ISS passes close to your location during nighttime.

Instead of constantly checking the sky, this script automatically tracks the ISS using public APIs and alerts you when it might be visible.

---

## 🌌 Features

- 🛰 Tracks the **real-time location** of the International Space Station  
- 📍 Checks if the ISS is within **±5° of your location**  
- 🌙 Determines whether it is **currently nighttime** at your coordinates  
- 📧 Sends an **email notification** when the ISS is visible  
- ⏱ Automatically checks conditions every **60 seconds**

---

## 📡 APIs Used

This project uses two public APIs:

### ISS Location API
Provides the real-time coordinates of the ISS.

`
http://api.open-notify.org/iss-now.json
`

### Sunrise-Sunset API
Provides sunrise and sunset times for any location.

`
https://api.sunrise-sunset.org/json
`

---

## 🛠 Technologies Used

- Python
- `requests` (API calls)
- `smtplib` (sending email)
- `datetime`
- `time`

---

## 📁 Project Structure

```
orbitwatch
│
├── main.py
├── .gitignore
└── README.md
```

---

## ⚙️ How the Program Works

The script runs in a loop and performs the following steps:

1. Retrieves the **current position of the ISS** using the ISS API.
2. Checks if the ISS is within **±5° latitude and longitude** of your location.
3. Retrieves **sunrise and sunset times** for your location.
4. Determines whether it is **currently nighttime**.
5. If both conditions are true, the program sends an **email notification**.

---

## 📍 Location Configuration

Your location is defined directly inside `main.py`.

Example:

```python
MY_LAT = 29.883274
MY_LONG = -97.941391
These coordinates correspond to:

San Marcos, Texas
```
---

## 📧 Email Configuration

To receive notifications, configure your email settings in config.py.

Example:

MY_EMAIL = "your_email@gmail.com"

MY_PASSWORD = "your_app_password"

For Gmail, you should create an `App Password` instead of using your normal password.

---

## 🧪 Installation

Clone the repository:
```
git clone https://github.com/YOUR_USERNAME/orbitwatch.git
```
Navigate into the project folder:
```
cd orbitwatch
```
Install required libraries:
```
pip install requests
```
Run the program:
```
python main.py
```
---
## ⏱ Program Behavior

The script continuously runs and checks every 60 seconds.
```
while True:
    time.sleep(60)
```

When the ISS is overhead and it is nighttime, you will receive an email like:
```
Subject: ISS Passing Overhead 🚀

The International Space Station is currently passing near your location.
Go outside and try spotting it in the night sky.
```
---

## 🔐 Security Note

Spotting the ISS in the night sky is exciting but timing it manually can be difficult.
This project automates the process by combining:

- real-time satellite tracking

- location-based calculations

- automated email alerts

So you never miss an ISS flyover.
