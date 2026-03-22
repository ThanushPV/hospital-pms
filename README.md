# 🏥 MediCare — Hospital Patient Management System

A full-featured **Patient Management System** built with **Django** and **MongoDB**, featuring a clean medical-grade UI.

---

## 📸 Features

- ✅ **Patient Registration** — Full demographic, medical & emergency contact info
- ✅ **Patient Profiles** — Detailed view with photo support
- ✅ **Search & Filter** — By name, ID, phone, department, and status
- ✅ **Dashboard** — Live stats: total, active, critical, discharged + department breakdown
- ✅ **CRUD Operations** — Create, Read, Update, Delete patients
- ✅ **MongoDB Backend** — Via Djongo ODM
- ✅ **Django Admin** — Full admin panel support
- ✅ **Responsive UI** — Bootstrap 5 + custom teal medical theme

---

## 🗂️ Project Structure

```
hospital_pms/
├── hospital_pms/          # Django project config
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── patients/              # Main app
│   ├── models.py          # Patient model
│   ├── views.py           # All CRUD views
│   ├── forms.py           # PatientForm + Search
│   ├── urls.py            # App URL routes
│   └── admin.py           # Admin registration
├── templates/
│   ├── base.html          # Master layout (sidebar + topbar)
│   └── patients/
│       ├── dashboard.html
│       ├── patient_list.html
│       ├── patient_detail.html
│       ├── patient_form.html
│       └── patient_confirm_delete.html
├── static/                # CSS, JS, Images
├── docs/                  # Documentation
├── manage.py
├── requirements.txt
├── .env.example
└── .gitignore
```

---

## ⚙️ Setup & Installation

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/hospital-pms.git
cd hospital-pms
```

### 2. Create & Activate Virtual Environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables
```bash
cp .env.example .env
```
Edit `.env` and set:
```
SECRET_KEY=your-secret-django-key
DEBUG=True
MONGO_DB_NAME=hospital_pms
MONGO_URI=mongodb://localhost:27017/hospital_pms
```

> **MongoDB Atlas (Cloud):** Replace `MONGO_URI` with your Atlas connection string:
> `mongodb+srv://<user>:<pass>@cluster0.mongodb.net/hospital_pms`

### 5. Run Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create Superuser (for Admin Panel)
```bash
python manage.py createsuperuser
```

### 7. Run the Development Server
```bash
python manage.py runserver
```

Open → [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 🗄️ MongoDB Collections

| Collection         | Description                      |
|--------------------|----------------------------------|
| `patients_patient` | All patient records              |
| `auth_user`        | Django admin users               |

---

## 🔗 URL Routes

| URL                         | View              | Description           |
|-----------------------------|-------------------|-----------------------|
| `/`                         | dashboard         | Stats overview        |
| `/patients/`                | patient_list      | All patients + search |
| `/patients/new/`            | patient_create    | Register new patient  |
| `/patients/<id>/`           | patient_detail    | Patient profile       |
| `/patients/<id>/edit/`      | patient_update    | Edit patient          |
| `/patients/<id>/delete/`    | patient_delete    | Delete patient        |
| `/admin/`                   | Django Admin      | Admin panel           |

---

## 🛠️ Tech Stack

| Layer      | Technology          |
|------------|---------------------|
| Backend    | Django 4.2          |
| Database   | MongoDB (via Djongo) |
| Frontend   | Bootstrap 5 + Custom CSS |
| ORM        | Djongo ODM          |
| Auth       | Django built-in     |

---

## 📤 Deploying to GitHub

```bash
git init
git add .
git commit -m "Initial commit: Hospital Patient Management System"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/hospital-pms.git
git push -u origin main
```

---

## 📄 License

MIT License — Free to use and modify.

---

> Built with ❤️ using Django + MongoDB
