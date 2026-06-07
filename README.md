# AI-Powered Smart Agriculture System

Complete IoT + ML + Cloud Dashboard system for intelligent farming

## Run Locally on Windows

Use this path when running the project from this folder on your computer.

### Option 1: One command

Double-click `setup.bat`, or run it from PowerShell/CMD:

```bat
setup.bat
```

The script will:

- Create `.venv` if it does not exist.
- Install the Python packages from `backend\ml_model\requirements.txt`.
- Start XAMPP MySQL/MariaDB on port `3306`.
- Import `backend\api\database.sql` when the MySQL CLI is available.
- Start the PHP API/frontend server on `http://127.0.0.1:8080`.
- Start the ML/weather API on `http://127.0.0.1:5000`.
- Open the dashboard in your browser.

Use these optional flags when testing the script:

```bat
setup.bat --no-open --no-pause
```

### Option 2: Manual steps

1. Start MySQL/MariaDB from XAMPP Control Panel, or run:

```bat
C:\xampp\mysql\bin\mysqld.exe --defaults-file=C:\xampp\mysql\bin\my.ini --console
```

2. Import the database once:

```bat
C:\xampp\mysql\bin\mysql.exe -u root < backend\api\database.sql
```

If the command fails, open phpMyAdmin and import `backend\api\database.sql` manually.

3. Install Python dependencies:

```bat
python -m venv .venv
.venv\Scripts\python.exe -m pip install --upgrade pip setuptools wheel
.venv\Scripts\python.exe -m pip install -r backend\ml_model\requirements.txt
```

4. Start the ML/weather API:

```bat
.venv\Scripts\python.exe backend\ml_model\run_local_server.py
```

It should answer at:

```text
http://127.0.0.1:5000/api/health
```

5. Start the PHP frontend/API server:

```bat
C:\xampp\php\php.exe -S 127.0.0.1:8080 -t .
```

6. Open the dashboard:

```text
http://127.0.0.1:8080/
```

Default admin login:

```text
Email: admin@smartfarming.com
Password: admin123
```

Farmer signup is available on the same login page under `Create Account`. New farmer accounts are inserted into the `users` table with `role = user`, `is_active = true`, and `payment_status = pending`.

Important local URLs:

```text
Dashboard:      http://127.0.0.1:8080/
PHP API check:  http://127.0.0.1:8080/backend/api/auth.php?debug=check
ML API check:   http://127.0.0.1:5000/api/health
```

## Default Credentials

```
Admin Login:
- Email: admin@smartfarming.com
- Password: admin123

Note: Change these after first login!
```

## Features

### User Dashboard
- Real-time sensor monitoring
- AI-powered irrigation prediction
- Fertilizer recommendations
- Historical data & statistics
- Pump remote control
- Manual & automatic mode

### Admin Panel
- User management (activate/suspend)
- Payment status tracking
- System-wide statistics
- Farmer location mapping
- Admin action logs

### ML Models
- Lightweight irrigation predictor
- Lightweight fertilizer recommender
- Rainfall prediction using live weather inputs
- Real-time predictions via Flask API

### IoT System
- ESP32 sensor data collection
- WiFi connectivity
- REST API communication
- Automatic pump control

## License

MIT License - Feel free to use and modify

## Authors

AI-Powered Smart Agriculture System v1.0