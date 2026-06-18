# 🧡 Monklingo — Monk Alms Offering Route Tracker

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Django-4.x-092E20?style=flat-square&logo=django&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tailwind_CSS-3.x-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white"/>
  <img src="https://img.shields.io/badge/Leaflet.js-1.x-199900?style=flat-square&logo=leaflet&logoColor=white"/>
  <img src="https://img.shields.io/badge/PostgreSQL-16-336791?style=flat-square&logo=postgresql&logoColor=white"/>
</p>

<p align="center">
  แพลตฟอร์มแสดงเส้นทางและตารางเวลาการตักบาตรของพระสงฆ์แบบ Real-time<br/>
  ช่วยให้ชาวบ้านสามารถมีส่วนร่วมในวัฒนธรรมท้องถิ่นได้ง่ายขึ้น
</p>

---

## 📖 About

**Monklingo** เป็นเว็บแอปพลิเคชันที่พัฒนาขึ้นเพื่อเชื่อมโยงชุมชนเข้ากับประเพณีการตักบาตร โดยแสดงเส้นทางเดินบิณฑบาตของพระสงฆ์บนแผนที่แบบ Interactive พร้อมระบบ Community ที่ช่วยให้ผู้ใช้สามารถติดตาม แชร์ และมีส่วนร่วมกับวัฒนธรรมพุทธศาสนาได้อย่างใกล้ชิด

> 🏆 **NSC 2025 First Round Selection** — 27th National Software Contest  
> 🎖️ **Good-Level Award** — SCI-TECH Symposium 2025, Ubon Ratchathani University

---

## ✨ Features

### 🗺️ Route Map
- แสดงเส้นทางตักบาตรของพระสงฆ์บนแผนที่ Interactive ด้วย **Leaflet.js**
- เลือกดูเส้นทางแยกตามวัด
- แสดง waypoints และข้อมูลจุดสำคัญบนเส้นทาง

### 👤 Authentication
- ลงทะเบียน / เข้าสู่ระบบด้วยบัญชีปกติ
- Social Login ผ่าน **Facebook** และ **Google** (OAuth)

### 🏅 Ranking & Community
- ระบบ Ranking ผู้ใช้ที่ตักบาตรสะสม
- แชร์ผลการตักบาตรไปยัง Facebook โดยตรง
- ห้องแชทแยกตามวัด

### 📰 News & Prayers
- ข่าวสารและประกาศจากวัดต่างๆ
- รวบรวมบทสวดมนต์สำหรับผู้ปฏิบัติ

### 🛠️ Admin Panel
- จัดการเส้นทาง: เพิ่ม / แก้ไข / ลบ waypoints
- จัดการผู้ใช้และสิทธิ์การเข้าถึง
- Dashboard แสดงสถิติการใช้งานรายเดือน
- จัดการข่าวสาร, บทสวด และห้องแชท

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | HTML, Tailwind CSS, JavaScript, Leaflet.js |
| **Backend** | Python 3.11, Django 4.x |
| **Database** | PostgreSQL |
| **Auth** | Django Allauth (Facebook & Google OAuth) |
| **Maps** | Leaflet.js + OpenStreetMap |
| **Tunnel (Dev)** | ngrok |

### System Architecture

```
CLIENT (Browser)
    │
    ▼
 ngrok (external access)
    │
    ▼
Django Backend ──── DATABASE QUERIES ───► PostgreSQL
    │
    ▼
Leaflet.js (get routes & show map)
    │
    ▼
Facebook / Google (share result & OAuth)
```

---

## 🚀 Getting Started

### Prerequisites

- Python **3.11**
- PostgreSQL
- ngrok (optional, for external access)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/jarkapatto/Monklingo.git
cd Monklingo/Sur/endproject

# 2. Create virtual environment
python3.11 -m venv venv
source venv/bin/activate       # macOS/Linux
# venv\Scripts\activate        # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Setup environment variables
cp .env.example .env
# Edit .env with your database credentials and OAuth keys
```

### Database Setup

```bash
# Create PostgreSQL database
createdb monklingo_db

# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser
```

### Run the Development Server

```bash
python manage.py runserver
```

Visit `http://localhost:8000`

### (Optional) External Access via ngrok

```bash
ngrok http 8000
```

---

## ⚙️ Environment Variables

Create a `.env` file in the project root:

```env
SECRET_KEY=your-django-secret-key

# Database
DB_NAME=monklingo_db
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432

# Google OAuth
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

# Facebook OAuth
FACEBOOK_APP_ID=your-facebook-app-id
FACEBOOK_APP_SECRET=your-facebook-app-secret

DEBUG=True
```

---

## 📁 Project Structure

```
Monklingo/
└── Sur/
    └── endproject/
        ├── manage.py
        ├── requirements.txt
        ├── config/              # Django settings & URLs
        ├── accounts/            # Auth, user profiles, ranking
        ├── routes/              # Map routes & waypoints
        ├── community/           # News, prayers, chat rooms
        ├── dashboard/           # Admin dashboard & stats
        └── templates/           # HTML templates
            └── static/          # CSS, JS, images
```

---

## 📸 Screenshots

| Route Map | Login | Dashboard |
|---|---|---|
| ![map](./screenshots/map.png) | ![login](./screenshots/login.png) | ![dashboard](./screenshots/dashboard.png) |

---

## 🏆 Awards

| Award | Event |
|---|---|
| 🏆 First Round Selection | 27th National Software Contest (NSC 2025) |
| 🎖️ Good-Level Award | SCI-TECH Symposium 2025, Faculty of Science, Ubon Ratchathani University |

---

## 👨‍💻 Author

**Jarkapat Tongla (Teem)**  
Software Engineer · Data Science & Software Innovation  
Ubon Ratchathani University

- Portfolio: [jarkapatto.github.io](https://jarkapatto.github.io)
- GitHub: [@jarkapatto](https://github.com/jarkapatto)
- Email: jarkapat.to@gmail.com

---

## 📄 License

This project is for educational and portfolio purposes.
