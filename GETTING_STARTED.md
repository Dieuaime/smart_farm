# AI-Powered Smart Agriculture System - Getting Started

## Quick Start (5 minutes)

### 1. Database Setup
```bash
# Import database schema
mysql -u root -p
mysql> CREATE DATABASE smart_farming;
mysql> USE smart_farming;
mysql> source backend/api/database.sql;
```

### 2. Backend API
```bash
# Copy to web server (Apache/Nginx)
cp -r backend/api/* /var/www/html/api/

# Test: http://localhost/api/
```

### 3. ML Model
```bash
# Install dependencies
pip install -r backend/ml_model/requirements.txt

# Train models
python backend/ml_model/train_models.py

# Start server
python backend/ml_model/app.py
# Runs on http://localhost:5000
```

### 4. Frontend
```bash
# Option 1: Static hosting
# Upload frontend/ to any web hosting

# Option 2: Local testing
cd frontend
python -m http.server 8000
# Open http://localhost:8000
```

### 5. ESP32
```
1. Open esp32/esp32_main.ino in Arduino IDE
2. Update WiFi credentials:
   const char* ssid = "YOUR_WIFI";
   const char* password = "YOUR_PASSWORD";
3. Update server IP:
   const char* serverName = "http://192.168.X.X/api/sensors.php";
4. Update user ID:
   const int USER_ID = 1;
5. Upload to ESP32
```

## 📱 Default Login
```
Username: admin
Email: admin@smartfarming.com
Password: admin123

⚠️ Change this immediately in production!
```

## 🔐 Security Checklist

- [ ] Change default admin password
- [ ] Use HTTPS in production
- [ ] Enable database backups
- [ ] Implement API rate limiting
- [ ] Use environment variables for secrets
- [ ] Enable CSRF protection
- [ ] Validate all inputs
- [ ] Use prepared statements (already done)
- [ ] Implement access logging
- [ ] Regular security updates

---

**Need help?** See README.md for detailed documentation.