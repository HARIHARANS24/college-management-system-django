# 🎓 College Management System (Django)

A simple yet powerful **College Management System** built with Django for educational and administrative purposes. This project helps **admins**, **teachers**, and **students** manage and access essential academic tasks efficiently through a web-based interface.

---

## 🚀 Features

### 🛠 Admin Panel
- 📊 View dashboard summary of student & staff performance.
- 👨‍🏫 Manage **Staffs** (Add, Update, Delete).
- 👨‍🎓 Manage **Students** (Add, Update, Delete).
- 📚 Manage **Courses** and **Subjects**.
- 📅 Manage **Sessions** (Academic Years).
- 📌 View and manage **Student Attendance**.
- 💬 Review and reply to **Feedback** from staff and students.
- 📝 Approve/Reject **Leave Applications**.
- ⚙️ Update **Admin Profile**.
- 🔐 Secure **Login/Logout** functionality.

### 👩‍🏫 Staff/Teachers Dashboard
- 📊 Summary view of own subjects, student attendance, etc.
- 🧾 Take and update **Student Attendance**.
- 🧮 Add and update **Student Results**.
- 📝 Apply for **Leave**.
- 💬 Send **Feedback** to Admin/HOD.
- ⚙️ Update **Profile**.
- 🔐 Secure **Login/Logout**.

### 👨‍🎓 Student Dashboard
- 📊 Summary view of own attendance, subjects, results, and leaves.
- 📌 View **Attendance Records**.
- 📈 View **Academic Results**.
- 📝 Apply for **Leave**.
- 💬 Send **Feedback** to Admin/HOD.
- ⚙️ Update **Profile**.
- 🔐 Secure **Login/Logout**.

---

## 🧰 Tech Stack

- **Backend:** Django (Python)
- **Frontend:** HTML, CSS, JavaScript, Bootstrap, Owl Carousel
- **Client-side:** jQuery, AJAX
- **Database:** SQLite (default, can be swapped with PostgreSQL/MySQL)

---

## 🖥️ Getting Started

### Prerequisites
- Python 3.x
- pip (Python package installer)
- Git (optional but recommended)
- Virtualenv (for managing project environment)

### 🔧 Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/HARIHARANS24/college-management-system-django.git
   cd college-management-system-django
   
## 📁 Project Structure

```plaintext
COLLEGE_MANAGEMENT_SYSTEM/
│
├── static/                             # Global static files (if any)
│
├── student_management_app/            # Main Django App
│   ├── __pycache__/                    # Compiled Python files
│   ├── migrations/                     # Database migrations
│   ├── static/                         # App-specific static files
│   ├── templates/                      # HTML templates
│   ├── __init__.py
│   ├── admin.py                        # Admin site configurations
│   ├── apps.py                         # App config
│   ├── EmailBackEnd.py                 # Custom email backend logic
│   ├── forms.py                        # Django forms
│   ├── HodViews.py                     # Views for HOD/Admin
│   ├── StaffViews.py                   # Views for Staff
│   ├── StudentViews.py                 # Views for Students
│   ├── models.py                       # Database models
│   ├── tests.py                        # Test cases
│   ├── urls.py                         # App-level URLs
│   ├── utils.py                        # Utility functions
│   └── views.py                        # Generic/common views
│
├── student_management_project/        # Django Project Settings
│   ├── __pycache__/
│   ├── __init__.py
│   ├── asgi.py                         # ASGI config
│   ├── settings.py                     # Project settings
│   ├── urls.py                         # Project-level URL routing
│   └── wsgi.py                         # WSGI config
│
├── db.sqlite3                          # SQLite database file
├── manage.py                           # Django management utility
├── README.md                           # Project documentation
└── requirements.txt                    # Python dependencies
```
# ✅ College Management System – Setup Guide

---

## ✅ 1. Initial Project Setup

### 🔹 Step 1: Install Python & Virtual Environment

```bash
python --version          # Python 3.10+ recommended
pip install virtualenv
```

### 🔹 Step 2: Create & Activate Virtual Environment

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

---

## ✅ 2. Install Django & Dependencies

```bash
pip install django
pip install pillow          # For file uploads (profile_pic etc.)
# Optionally save dependencies
pip freeze > requirements.txt
```

---

## ✅ 3. Start the Project & App

> If not already done:

```bash
django-admin startproject college_project
cd college_project
python manage.py startapp student_management_app
```

---

## ✅ 4. Apply Migrations & Create DB

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## ✅ 5. Create Superuser (for admin panel)

```bash
python manage.py createsuperuser
# Provide username, email, password when prompted
```

---

## ✅ 6. Run the Development Server

```bash
python manage.py runserver
```

- Access site: [http://127.0.0.1:8000](http://127.0.0.1:8000)  
- Admin Panel: [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)

---

## ✅ 7. Register Users in Django Shell

```bash
python manage.py shell
```

Then in the shell:

```python
from student_management_app.models import CustomUser, Students, Courses, SessionYearModel

# Create Staff
staff = CustomUser.objects.create_user(
    username='priya',
    email='priya.staff@xyzcollege.edu',
    password='Staff@2025',
    first_name='Priya',
    last_name='Sharma',
    user_type=CustomUser.STAFF
)

# Create HOD
hod = CustomUser.objects.create_user(
    username='neeraj',
    email='neeraj.hod@xyzcollege.edu',
    password='Hod@2025',
    first_name='Neeraj',
    last_name='Mehta',
    user_type=CustomUser.HOD
)

# Create Student
student = CustomUser.objects.create_user(
    username='rahul',
    email='rahul.student@xyzcollege.edu',
    password='Student@2025',
    first_name='Rahul',
    last_name='Verma',
    user_type=CustomUser.STUDENT
)

# Student extra info (only if signals don't handle it)
Students.objects.create(
    admin=student,
    gender="Male",
    profile_pic="",
    address="Hostel",
    course_id=Courses.objects.get(id=1),
    session_year_id=SessionYearModel.objects.get(id=1)
)
```

> 🔸 Make sure `Courses` and `SessionYearModel` have valid records  
> (insert them from the admin panel or use the commands below).

---

## ✅ 8. Optional Commands

### 🔹 Create Course

```python
from student_management_app.models import Courses
Courses.objects.create(course_name='B.Tech')
```

### 🔹 Create Session Year

```python
from student_management_app.models import SessionYearModel
from datetime import date
SessionYearModel.objects.create(
    session_start_year=date(2023,6,1),
    session_end_year=date(2024,5,31)
)
```

---

## ✅ 9. Recommended Folder Settings

### In `settings.py`:

```python
INSTALLED_APPS = [
    ...
    'student_management_app',
]

MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

### In `urls.py`:

```python
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    ...
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

---

## 🧪 Testing

Open in browser: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

Login Credentials:

```plaintext
Staff Login:
Email: priya.staff@xyzcollege.edu
Password: Staff@2025

Student Login:
Email: rahul.student@xyzcollege.edu
Password: Student@2025

Admin (HOD) Login:
Email: neeraj.hod@xyzcollege.edu
Password: Hod@2025
```

