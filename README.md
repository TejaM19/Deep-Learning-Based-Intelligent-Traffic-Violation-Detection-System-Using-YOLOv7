# Deep-Learning-Based Intelligent Traffic Violation Detection System Using YOLOv7

[![Python](https://img.shields.io/badge/python-3.8%20%7C%203.9%20%7C%203.10-blue.svg)](https://www.python.org/)
[![Django](https://img.shields.io/badge/django-4.2-green.svg)](https://www.djangoproject.com/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.8.0-orange.svg)](https://opencv.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An intelligent, computer-vision-driven traffic violation detection system built on top of Django and OpenCV. The system is designed to automate the process of detecting multiple common traffic violations, facilitating efficient enforcement and monitoring.

---

## 🚀 Key Features

The application supports four main modules for detecting traffic violations:

### 1. 🏎️ Overspeed Detection
- Tracks vehicles in real time using **Dlib correlation trackers**.
- Estimates vehicle speed based on frame rate and distance calibration.
- Identifies overspeeding vehicles based on set speed thresholds.
- Outputs annotated tracking logs.

### 2. 🪖 Helmet Detection
- Utilizes Haar Cascade classifiers to identify motorcycle riders and check for helmets.
- Features a clean GUI window using **Tkinter** to monitor and stream feed updates.

### 3. 🚦 Traffic Signal Jump Detection
- Monitors designated Regions of Interest (ROI).
- Analyzes signal states (Red, Yellow, Green) in the HSV color space using custom masks.
- Automatically flags vehicles that pass the stop line during a Red signal.

### 4. 👥 Triple Riding Detection
- Detects overloaded two-wheelers by identifying and counting faces/heads using Haar Cascade models.
- Flags violations if three or more riders are detected on a single vehicle.

---

## 🛠️ Technology Stack

- **Backend Framework:** Django (Python)
- **Computer Vision & Image Processing:** OpenCV, Dlib
- **Database:** MySQL
- **Frontend / UI:** HTML5, CSS3, JavaScript, Bootstrap
- **GUI Engine:** Tkinter & Pillow (PIL)

---

## 💻 Installation & Setup

### Prerequisites
Make sure you have the following installed on your local machine:
- Python 3.8+
- MySQL Server

### 1. Clone the Repository
```bash
git clone https://github.com/TejaM19/Deep-Learning-Based-Intelligent-Traffic-Violation-Detection-System-Using-YOLOv7.git
cd Deep-Learning-Based-Intelligent-Traffic-Violation-Detection-System-Using-YOLOv7
```

### 2. Set Up a Virtual Environment
```bash
python -m venv myvenv
source myvenv/bin/activate  # On Windows: myvenv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

> [!NOTE]
> Installing `dlib` requires C++ build tools installed on your system (e.g., Visual Studio Build Tools with C++ workload on Windows).

### 4. Configure the Database
Create a MySQL database named `traffic_db` (or as required by your settings).
Update the database connection settings in [settings.py](file:///c:/traffic%20detection%20code/trafficproject/settings.py):
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'traffic_db',
        'USER': 'your_mysql_user',
        'PASSWORD': 'your_mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 5. Run Migrations & Start Server
Run the migrations to create the database schemas and start the development server:
```bash
python manage.py migrate
python manage.py runserver
```

Open your browser and navigate to `http://127.0.0.1:8000/`.

---

## 📁 Project Structure

```
├── assets/                  # Frontend static files and templates
├── media/                   # Uploaded media (videos, processed frames)
├── trafficapp/              # Django app containing main business logic & views
│   ├── migrations/          # DB migration history
│   ├── models.py            # Violation databases/models
│   ├── views.py             # Computer vision core logic & view controllers
├── trafficproject/          # Project configurations (settings, routing)
├── requirements.txt         # Project dependencies
├── manage.py                # Django CLI entrypoint
└── LICENSE                  # MIT License
```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.