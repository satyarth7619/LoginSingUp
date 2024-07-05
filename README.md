# Django Login and Sign-up Page with Password Encryption - Setup

## Installation

### Prerequisites

- Python (3.x recommended)
- Django

### Clone the Repository

Clone the repository to your local machine:

```bash
git clone <repository_url>
cd <repository_name>
```

Create a Virtual Environment
Create a virtual environment for the project:
```bash
python -m venv env
```
### Step 3: Install Dependencies
Install Django and bcrypt:

```bash

pip install django bcrypt
```
### Step 4: Configure Django Settings

Configure your Django project settings (settings.py):
- Add 'django.contrib.auth' and 'django.contrib.sessions' to INSTALLED_APPS.
- Set up database settings (DATABASES).
### Step 5: Create Django Apps
Create Django apps for authentication and main functionality:

```bash

python manage.py startapp accounts
python manage.py startapp main
```
### Step 6: Implement Authentication Views
Create views, templates, and forms for login and sign-up:

- Login: accounts/views.py, accounts/templates/login.html, accounts/forms.py
- Sign-up: accounts/views.py, accounts/templates/signup.html, accounts/forms.py
### Step 7: Implement Password Encryption
Use bcrypt to hash passwords before saving:

```
# accounts/views.py
import bcrypt

def signup(request):
    if request.method == 'POST':
        password = request.POST['password'].encode('utf-8')
        hashed_password = bcrypt.hashpw(password, bcrypt.gensalt())
        # Save hashed_password to the database
```
### Step 8: Create URLs
Define URLs for login and sign-up pages:
```
main/urls.py and accounts/urls.py
```
### Step 9: Run Migrations
Apply migrations to create database tables:
```
python manage.py makemigrations
python manage.py migrate
```
### Step 10: Start the Django Development Server
Start the Django server and test your login and sign-up pages:
```
python manage.py runserver
Open your browser and go to http://localhost:8000/ to see the application.
```
