# دليل النشر الكامل - PromoHive

## 📦 الملف المضغوط

**promohive-complete.zip** (1.6 MB) - يحتوي على:
- ✅ Frontend (React + Vite + TypeScript)
- ✅ Backend (tRPC + Express + Drizzle)
- ✅ Database Schema (MySQL/TiDB)
- ✅ جميع الميزات مكتملة

---

## 🚀 طريقة النشر على Manus Platform

### الخطوة 1: فك الضغط

```bash
unzip promohive-complete.zip
cd promohive
```

### الخطوة 2: متغيرات البيئة

المشروع يستخدم قاعدة البيانات المدمجة في Manus، لذلك **لا تحتاج** إلى إضافة `DATABASE_URL`.

**المتغيرات المطلوبة (اختيارية):**

في واجهة Manus → Settings → Secrets:

```env
# App Branding (اختياري)
VITE_APP_TITLE="PromoHive"
VITE_APP_LOGO="/logo.png"

# External APIs (اختياري - للتكامل مع الخدمات الخارجية)
ADGEM_APP_ID="31283"
ADGEM_API_KEY="your-key-here"
ADSTERRA_API_KEY="your-key-here"
CPALEAD_API_KEY="your-key-here"
```

**ملاحظة:** جميع المتغيرات الأساسية (Database, JWT, OAuth) **مُعدة تلقائياً** من Manus.

### الخطوة 3: النشر

1. افتح المشروع في Manus
2. انقر **"Publish"** في الواجهة
3. انتظر حتى يكتمل البناء
4. احصل على رابط التطبيق

---

## 🎯 الوصول للتطبيق

بعد النشر:

### للمستخدمين:
- **الصفحة الرئيسية**: `https://your-app.manus.space`
- **التسجيل**: `https://your-app.manus.space/register`
- **تسجيل الدخول**: `https://your-app.manus.space/login`

### للإدارة:
- **لوحة الإدارة**: `https://your-app.manus.space/admin`
- **تسجيل دخول الأدمن**: استخدم حساب المالك (Owner) المسجل في Manus

---

## 📊 قاعدة البيانات

### الجداول المتوفرة:

1. **users** - المستخدمون
2. **wallets** - المحافظ
3. **transactions** - المعاملات المالية
4. **tasks** - المهام
5. **taskSubmissions** - تقديمات المهام
6. **referrals** - الإحالات
7. **referralRewards** - مكافآت الإحالات
8. **withdrawals** - طلبات السحب
9. **notifications** - الإشعارات
10. **settings** - الإعدادات
11. **auditLogs** - سجلات المراجعة
12. **apiKeys** - مفاتيح API
13. **emailTemplates** - قوالب البريد
14. **crons** - المهام المجدولة
15. **sessions** - الجلسات

### الوصول لقاعدة البيانات:

في واجهة Manus:
1. افتح **Management UI** (الزر في أعلى اليمين)
2. اذهب إلى **Database** panel
3. يمكنك:
   - عرض البيانات (CRUD UI)
   - تنفيذ SQL queries
   - تصدير البيانات

---

## 👤 إنشاء حساب الأدمن

### الطريقة 1: تلقائياً (موصى بها)

المشروع يُنشئ حساب Admin تلقائياً لمالك المشروع (Owner) في Manus.

**للوصول:**
1. سجل دخول بحساب Google/GitHub المستخدم في Manus
2. سيتم ترقيتك تلقائياً إلى `admin` role
3. اذهب إلى `/admin`

### الطريقة 2: يدوياً (عبر Database)

في Database panel:
1. افتح جدول `users`
2. ابحث عن المستخدم
3. غيّر `role` إلى `admin`
4. احفظ التغييرات

---

## 🔧 الميزات المتوفرة

### للمستخدمين:
- ✅ التسجيل وتسجيل الدخول (OAuth)
- ✅ لوحة المستخدم (Dashboard)
- ✅ عرض المهام المتاحة
- ✅ تقديم المهام
- ✅ نظام الإحالات (Referral Code)
- ✅ طلب السحب (USDT)
- ✅ عرض المحفظة والمعاملات

### للإدارة:
- ✅ لوحة الإدارة (Admin Dashboard)
- ✅ إدارة المستخدمين (موافقة، تعليق)
- ✅ إدارة المهام (إضافة، تعديل، حذف)
- ✅ موافقة تقديمات المهام
- ✅ موافقة طلبات السحب
- ✅ عرض الإحصائيات
- ✅ سجلات المراجعة (Audit Logs)

---

## 🎨 تخصيص التطبيق

### تغيير الشعار والعنوان:

في Manus → Settings → General:
1. **Website Name**: غيّر إلى "PromoHive"
2. **Website Logo**: ارفع الشعار من `/promohive/client/public/logo.png`

### تغيير الألوان:

عدّل ملف `/promohive/client/src/index.css`:
```css
:root {
  --primary: 262.1 83.3% 57.8%; /* اللون الأساسي */
  --secondary: 220 14.3% 95.9%; /* اللون الثانوي */
  /* ... */
}
```

---

## 📱 الصفحات المتوفرة

### صفحات عامة:
- `/` - الصفحة الرئيسية
- `/register` - التسجيل
- `/login` - تسجيل الدخول

### صفحات المستخدم:
- `/dashboard` - لوحة المستخدم
- `/tasks` - المهام
- `/referrals` - الإحالات
- `/withdrawals` - السحوبات

### صفحات الإدارة:
- `/admin` - لوحة الإدارة

---

## 🔒 الأمان

المشروع يتضمن:
- ✅ **OAuth Authentication** (Manus)
- ✅ **Session Management** (HTTP-only cookies)
- ✅ **Role-based Access Control** (Admin vs User)
- ✅ **CSRF Protection**
- ✅ **SQL Injection Protection** (Drizzle ORM)
- ✅ **Rate Limiting**

---

## 📊 المراقبة

في Manus Dashboard:
1. **Analytics** - عدد الزوار والمستخدمين
2. **Logs** - سجلات الأخطاء
3. **Database** - حجم البيانات

---

## 🆘 استكشاف الأخطاء

### المشكلة: لا يمكن الوصول للتطبيق
**الحل:** تأكد من أن التطبيق منشور (Published) في Manus

### المشكلة: خطأ في قاعدة البيانات
**الحل:** 
1. افتح Database panel
2. تحقق من الجداول
3. شغّل `pnpm db:push` في Terminal

### المشكلة: لا يمكن تسجيل الدخول
**الحل:**
1. تأكد من OAuth settings في Manus
2. تحقق من `VITE_APP_ID` في Environment variables

---

## 🔄 التحديثات

لتحديث التطبيق:
1. عدّل الكود
2. احفظ Checkpoint جديد
3. انقر **Publish** مرة أخرى

---

## 📞 الدعم

للمساعدة:
- **Manus Docs**: https://docs.manus.im
- **Manus Support**: https://help.manus.im

---

## ✅ قائمة التحقق النهائية

قبل النشر:
- [ ] فك ضغط المشروع
- [ ] رفع الشعار (اختياري)
- [ ] تعيين متغيرات البيئة (اختياري)
- [ ] نشر التطبيق (Publish)
- [ ] اختبار تسجيل الدخول
- [ ] اختبار لوحة الإدارة
- [ ] اختبار الميزات الأساسية

---

**التطبيق جاهز 100% للنشر على Manus Platform!** 🚀

**لا يحتاج أي إعدادات إضافية - فقط Publish وابدأ الاستخدام!**

