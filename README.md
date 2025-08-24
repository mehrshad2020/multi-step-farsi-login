# فرم ورود چند مرحله‌ای 🔐

یک فرم ورود مدرن و زیبا با سه روش مختلف ورود که با Tailwind CSS و HTML خالص طراحی شده است.
<img width="745" height="778" alt="image" src="https://github.com/user-attachments/assets/95aa43ed-035a-4192-a0c5-7cb2714cbfb9" />


## 📋 فهرست مطالب

- [ویژگی‌ها](#ویژگی‌ها)
- [روش‌های ورود](#روش‌های-ورود)
- [نصب و راه‌اندازی](#نصب-و-راه‌اندازی)
- [ساختار پروژه](#ساختار-پروژه)
- [راهنمای طراحی](#راهنمای-طراحی)
- [قابلیت‌های تکنیکی](#قابلیت‌های-تکنیکی)
- [سفارشی‌سازی](#سفارشی‌سازی)
- [مرورگرهای پشتیبانی‌شده](#مرورگرهای-پشتیبانی‌شده)

## ✨ ویژگی‌ها

### 🎯 عملکردی
- **سه روش ورود مختلف** با UX متفاوت
- **Progress Stepper** نمایشگر پیشرفت
- **Validation در زمان واقعی** برای تمام فیلدها
- **Auto-advance OTP** تکمیل خودکار کد یکبارمصرف
- **Resend Timer** تایمر برای ارسال مجدد کد
- **Remember Device** ذخیره دستگاه

### 🎨 ظاهری
- **طراحی Responsive** متناسب با تمام دستگاه‌ها
- **Dark/Light Mode** حالت تیره و روشن
- **RTL Support** پشتیبانی کامل از راست‌چین
- **فونت وزیر** برای زیبایی متن فارسی
- **انیمیشن‌های نرم** برای تجربه بهتر کاربر

### 🔧 تکنیکی
- **بدون وابستگی خارجی** (فقط Tailwind CDN)
- **Vanilla JavaScript** بدون framework
- **Accessible** دسترسی‌پذیری WCAG
- **Cross-browser** سازگاری با تمام مرورگرها

## 🚪 روش‌های ورود

### Flow 1: ورود کلاسیک (امن) 🔒
```
شناسه کاربر → رمز عبور → تأیید دومرحله‌ای → موفقیت
```
- ایمیل یا شماره موبایل
- رمز عبور با قابلیت نمایش/مخفی
- کد ۶ رقمی OTP
- گزینه "به خاطر سپردن دستگاه"

### Flow 2: ورود بدون رمز (مینیمال) 📱
```
شناسه کاربر → انتخاب روش → کد/لینک → موفقیت
```
- ایمیل یا شماره موبایل
- انتخاب از بین:
  - کد پیامکی (SMS)
  - کد ایمیلی
  - لینک جادویی (Magic Link)

### Flow 3: ورود سریع (Social + Fallback) ⚡
```
Social Login → Fallback (در صورت خطا) → موفقیت
```
- دکمه‌های Google و Apple
- Fallback به روش‌های معمول در صورت خطا

## 🚀 نصب و راه‌اندازی

### نصب ساده
```bash
# کلون پروژه
git clone [repository-url]
cd فرم_چند_مرحله_لاگین

# باز کردن فایل در مرورگر
open index.html
```


## 📁 ساختار پروژه

```
فرم_چند_مرحله_لاگین/
├── index.html          # فایل اصلی HTML
├── README.md          # مستندات (این فایل)
└── assets/            # (در صورت نیاز)
    ├── images/
    └── icons/
```

## 🎨 راهنمای طراحی

### رنگ‌ها
```css
Primary:     #4F46E5  /* ایندیگو اصلی */
Success:     #10B981  /* سبز موفقیت */
Destructive: #EF4444  /* قرمز خطا */
Surface:     #FFFFFF  /* سطح روشن */
Dark:        #0B1220  /* سطح تیره */
```

### فاصله‌گذاری
- **8px**: فاصله‌های کوچک (tight)
- **16px**: فاصله‌های استاندارد
- **24px**: فاصله بین بلوک‌ها
- **32px**: فاصله قبل از دکمه‌های اصلی

### تایپوگرافی
- **عنوان مراحل**: 20-22px، وزن 600
- **لیبل‌ها**: 13-14px، وزن 500
- **متن کمکی**: 12-13px
- **OTP**: فونت Monospace

## ⚙️ قابلیت‌های تکنیکی

### Validation
```javascript
// ایمیل
const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

// شماره موبایل ایران
const phoneRegex = /^09\d{9}$/;

// رمز عبور (حداقل 8 کاراکتر)
const isValidPassword = password.length >= 8;
```

### انیمیشن‌ها
- **Fade + Slide**: ورود نرم مراحل
- **Shake**: تکان برای خطاها
- **Success Bounce**: پرش موفقیت
- **Loading Spinner**: حالت بارگذاری

### Local Storage
```javascript
// ذخیره تم
localStorage.setItem('theme', 'dark');

// ذخیره دستگاه (در نسخه کامل)
localStorage.setItem('rememberedDevice', 'true');
```

## 🎛️ سفارشی‌سازی

### تغییر رنگ‌ها
در بخش `tailwind.config`:
```javascript
colors: {
    primary: '#YOUR_COLOR',    // رنگ اصلی
    success: '#YOUR_COLOR',    // رنگ موفقیت
    destructive: '#YOUR_COLOR' // رنگ خطا
}
```

### تغییر فونت
```css
body {
    font-family: 'YOUR_FONT', 'Vazirmatn', sans-serif;
}
```

### افزودن روش ورود جدید
1. Function جدید در `getStepContent()`
2. بروزرسانی `maxSteps` برای flow
3. اضافه کردن validation مربوطه

## 🔧 ادغام با Backend

### نمونه API Calls
```javascript
// ارسال ایمیل
async function sendOTP(email) {
    const response = await fetch('/api/send-otp', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ email })
    });
    return response.json();
}

// تأیید کد
async function verifyOTP(email, code) {
    const response = await fetch('/api/verify-otp', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ email, code })
    });
    return response.json();
}
```

### Security Headers
```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">
<meta http-equiv="X-Content-Type-Options" content="nosniff">
<meta http-equiv="X-Frame-Options" content="DENY">
```

## 🌐 مرورگرهای پشتیبانی‌شده

### دسکتاپ
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

### موبایل
- ✅ iOS Safari 14+
- ✅ Chrome Mobile 90+
- ✅ Samsung Internet 14+

## 📱 ویژگی‌های موبایل

- **Touch Friendly**: دکمه‌ها و فیلدهای لمسی مناسب
- **Viewport Optimized**: بهینه‌سازی برای صفحه‌نمایش کوچک
- **Haptic Feedback**: لرزش در تأیید (قابل فعال‌سازی)
- **Auto-zoom Prevention**: جلوگیری از zoom خودکار iOS

## 🔒 ملاحظات امنیتی

### مخفی‌سازی اطلاعات
```javascript
// ماسک کردن ایمیل: user@example.com → us***@example.com
function maskEmail(email) {
    const [username, domain] = email.split('@');
    return `${username.substring(0, 2)}***@${domain}`;
}
```

### محدودیت تلاش
- حداکثر 3 تلاش برای رمز عبور
- تایمر برای ارسال مجدد OTP
- Rate limiting (در سمت سرور)

## 🐛 عیب‌یابی

### مشکلات رایج

**فونت وزیر لود نمی‌شود:**
```css
/* جایگزین CDN محلی */
@font-face {
    font-family: 'Vazirmatn';
    src: url('./fonts/Vazirmatn.woff2') format('woff2');
}
```

**انیمیشن‌ها کار نمی‌کنند:**
```css
/* اضافه کردن prefixes */
-webkit-animation: fadeSlideIn 220ms ease-out;
animation: fadeSlideIn 220ms ease-out;
```

**مشکل RTL:**
```html
<!-- اطمینان از dir="rtl" -->
<html lang="fa" dir="rtl">
```

## 📈 بهینه‌سازی عملکرد

### تصاویر
- استفاده از SVG برای آیکون‌ها
- تنظیم `loading="lazy"` برای تصاویر

### CSS
- حذف CSS استفاده‌نشده Tailwind
- فشرده‌سازی فایل‌ها در production

### JavaScript
- Minification کد
- Lazy loading برای بخش‌های غیرضروری





این پروژه تحت مجوز MIT منتشر شده است.

---

**ساخته شده با ❤️ برای جامعه توسعه‌دهندگان ایرانی**

🔗 **پیوندهای مفید:**
- [Tailwind CSS](https://tailwindcss.com)
- [Lucide Icons](https://lucide.dev)
- [فونت وزیر](https://github.com/rastikerdar/vazirmatn)

