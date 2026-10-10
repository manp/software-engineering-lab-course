# 🧾 تاپیک ۳ — ساخت رپازیتوری تست

> «اولین مخزن روی GitHub مثل اولین commit است: وقتی انجام شد، همه‌چیز بعدی راحت‌تر می‌شود.»

---

## ۱. هدف این تمرین

یک مخزن عمومی کوچک روی GitHub می‌سازیم، آن را با گیت محلی وصل می‌کنیم و اولین commit و push را انجام می‌دهیم. این همان مسیری است که در پروژه‌های واقعی و تحویل تمرین‌های آزمایشگاه طی می‌کنید.

---

## ۲. ساخت رپازیتوری روی GitHub

1. وارد حساب GitHub شوید.
2. روی علامت **+** (بالا سمت راست) کلیک کنید و **New repository** را انتخاب کنید.
3. این‌ها را پر کنید:
   - **Repository name:** `my-test-repo`
   - **Description:** مخزن تست برای آزمایشگاه مهندسی نرم‌افزار
   - **Public** را انتخاب کنید (برای تمرین اول)
   - **Add a README file** را تیک بزنید
4. دکمه‌ی سبز **Create repository** را بزنید.

حالا GitHub یک صفحه‌ی خوش‌آمد با چند دستور نشان می‌دهد. ما از مسیر «…or push an existing repository from the command line» استفاده می‌کنیم.

---

## ۳. اتصال مخزن محلی به GitHub

### حالت A — شروع از صفر روی سیستم خودتان

```bash
# داخل پوشه‌ی پروژه‌ی خودتان
mkdir my-test-repo && cd my-test-repo

git init
git add .
git commit -m "first commit"

git branch -M main

git remote add origin git@github.com:username/my-test-repo.git

git push -u origin main
```

> آدرس دقیق remote در همین صفحه‌ی GitHub بعد از ساخت مخزن نمایش داده می‌شود. اگر از HTTPS استفاده می‌کنید آدرس به این شکل است: `https://github.com/username/my-test-repo.git`

### حالت B — وقتی مخزن خالی روی GitHub ساخته‌اید و می‌خواهید فایل اضافه کنید

```bash
git clone git@github.com:username/my-test-repo.git
cd my-test-repo

echo "# My Test Repo" > README.md
echo "hello from lab" > hello.txt

git add .
git commit -m "add: فایل تست اضافه شد"
git push
```

---

## ۴. ساختار پیشنهادی یک مخزن تمرین

برای تمرین‌های آزمایشگاه، یک ساختار ساده و منظم کمک می‌کند:

```
my-test-repo/
├── README.md          # معرفی پروژه و نحوه‌ی اجرا
├── src/               # کدها
│   └── main.py
└── docs/              # مستندات و گزارش‌ها
    └── report.md
```

### README خوب چه دارد؟
- عنوان پروژه
- توضیح کوتاه: این پروژه چیست؟
- نحوه‌ی اجرا (دستورها)
- نام و شماره‌دانشجویی

مثال:
```markdown
# تمرین آزمایشگاه مهندسی نرم‌افزار

این مخزن تمرین اول آزمایشگاه است.

## نحوه اجرا
```bash
python src/main.py
```

## اطلاعات
- نام: علی رضایی
- شماره دانشجویی: ۴۰۰۱۲۳۴۵
```

---

## ۵. بررسی نتیجه

بعد از push:

1. صفحه‌ی `github.com/username/my-test-repo` را باز کنید — فایل‌ها باید آنجا باشند.
2. روی تعداد commit ها کلیک کنید — تاریخچه را می‌بینید.
3. یک تغییر کوچک در README بدهید و دوباره commit و push کنید:
```bash
echo "## تغییر دوم" >> README.md
git add .
git commit -m "docs: README به‌روزرسانی شد"
git push
```
4. صفحه رفرش کنید — commit جدید باید دیده شود.

---

## ۶. تمرین کوتاه

1. مخزن `my-test-repo` را روی GitHub بسازید.
2. آن را clone کنید (حالت B).
3. یک `src/` و `docs/` بسازید و دو فایل ساده داخلشان قرار دهید.
4. commit بزنید و push کنید.
5. README را ویرایش کنید و یک commit دیگر بزنید.
6. `git log --oneline` را اجرا کنید و خروجی را در گزارش جلسه بنویسید.

---

📎 **فایل قبلی:** [ساخت حساب کاربری در GitHub](02-github-account.md) · **نمایه جلسه:** [جلسه ۱](index.md)
