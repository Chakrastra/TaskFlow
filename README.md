# TaskFlow ✅

A simple, elegant **Task Manager** web application built with **Python Django**. Create, manage, and track your tasks with a beautiful dark glassmorphism UI.

🌐 **Live Demo**: [https://taskflow-mjgu.onrender.com](https://taskflow-mjgu.onrender.com)

---

## 📸 Features

- ✅ **Create Tasks** — Add tasks with a title and optional description
- 📋 **View All Tasks** — See all your tasks at a glance with status badges
- 🔍 **Task Detail View** — View full details of any task
- ✏️ **Edit Tasks** — Update title, description, or mark as completed
- 🗑️ **Delete Tasks** — Remove tasks with a confirmation step
- 🎨 **Premium Dark UI** — Glassmorphism design with smooth animations
- 🔐 **Django Admin Panel** — Manage everything from `/admin`

---

## 🛠️ Tech Stack

| Layer | Technology |
|:---|:---|
| Backend | Python 3.11, Django 5.2 |
| Database (local) | SQLite |
| Database (production) | PostgreSQL (Render) |
| Static Files | WhiteNoise |
| Web Server | Gunicorn |
| Hosting | Render |
| Frontend | HTML5, Vanilla CSS (Glassmorphism) |

---

## 🚀 Getting Started Locally

### 1. Clone the repository
```bash
git clone https://github.com/sohamrane10/TaskFlow.git
cd TaskFlow
```

### 2. Create and activate a virtual environment
```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run migrations
```bash
python manage.py migrate
```

### 5. Create an admin user
```bash
python manage.py createsuperuser
```

### 6. Start the development server
```bash
python manage.py runserver
```

Visit **[http://127.0.0.1:8000](http://127.0.0.1:8000)** in your browser.

---

## 🌐 Deployment (Render)

This project is production-ready and configured for deployment on [Render](https://render.com).

### Environment Variables required on Render:

| Variable | Description |
|:---|:---|
| `SECRET_KEY` | Django secret key (long random string) |
| `DEBUG` | Set to `False` in production |
| `ALLOWED_HOSTS` | Your Render domain e.g. `taskflow-mjgu.onrender.com` |
| `DATABASE_URL` | PostgreSQL connection URL (provided by Render) |
| `DJANGO_SUPERUSER_USERNAME` | Auto-created admin username |
| `DJANGO_SUPERUSER_EMAIL` | Admin email |
| `DJANGO_SUPERUSER_PASSWORD` | Admin password |

### Build Command:
```bash
pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate && python manage.py createsuperuser --noinput
```

### Start Command:
```bash
gunicorn task_manager.wsgi --log-file -
```

---

## 📁 Project Structure

```
TaskFlow/
│
├── manage.py               # Django entry point
├── requirements.txt        # Python dependencies
├── Procfile                # Render start command
├── runtime.txt             # Python version for Render
├── .gitignore              # Ignored files
│
├── task_manager/           # Django project configuration
│   ├── settings.py         # Production-ready settings
│   ├── urls.py             # Root URL routing
│   └── wsgi.py             # WSGI application
│
└── tasks/                  # Task Manager app
    ├── models.py           # Task data model
    ├── views.py            # CRUD views
    ├── forms.py            # Task form
    ├── urls.py             # App URL patterns
    ├── admin.py            # Admin panel config
    └── templates/tasks/    # HTML templates
        ├── base.html
        ├── task_list.html
        ├── task_detail.html
        ├── task_form.html
        └── task_confirm_delete.html
```

---

## 📝 Usage

| URL | Description |
|:---|:---|
| `/` | Task list (home page) |
| `/task/new/` | Create a new task |
| `/task/<id>/` | View task details |
| `/task/<id>/edit/` | Edit a task |
| `/task/<id>/delete/` | Delete a task |
| `/admin/` | Django admin panel |

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

Made with ❤️ using Python & Django
