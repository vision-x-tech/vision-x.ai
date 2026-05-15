# Deployment Guide - نشر تلقائي من GitHub

## 🚀 نظرة عامة

تم إعداد **نشر تلقائي كامل** باستخدام:
- **GitHub** - مستودع الكود
- **Vercel** - منصة النشر
- **GitHub Actions** - التشغيل التلقائي

---

## 📋 المتطلبات

- ✅ حساب GitHub (لديك بالفعل)
- ✅ حساب Vercel مجاني
- ✅ حساب Supabase (اختياري)

---

## ⚙️ خطوات الإعداد

### 1️⃣ **إنشاء حساب Vercel**

```
اذهب إلى: https://vercel.com
اضغط "Sign Up"
اختر "Continue with GitHub"
وافق على التصاريح
```

### 2️⃣ **الحصول على VERCEL_TOKEN**

```
Vercel → Settings → Tokens
اضغط "Create Token"
اسمه: "GitHub Actions"
النوع: "Full Access"
انسخ الـ Token
```

### 3️⃣ **الحصول على VERCEL_ORG_ID و VERCEL_PROJECT_ID**

```
أنشئ مشروع جديد في Vercel
اضغط "Import Git Repository"
اختر: vision-x-tech/vision-x.ai
سيحصل على المعرّفات تلقائياً
```

أو استخدم الأوامر:

```bash
npm install -g vercel
vercel login
vercel link
vercel env pull
```

### 4️⃣ **إضافة Secrets إلى GitHub**

في مستودعك:

```
Settings → Secrets and variables → Actions
```

أضف 3 Secrets:

```
VERCEL_TOKEN = (من الخطوة 2)
VERCEL_ORG_ID = (من الخطوة 3)
VERCEL_PROJECT_ID = (من الخطوة 3)
```

### 5️⃣ **إضافة متغيرات البيئة (اختياري)**

```
VITE_SUPABASE_URL
VITE_SUPABASE_KEY
```

---

## 🎯 كيفية النشر

### **النشر إلى الإنتاج** (Production) 🌍

```bash
# 1. قم بالتعديلات
# 2. اعمل Commit
git add .
git commit -m "Update features"

# 3. اعمل Push إلى main
git push origin main

# 4. سيتم النشر تلقائياً!
```

### **معاينة قبل النشر** 👁️ (Preview)

```bash
# 1. أنشئ فرع جديد
git checkout -b feature/new-feature

# 2. قم بالتعديلات
# 3. اعمل Commit و Push
git push origin feature/new-feature

# 4. أنشئ Pull Request على GitHub
# 5. سيتم إنشاء رابط preview تلقائياً
```

---

## 📊 مراقبة النشر

### **في GitHub:**

```
Actions → Deploy to Vercel
```

ستشاهد:
- ✅ Status: Install Dependencies
- ✅ Status: Build project
- ✅ Status: Deploy to Vercel

### **في Vercel:**

```
Dashboard → Projects → vision-x-tech-ai → Deployments
```

ستشاهد:
- ✅ Production (الحالي)
- ✅ Preview (للـ PR)
- ✅ السرعة والحجم

---

## 🔐 متغيرات البيئة

### **في Vercel Dashboard:**

```
Settings → Environment Variables
```

أضف:

```
VITE_SUPABASE_URL = https://your-project.supabase.co
VITE_SUPABASE_KEY = your-anon-key
VITE_API_URL = https://your-api.com
VITE_ENVIRONMENT = production
```

---

## ✅ قائمة التحقق

- [ ] حساب Vercel أنشأ
- [ ] VERCEL_TOKEN نسخ
- [ ] Secrets في GitHub أضيفت
- [ ] GitHub Actions Workflow يعمل
- [ ] أول Build نجح
- [ ] الموقع يعمل بـ HTTPS
- [ ] Domain مخصص أضيف (اختياري)

---

## 🆘 استكشاف الأخطاء

### **Build فشل:**

```
اذهب إلى: GitHub → Actions → الـ Workflow الأخير
اقرأ الخطأ في "Build project"
تأكد من: pnpm install و pnpm build تعمل محلياً
```

### **متغيرات البيئة ناقصة:**

```
تأكد من Secrets موجودة في GitHub
وفي Vercel Environment Variables
```

### **الموقع بطيء:**

```
تحقق من: Vercel Dashboard → Analytics
استخدم: Vercel Edge Functions إذا لزم
```

---

## 🎓 الأوامر المفيدة

```bash
# اختبر محلياً قبل النشر
pnpm dev

# بناء الإنتاج
pnpm build

# معاينة البناء
pnpm preview

# تحديث المتطلبات
pnpm update

# فحص الأخطاء
pnpm lint
```

---

## 📞 الدعم

- **Vercel Docs:** https://vercel.com/docs
- **GitHub Actions:** https://docs.github.com/actions
- **Vite Guide:** https://vitejs.dev/guide/

---

## 🎉 النتيجة النهائية

بعد الإعداد:

✅ **كل Push إلى main → نشر تلقائي على Vercel**  
✅ **كل PR → معاينة مؤقتة**  
✅ **SSL مجاني**  
✅ **CDN عالمي**  
✅ **Rollback سهل**  
✅ **بدون تكاليف**

---

**تم الإعداد بواسطة:** GitHub Copilot  
**التاريخ:** 2026-05-15  
**الحالة:** جاهز للاستخدام ✅
