# V2Ray VMESS Server & Client Setup

## 📋 توضیحات

این پوشه حاوی **سرور و کلاینت V2Ray** با پروتکل **VMESS** است.

### ⚙️ تنظیمات پیش‌فرض:
- **پورت سرور**: 10086
- **UUID**: `a3c8b9f7-2e1d-4a6c-9b5f-8e2c1a7d4b6f`
- **AlterID**: 64
- **پروتکل**: VMESS
- **پورت SOCKS کلاینت**: 1080
- **پورت HTTP کلاینت**: 1081

---

## 🚀 نصب و راه‌اندازی

### 1️⃣ پیش‌نیازها

- Docker و Docker Compose نصب شده باشند
- یا V2Ray مستقل نصب شده باشد

### 2️⃣ استفاده از Docker Compose

```bash
# راه‌اندازی سرور و کلاینت
docker-compose -f v2ray/docker-compose.yml up -d

# بررسی وضعیت
docker-compose -f v2ray/docker-compose.yml ps

# مشاهده لاگ‌ها
docker-compose -f v2ray/docker-compose.yml logs -f v2ray-server
docker-compose -f v2ray/docker-compose.yml logs -f v2ray-client
```

### 3️⃣ استفاده بدون Docker

#### سرور:
```bash
v2ray -c v2ray/server-config.json
```

#### کلاینت:
```bash
v2ray -c v2ray/client-config.json
```

---

## 🔧 تنظیمات کلاینت

### تغییر IP سرور

فایل `v2ray/client-config.json` را باز کنید و IP سرور را تغییر دهید:

```json
"vnext": [
  {
    "address": "YOUR_SERVER_IP",
    "port": 10086,
    ...
  }
]
```

### UUID تغییر‌شده

اگر UUID جدید می‌خواهید:

1. UUID جدید تولید کنید:
```bash
uuidgen
```

2. در هر دو فایل `v2ray/server-config.json` و `v2ray/client-config.json` تغییر دهید

---

## 📊 ساختار فایل‌ها

```
v2ray/
├── server-config.json      # تنظیمات سرور
├── client-config.json      # تنظیمات کلاینت
├── docker-compose.yml      # Docker Compose
├── .env.example            # متغیرهای محیطی
├── Dockerfile              # Docker برای سرور
└── README.md               # این فایل
```

---

## 🌐 اتصال بر روی Windows/Mac

### با Qv2ray:
1. Qv2ray را دانلود کنید
2. تنظیمات جدید ایجاد کنید
3. IP و پورت سرور را وارد کنید (10086)
4. UUID و AlterID را تغییر دهید

### با V2RayNG (اندروید):
1. اپ را دانلود کنید
2. سرور جدید اضافه کنید
3. اطلاعات سرور را وارد کنید

---

## 🛑 متوقف کردن

```bash
docker-compose -f v2ray/docker-compose.yml down
```

---

## 📝 لاگ‌ها

- **سرور Access**: `/var/log/v2ray/access.log`
- **سرور Errors**: `/var/log/v2ray/error.log`

---

## ⚠️ نکات امنیتی

1. ✅ UUID را تغییر دهید
2. ✅ AlterID را افزایش دهید
3. ✅ TLS را فعال کنید (اختیاری)
4. ✅ فایرفال را پیکربندی کنید
5. ✅ سرور را منظم بروزرسانی کنید

---

## 📞 راهنمایی بیشتر

- [V2Ray Official](https://www.v2fly.org/)
- [VMESS Protocol](https://www.v2fly.org/en/guide/protocols/vmess.html)

---

**ساخته شده با ❤️ برای IranGate**