# تعليمات إعداد PromoHive للادمن والمالك

## ✅ ما تم إنجازه حتى الآن
1. ✅ جميع الصفحات والتطبيق جاهز
2. ✅ النماذج متجاوبة ومرئية
3. ✅ العجلة الحظ تعمل بشكل مثالي
4. ✅ نظام الإشعارات والإحالات جاهز
5. ✅ لوحة الأدمن كاملة وجاهزة
6. ✅ تم رفع المشروع على GitHub: https://github.com/nyttynt96-art/1.git

---

## 📋 ما يجب على المالك/الادمن فعله

### 1. إنشاء ملف `.env` (مهم جداً!)

قم بإنشاء ملف `.env` في المجلد الرئيسي للمشروع:

```bash
# في المجلد C:\Users\SANND\Desktop\promohive
# انسخ محتوى ملف env.supabase
cp env.supabase .env
```

### 2. تحديث كلمة مرور قاعدة البيانات

افتح ملف `.env` وعدّل هذه السطر:

```env
DATABASE_URL="postgresql://postgres:PASSWORD@db.jxtutquvxmkrajfvdbab.supabase.co:5432/postgres"
```

استبدل `PASSWORD` بكلمة مرور قاعدة البيانات الفعلية من حساب Supabase.

### 3. تحديث كلمة مرور البريد الإلكتروني

في ملف `.env`، ابحث عن:

```env
SMTP_PASS="your-password"
```

استبدل `your-password` بكلمة مرور صندوق البريد الخاص بـ Hostinger.

---

## 🗄️ إنشاء الجداول في Supabase

### الخطوات:

1. **اذهب إلى Supabase Dashboard**
   - الرابط: https://supabase.com/dashboard/project/jxtutquvxmkrajfvdbab/editor

2. **افتح SQL Editor**
   - من القائمة الجانبية، اختر "SQL Editor"
   - ثم اضغط "New query"

3. **الصق كامل محتوى ملف `supabase-setup-complete.sql`**
   - افتح الملف `supabase-setup-complete.sql` من المشروع
   - انسخ كامل المحتوى
   - الصق في SQL Editor

4. **نفذ الاستعلام**
   - اضغط زر "RUN" (أو F5)
   - انتظر حتى يظهر "Success"

### النتيجة المتوقعة:

✅ سيتم إنشاء:
- 14 جدول (User, Wallet, Task, Transaction, إلخ)
- جميع الفهارس (Indexes)
- حساب Super Admin (email: admin@promohive.com, password: Admin123!)
- بيانات تجريبية (6 مهام)
- إعدادات افتراضية

---

## 🚀 تشغيل المشروع

### 1. تثبيت الاعتمادات

```bash
npm install
```

### 2. توليد Prisma Client

```bash
npm run prisma:generate
```

### 3. تشغيل المهام

```bash
npm run prisma:migrate
```

### 4. بيانات تجريبية (اختياري)

```bash
npm run prisma:seed
```

### 5. تشغيل المشروع

```bash
# وضع التطوير
npm run dev

# أو بناء للإنتاج
npm run build
npm start
```

---

## 🔐 معلومات تسجيل الدخول الافتراضية

بعد إنشاء الجداول، يمكنك تسجيل الدخول كـ Super Admin:

```
Email: admin@promohive.com
Password: Admin123!
```

⚠️ **هام**: غيّر كلمة المرور فور تسجيل الدخول!

---

## 📧 إعداد البريد الإلكتروني

### في Supabase Dashboard:

1. اذهب إلى **Settings** → **Integrations** → **Email**
2. تأكد من تفعيل "SMTP"
3. أدخل معلومات Hostinger:
   ```
   SMTP Host: smtp.hostinger.com
   Port: 465
   Username: promohive@globalpromonetwork.store
   Password: YOUR_EMAIL_PASSWORD
   ```

---

## 🌐 نشر على Netlify

### 1. ربط المشروع

1. اذهب إلى https://netlify.com
2. سجّل دخول بحساب GitHub
3. اختر "New site from Git"
4. اختر المستودع: `nyttynt96-art/1`

### 2. إعدادات البناء

Netlify سيكتشف `netlify.toml` تلقائياً:
- Build command: `npm run build:client`
- Publish directory: `dist`

### 3. متغيرات البيئة

أضف في Netlify → Site settings → Environment variables:

```
VITE_SUPABASE_URL=https://jxtutquvxmkrajfvdbab.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

### 4. نشر

اضغط "Deploy site"

---

## ✅ قائمة فحص

- [ ] تم إنشاء ملف `.env`
- [ ] تم تحديث كلمة مرور قاعدة البيانات في `.env`
- [ ] تم تحديث كلمة مرور البريد في `.env`
- [ ] تم تنفيذ SQL في Supabase
- [ ] تم تثبيت الاعتمادات (`npm install`)
- [ ] تم توليد Prisma Client (`npm run prisma:generate`)
- [ ] تم تشغيل المهام (`npm run prisma:migrate`)
- [ ] تم ربط المشروع مع Netlify
- [ ] تمت إضافة متغيرات البيئة في Netlify
- [ ] تم نشر المشروع
- [ ] يمكن تسجيل الدخول كأدمن

---

## 🆘 في حالة وجود مشاكل

### المشكلة: لا يمكن الاتصال بقاعدة البيانات

**الحل:**
1. تحقق من صحة كلمة المرور في `DATABASE_URL`
2. تأكد من تفعيل Supabase
3. راجع `Settings` → `Database` → `Connection string`

### المشكلة: البريد الإلكتروني لا يصل

**الحل:**
1. تحقق من كلمة مرور SMTP في `.env`
2. تأكد من السماح بالوصول من التطبيقات الخارجية في Hostinger
3. اختبر من Supabase Dashboard → Email

### المشكلة: لا يمكن تسجيل الدخول

**الحل:**
1. تأكد من تنفيذ SQL بشكل صحيح
2. تحقق من وجود جدول `User` في Supabase
3. جرب استعادة البيانات (`npm run prisma:seed`)

---

## 📞 للدعم

- **WhatsApp**: +17253348692
- **Email**: promohive@globalpromonetwork.store
- **GitHub**: https://github.com/nyttynt96-art/1

---

## 📝 ملاحظات إضافية

1. **أمان**: لا تشارك `.env` مع أي شخص
2. **النسخ الاحتياطي**: قم بعمل backup لقاعدة البيانات بانتظام
3. **التحديثات**: `git pull` لسحب التحديثات الجديدة
4. **السجلات**: راجع `Logs` في Netlify لتتبع المشاكل

---

## ✨ المشروع جاهز تماماً!

ما عليك سوى:
1. إنشاء `.env` وإضافة كلمة المرور
2. تنفيذ SQL في Supabase
3. نشر على Netlify
4. تبدأ في استخدام التطبيق!

**🎉 كل التوفيق!**

