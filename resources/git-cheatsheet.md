# برگه‌ی تقلب گیت (Git Cheat Sheet) — جلسه ۱

خلاصه‌ی دستورهای پرکاربرد این جلسه؛ آن را در کنار خود نگه دارید.

## تنظیم اولیه (یک‌بار)
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

## شروع کار
| دستور | توضیح |
|---|---|
| `git init` | شروع یک مخزن جدید در پوشه‌ی فعلی |
| `git clone <url>` | کپی یک مخزن راه دور به سیستم خودتان |

## چرخه‌ی روزانه
| دستور | توضیح |
|---|---|
| `git status` | وضعیت فایل‌ها |
| `git add <file>` یا `git add .` | آماده‌سازی تغییرات |
| `git commit -m "پیام"` | ثبت تغییرات |
| `git push` | ارسال به GitHub |
| `git pull` | دریافت از GitHub |

## مشاهده و مقایسه
| دستور | توضیح |
|---|---|
| `git log --oneline` | تاریخچه‌ی commit ها |
| `git diff` | دیدن تغییرات |
| `git remote -v` | آدرس مخزن راه دور |

## نکته‌ی مهم
> اگر در هنگام push خطای authentication دیدید، از روش SSH استفاده کنید: `ssh -T git@github.com` را اول تست کنید.
