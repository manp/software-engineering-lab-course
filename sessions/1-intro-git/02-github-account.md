# 🧾 تاپیک ۲ — ساخت حساب کاربری در GitHub

> «GitHub بزرگ‌ترین سرویس میزبانی مخازن گیت است؛ جایی که تاریخچه‌ی پروژه‌ها را نگه می‌دارد و تیم‌ها روی آن هم‌کاری می‌کنند.»

---

## ۱. GitHub چیست؟

**GitHub** یک سرویس ابری برای میزبانی **رپازیتوری‌های گیت** است و این امکانات را می‌دهد:

- نگه‌داری نسخه‌ی راه دور (Remote) از پروژه‌های شما
- اشتراک‌گذاری پروژه با دیگران (عمومی یا خصوصی)
- هم‌کاری تیمی (Issue، Pull Request، Code Review)
- پشتیبان‌گیری خودکار از کدها
- مشاهده‌ی تاریخچه و تغییرات از مرورگر

> گیت ابزار محلی است، GitHub سرویس ابری میزبانی آن است. با هم کار می‌کنند ولی یکی نیستند.

---

## ۲. ساخت حساب کاربری — قدم به قدم

1. به آدرس [github.com](https://github.com) بروید.
2. روی **Sign up** کلیک کنید.
3. ایمیل خود را وارد کنید و **Continue** بزنید.
4. یک **Password** قوی بسازید (ترجیحاً با مدیر رمز مثل Bitwarden).
5. یک **Username** انتخاب کنید:
   - کوتاه، خوانا و تکراری‌نباشد
   - معمولاً `نام-خانوادگی` یا ترکیبی از حروف اول نام
   - مثال خوب: `zahra-mohammadi`، `ali-rezaei-dev`
   - مثال بد: `ali1385xx1990mohammadi`
6. بعد از تأیید ایمیل (ورود به لینکی که به ایمیل شما می‌آید)، وارد حساب شوید.

---

## ۳. تنظیمات پیشنهادی اولیه

### پروفایل
- **Settings ← Profile:** عکس، نام نمایشی، بیو و لینک‌ها را کامل کنید.
- **Settings ← Public profile:** املای نام را درست بنویسید — کارفرماها و استادها آن را می‌بینند.

### ایمیل خصوصی برای commit ها
برای اینکه ایمیلتان عمومی نشود:

1. **Settings ← Emails**
2. گزینه‌ی **Keep my email addresses private** را فعال کنید.
3. آدرسِ `ID+username@users.noreply.github.com` را کپی کنید.
4. در گیت تنظیم کنید:
```bash
git config --global user.email "12345678+username@users.noreply.github.com"
git config --global user.name "Your Name"
```

### تأیید دو مرحله‌ای (۲FA) — الزامی
حساب‌های GitHub هدف حملات پرتکرارند؛ حتماً فعال کنید:

- **Settings ← Password and authentication ← Two-factor authentication**
- روش پیشنهادی: اپ احراز هویت مثل Google Authenticator یا Face ID/Premium

---

## ۴. اتصال امن از خط فرمان

### روش SSH (پیشنهادی)
```bash
# بررسی اینکه کلید دارید یا نه
ls -la ~/.ssh

# ساخت کلید جدید (در صورت نبود)
ssh-keygen -t ed25519 -C "your-email@example.com"

# نمایش کلید عمومی برای کپی
cat ~/.ssh/id_ed25519.pub
```

بعد:
1. **Settings ← SSH and GPG keys ← New SSH key**
2. کلید کپی‌شده را Paste کنید و یک نام بدهید (مثلاً «لاب‌تاپ دانشگاه»).
3. تست کنید:
```bash
ssh -T git@github.com
# خروجی موفق: Hi username! You've successfully authenticated...
```

### روش HTTPS + توکن (حالت جایگزین)
1. **Settings ← Developer settings ← Personal access tokens ← Tokens (classic) ← Generate new token**
2. scope های `repo` و `read:org` را انتخاب کنید.
3. توکن را کپی کنید و به‌جای رمز در هنگام push استفاده کنید.

> روش SSH یک‌بار تنظیم می‌شود و همیشه کار می‌کند؛ برای درس‌ها و پروژه‌های ترم پیشنهاد می‌شود.

---

## ۵. تمرین کوتاه

1. حساب GitHub بسازید (قدم‌های بخش ۲).
2. ۲FA را فعال کنید.
3. یک SSH key بسازید و به حساب اضافه کنید.
4. `ssh -T git@github.com` بزنید و پیام موفقیت را ببینید.
5. نام و ایمیل گیت را با `git config --global` تنظیم کنید.

---

📎 **بعدی:** [ساخت رپازیتوری تست](03-test-repo.md)
