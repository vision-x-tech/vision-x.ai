# 🚀 Vision-X.ai - Setup Guide

## ✅ تم إعداد النشر التلقائي بنجاح!

جميع الملفات اللازمة تم إنشاؤها وجاهزة للعمل.

---

## 📋 الملفات المُنشأة:

```
✅ vercel.json                     تكوين Vercel
✅ .github/workflows/deploy.yml    GitHub Actions
✅ .env.example                    مثال المتغيرات
✅ .gitignore                      تجاهل الملفات
✅ DEPLOYMENT.md                   دليل النشر
```

---

## 🚀 البدء السريع (5 دقائق)

### 1️⃣ **أنشئ حساب Vercel**
```
https://vercel.com
Sign Up with GitHub
```

### 2️⃣ **احصل على GitHub Secrets**

```bash
# الخيار 1: من لوحة Vercel
https://vercel.com/account/tokens

# الخيار 2: من CLI
npm install -g vercel
vercel login
vercel link
```

### 3️⃣ **أضف Secrets إلى GitHub**

```
Settings → Secrets and variables → Actions
```

أضف 3 secrets:
- `VERCEL_TOKEN` - من Vercel
- `VERCEL_ORG_ID` - معرّف الحساب
- `VERCEL_PROJECT_ID` - معرّف المشروع

### 4️⃣ **اعمل Push**

```bash
git add .
git commit -m "Setup automatic deployment"
git push origin main
```

---

## 🎯 النشر

### **Production (الإنتاج)** 🌍
```bash
git push origin main
```

### **Preview (معاينة)** 👁️
```bash
git push origin feature-branch
# ثم أنشئ Pull Request
```

---

## ✨ المميزات

- ✅ نشر تلقائي مع كل push
- ✅ معاينة مؤقتة للـ PR
- ✅ SSL مجاني
- ✅ CDN عالمي
- ✅ Rollback سهل
- ✅ بدون تكاليف

---

## 📞 الدعم

اقرأ `DEPLOYMENT.md` للمزيد من التفاصيل.
