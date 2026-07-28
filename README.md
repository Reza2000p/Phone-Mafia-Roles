# 🎩 Mafia Assistant – دستیار کامل بازی مافیا

<p align="center">
  <img src="assets/icon.png" width="120" alt="Mafia Assistant Logo">
</p>

<p align="center">
  <strong>یک اپلیکیشن جامع، آفلاین و سریع برای مدیریت بازی مافیا</strong><br>
  <span>تقسیم نقش، قرعه‌کشی، پنل گرداننده، لیدربورد و گالری نقش‌ها</span>
</p>

<p align="center">
  <a href="#-features">ویژگی‌ها</a> •
  <a href="#-screenshots">تصاویر</a> •
  <a href="#-installation">نصب</a> •
  <a href="#-development">توسعه</a> •
  <a href="#-folder-structure">ساختار</a> •
  <a href="#-license">مجوز</a>
</p>

---

## 📱 درباره‌ی پروژه

**دستیار مافیا** یک اپلیکیشن موبایل اندروید (و وب‌اپلیکیشن PWA) است که به‌صورت کامل فرآیند **تقسیم نقش، قرعه‌کشی کارت‌ها، مدیریت بازی توسط گرداننده (گاد)** و **ثبت امتیازات و لیدربورد** را خودکار می‌کند.

این برنامه با استفاده از **Capacitor** ساخته شده و برای اندروید به‌صورت native ارائه می‌شود، اما در مرورگر وب نیز کاملاً قابل اجراست.

---

## ✨ ویژگی‌ها

- 🎯 **تقسیم نقش‌ها** با بیش از ۸۰ نقش مختلف در سه گروه شهروند، مافیا و مستقل
- 🃏 **قرعه‌کشی کارت‌ها** با شماره‌های تصادفی – هر بازیکن نقش خود را باز می‌کند
- 👑 **پنل گاد (گرداننده)**:
  - ثبت نام بازیکنان
  - مدیریت امتیاز و اخطار هر بازیکن
  - تغییر وضعیت زنده/مرده
  - نمایش آمار لحظه‌ای گروه‌ها
  - تایمر با حالت‌های عادی و معکوس
  - پخش موسیقی زمینه (با انتخاب فایل از حافظه)
- 🏆 **لیدربورد** با ذخیره‌سازی امتیازات و اخطارها
- 👥 **مدیریت بازیکنان** (افزودن، ویرایش، حذف، ورود/خروج CSV)
- 🖼️ **گالری نقش‌ها** با تصاویر و توضیحات
- 📋 **گزارش نهایی** با خروجی TXT، HTML و ذخیره‌سازی خودکار نتایج
- 💾 **ذخیره‌سازی دائمی** در اندروید با Capacitor Preferences
- 🌙 **حالت شب** و رابط کاربری واکنش‌گرا (RTL)
- 📱 **آفلاین** – کاملاً بدون نیاز به اینترنت کار می‌کند
- 🔒 **قفل چرخش صفحه، غیرفعال‌سازی زوم و خاموش نشدن صفحه** در پنل گاد

---

## 📸 تصاویر

> به‌زودی اسکرین‌شات‌ها اضافه می‌شوند.

---

## 📦 نصب روی گوشی اندروید

برای نصب نسخه‌ی آماده‌ی APK:

1. فایل `app-release.apk` را از [بخش Releases](https://github.com/your-username/mafia-assistant/releases) دانلود کنید.
2. در گوشی، گزینه‌ی **نصب از منابع ناشناس** را فعال کنید.
3. روی فایل APK بزنید و نصب را کامل کنید.

---

## 🛠️ توسعه و ساخت از صفر

### پیش‌نیازها

- [Node.js](https://nodejs.org/) (نسخه ۱۶ یا بالاتر)
- [Android Studio](https://developer.android.com/studio) (با Android SDK نصب‌شده)
- [JDK 11 یا 17](https://adoptium.net/)

### مراحل ساخت

```bash
# 1. کلون کردن مخزن
git clone https://github.com/your-username/mafia-assistant.git
cd mafia-assistant

# 2. نصب وابستگی‌ها
npm install

# 3. افزودن پلتفرم اندروید (فقط بار اول)
npx cap add android

# 4. همگام‌سازی فایل‌ها
npx cap sync android

# 5. باز کردن در Android Studio
npx cap open android

# 6. در Android Studio: Build > Build Bundle(s) / APK(s) > Build APK(s)
```

فایل APK در مسیر `android/app/build/outputs/apk/debug/` یا `release/` قرار می‌گیرد.

### ساخت نسخه‌ی Release (امضا شده)

برای انتشار، باید یک Keystore بسازید و در Android Studio از گزینه‌ی **Generate Signed Bundle / APK** استفاده کنید.

---

## 📂 ساختار پوشه‌ها

```
mafia-assistant/
├── index.html                 # صفحه‌ی اصلی اپلیکیشن
├── manifest.json              # PWA manifest
├── sw.js                      # Service Worker
├── roles-descriptions.json    # توضیحات نقش‌ها
├── capacitor.config.json      # تنظیمات Capacitor
├── package.json               # وابستگی‌ها و اسکریپت‌ها
├── .gitignore                 # فایل‌های نادیده‌گرفته‌شده
├── assets/                    # تصاویر و منابع
│   ├── images/                # تصاویر نقش‌ها (roleId.png)
│   ├── icons/                 # آیکون‌های PWA
│   └── screenshots/           # اسکرین‌شات‌ها (اختیاری)
├── android/                   # پروژه‌ی اندروید (تولید شده توسط Capacitor)
├── node_modules/              # وابستگی‌ها (نادیده گرفته شود)
└── resources/                 # منابع آیکون و اسپلش (برای تولید assets)
    └── icon.png               # آیکون اصلی (۱۰۲۴×۱۰۲۴)
```

---

## 🧪 تست در مرورگر

برای تست نسخه‌ی وب بدون نیاز به اندروید، کافی است فایل `index.html` را در مرورگر باز کنید یا از یک سرور محلی استفاده کنید:

```bash
npx serve .
```

---

## 🌐 دسترسی به داده‌ها در اندروید

در نسخه‌ی اندروید، تمام داده‌ها (بازیکنان، سناریوها، امتیازات و وضعیت بازی) با استفاده از **Capacitor Preferences** در سطح سیستمعامل ذخیره می‌شوند و با پاک شدن کش مرورگر از بین نمی‌روند.

---

## 🤝 مشارکت

اگر ایده یا پیشنهادی برای بهبود دارید، خوشحال می‌شویم Pull Request شما را ببینیم.

1. مخزن را Fork کنید.
2. یک شاخه‌ی جدید برای ویژگی خود ایجاد کنید (`git checkout -b feature/amazing-feature`).
3. تغییرات را Commit کنید (`git commit -m 'Add some amazing feature'`).
4. به شاخه‌ی اصلی Push کنید (`git push origin feature/amazing-feature`).
5. یک Pull Request باز کنید.

---

## 📄 مجوز

این پروژه تحت مجوز **MIT** منتشر شده است. برای جزئیات بیشتر، فایل [LICENSE](LICENSE) را ببینید.

---

## 👨‍💻 توسعه‌دهنده

**رضا پاکدل**  
[GitHub](https://github.com/your-username) • [Email](mailto:your-email@example.com)

---

<p align="center">
  <sub>ساخته شده با ❤️ برای جامعه‌ی مافیا‌بازان ایران</sub>
</p>
