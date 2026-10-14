# 🐳 راه‌اندازی Docker Registry Mirror با ابر آروان

> دسترسی سریع به ایمیج‌های داکر بدون تحریم

---

## ⚡ روش ۱: راه‌اندازی Mirror (پیشنهادی)

**۱. افزودن Mirror به داکر:**

```bash
sudo bash -c 'cat > /etc/docker/daemon.json <<EOF
{
  "insecure-registries" : ["https://docker.arvancloud.ir"],
  "registry-mirrors": ["https://docker.arvancloud.ir"]
}
EOF'
```

**۲. اعمال تغییرات:**

```bash
docker logout
sudo systemctl restart docker
```

**۳. دریافت ایمیج:**

```bash
docker pull <ImageName>
```

---

## 🚀 روش ۲: استفاده مستقیم (بدون تغییر تنظیمات)

```bash
docker pull docker.arvancloud.ir/<ImageName>
```

---

## 🧪 تست

```bash
docker info
```

باید در بخش `Registry Mirrors` ببینید:
```
https://docker.arvancloud.ir
```

---

## 📝 نکته

- `<ImageName>` = نام ایمیج موردنظر
- **Mirror** = آینه‌ی رجیستری داکر (کپی محلی از Docker Hub)
