# 🚀 Vitorrio Web Server

یک **Web Server Express.js** آماده و کامل برای پروژه Vitorrio.

## ⚙️ ویژگی‌ها

- ✅ Express.js Framework
- ✅ CORS فعال
- ✅ Security Headers (Helmet)
- ✅ Request Logging (Morgan)
- ✅ Error Handling
- ✅ Docker Support
- ✅ Health Check
- ✅ Static Files Serving
- ✅ REST API Ready

---

## 📋 نیازمندی‌ها

### بدون Docker:
- Node.js >= 14
- npm یا yarn

### با Docker:
- Docker
- Docker Compose

---

## 🚀 شروع سریع

### 1️⃣ بدون Docker

```bash
# رفتن به دایرکتوری
cd vitorrio-server

# نصب Dependencies
npm install

# ایجاد .env فایل
cp .env.example .env

# اجرای Server
npm start

# یا برای Development
npm run dev
```

### 2️⃣ با Docker

```bash
# بیلد کردن Image
docker build -t vitorrio-server .

# اجرای Container
docker run -p 3000:3000 vitorrio-server

# یا با Docker Compose
docker-compose up -d
```

---

## 📡 API Endpoints

### 1. Root Endpoint
```bash
GET /
```
**Response:**
```json
{
  "status": "success",
  "message": "Welcome to Vitorrio Web Server",
  "version": "1.0.0",
  "timestamp": "2026-06-07T12:34:56.789Z"
}
```

### 2. Health Check
```bash
GET /api/health
```
**Response:**
```json
{
  "status": "healthy",
  "uptime": 1234.567,
  "timestamp": "2026-06-07T12:34:56.789Z"
}
```

### 3. Server Info
```bash
GET /api/info
```
**Response:**
```json
{
  "name": "Vitorrio Server",
  "version": "1.0.0",
  "environment": "production",
  "nodeVersion": "v18.0.0"
}
```

### 4. Send Message (POST)
```bash
POST /api/message
Content-Type: application/json

{
  "message": "Hello Vitorrio"
}
```
**Response:**
```json
{
  "status": "success",
  "receivedMessage": "Hello Vitorrio",
  "timestamp": "2026-06-07T12:34:56.789Z"
}
```

---

## 🔧 تنظیمات محیطی

فایل `.env` را تنظیم کنید:

```env
# Server Configuration
NODE_ENV=development
PORT=3000
HOST=localhost

# API Configuration
API_BASE_URL=http://localhost:3000

# Logging
LOG_LEVEL=debug

# CORS
CORS_ORIGIN=*

# Security
SECURE_HEADERS=true
```

---

## 📁 ساختار پروژه

```
vitorrio-server/
├── server.js              # Main server file
├── package.json           # Dependencies
├── Dockerfile            # Docker configuration
├── docker-compose.yml    # Docker Compose
├── .env.example          # Environment template
├── .gitignore           # Git ignore
├── public/              # Static files
│   └── index.html       # Web UI
└── README.md            # This file
```

---

## 🧪 تست کردن

### با curl:
```bash
# GET Request
curl http://localhost:3000/

# Health Check
curl http://localhost:3000/api/health

# POST Request
curl -X POST http://localhost:3000/api/message \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello"}'
```

### با Postman:
1. Collection جدید بسازید
2. Requests اضافه کنید:
   - `GET http://localhost:3000/`
   - `GET http://localhost:3000/api/health`
   - `GET http://localhost:3000/api/info`
   - `POST http://localhost:3000/api/message`

---

## 🐳 Docker Compose Commands

```bash
# شروع Server
docker-compose up -d

# مشاهده logs
docker-compose logs -f vitorrio-server

# توقف Server
docker-compose down

# حذف Volume
docker-compose down -v
```

---

## ⚠️ نکات امنیتی

✅ Helmet.js برای Security Headers
✅ CORS Configuration
✅ Input Validation
✅ Error Handling
✅ Environment Variables

---

## 📊 مشاهده وب UI

به این آدرس برروید:
```
http://localhost:3000
```

یک Dashboard زیبا و کامل دیده می‌شود! 🎨

---

## 🚀 Deploy کردن

### Heroku:
```bash
heroku login
heroku create vitorrio-server
git push heroku main
```

### AWS/GCP:
فایل‌های Docker را استفاده کنید

---

## 📝 لاگ‌ها

تمام requests و events لاگ می‌شوند:
```
[morgan] GET / 200 - 2.345 ms
[morgan] GET /api/health 200 - 1.234 ms
```

---

## 🆘 خطا‌گیری

### Port در حال استفاده است:
```bash
# تغییر PORT در .env
PORT=3001
```

### Module نیافت شد:
```bash
npm install
```

### Docker Connection Error:
```bash
docker-compose down
docker-compose up --build
```

---

## 📞 دریافت کمک

اگر سوالی دارید:
1. README را دوباره بخوانید
2. Issues را بررسی کنید
3. Log‌ها را چک کنید

---

## 📜 License

MIT License - Feel free to use!

---

**ساخته شده با ❤️ برای Vitorrio**

🚀 Happy Coding!
