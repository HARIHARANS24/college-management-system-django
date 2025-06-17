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
