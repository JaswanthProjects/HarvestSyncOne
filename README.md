# Farmer Management System 🌾

A web-based Farmer Management System built with **Flask** and **MySQL (MariaDB)**, designed to manage farmer registrations, agricultural products, and farming types. The system includes authentication, CRUD operations, and triggers to track database changes.

## 📝 Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Folder Structure](#folder-structure)
- [Database Schema](#database-schema)
- [Dependencies](#dependencies)
- [License](#license)

---

## ✨ Features
- Farmer Registration with CRUD operations.
- Product Management (Add, View Agricultural Products).
- Farming Types Management.
- User Authentication (Signup, Login, Logout).
- Database Triggers to monitor data changes (Insert, Update, Delete).
- Flash messages for user feedback.

---

## 🛠 Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/farmer-management-system.git
   cd farmer-management-system
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the MySQL (MariaDB) Database (via XAMPP/Apache):**
   - Start **Apache** and **MySQL** using XAMPP or your preferred local server.
   - Open **phpMyAdmin**: `http://localhost/phpmyadmin/`
   - Create a new database called `farmers`.
   - Import the `farmers.sql` file into the `farmers` database.

5. **Update database connection in `main.py`:**
   ```python
   app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://root:@localhost/farmers'
   ```

6. **Run the Flask application:**
   ```bash
   python main.py
   ```

7. **Open the application in your browser:**
   ```
   http://127.0.0.1:5000/
   ```

---

## ▶️ Usage
- Visit `/signup` to create an account.
- Visit `/login` to log in.
- Navigate through the dashboard to manage farmers, products, and farming types.

---

## 📂 Folder Structure
```
.
│
├── main.py                  # Flask Application Code
├── requirements.txt          # Dependencies
│
├── templates/                # HTML Templates
│   └── (about.html, index.html, signup.html, login.html, etc.)
│
├── static/
│   └── assets/
│       ├── css/              # Stylesheets
│       ├── js/               # JavaScript Files
│       └── vendor/           # External Libraries (Bootstrap, jQuery, etc.)
```

---

## 🗄 Database Schema

The project consists of the following tables:

| Table Name         | Description                                      |
|--------------------|--------------------------------------------------|
| `register`         | Stores farmer details                            |
| `addagroproducts`  | Stores agricultural products                     |
| `farming`          | Stores farming types                             |
| `user`             | Stores user credentials                          |
| `trig`             | Logs database actions (INSERT, DELETE, UPDATE)   |
| `test`             | Test table for connection testing                |

### 🌀 Triggers:
The `register` table has the following triggers:
- **Insertion Trigger**: Logs when a new farmer is registered.
- **Update Trigger**: Logs when a farmer's details are updated.
- **Deletion Trigger**: Logs when a farmer's record is deleted.

---

## 📦 Dependencies
- Flask==1.1.2
- Flask-SQLAlchemy
- Flask-Login
- Werkzeug
- MySQL (MariaDB) – via XAMPP (or any local server)

Install all using:
```bash
pip install -r requirements.txt
```

---

## 📝 License
This project is open-source and available under the [MIT License](LICENSE).
