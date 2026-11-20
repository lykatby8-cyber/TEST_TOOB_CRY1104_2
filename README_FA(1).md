# Toobit Crypto Pre-Move Hunter v3

این مخزن برای اجرای اسکنر تحقیقاتی Toobit با GitHub Actions است.

## فایل‌ها
- `toobit_hunter.py` کد اصلی اسکنر
- `requirements.txt` وابستگی پایتون
- `.github/workflows/toobit-scan.yml` زمان‌بندی و اجرای خودکار

## نصب در GitHub
1. `toobit_hunter.py`، `requirements.txt` و `README_FA.md` را در ریشه مخزن قرار دهید.
2. در GitHub گزینه Add file → Create new file را بزنید.
3. در نام فایل دقیقاً وارد کنید: `.github/workflows/toobit-scan.yml`
4. محتوای فایل workflow را در فایل جدید قرار دهید و Commit کنید.
5. از Settings → Secrets and variables → Actions → New repository secret این دو Secret را بسازید:
   - `NTFY_TOPIC`: نام Topic تصادفی و خصوصی ntfy
   - `NTFY_SERVER`: مقدار `https://ntfy.sh`
6. از زبانه Actions اجرای workflow را بررسی کنید. می‌توانید از Run workflow هم اجرای دستی انجام دهید.

## نکات
- زمان‌بندی Cron روی فاصله اسمی ۶ دقیقه تنظیم شده است؛ GitHub ممکن است اجرا را با تأخیر آغاز کند و اجرای دقیقاً سر هر ۶ دقیقه تضمین نیست.
- برای پایش اولیه همه قراردادهای واجد شرایط فهرست می‌شوند؛ تحلیل عمیق روی حداکثر ۶۰ قرارداد منتخب انجام می‌شود.
- کندل ۵ دقیقه‌ای در حال تشکیل نیز بررسی می‌شود؛ حجم آن تخمینی/لحظه‌ای است و تا بسته‌شدن نهایی نیست.
- تاریخچه شکارها در GitHub Actions Cache نگهداری می‌شود؛ Cache تضمین ذخیره‌سازی دائمی نیست.
- این ابزار فقط داده عمومی بازار را می‌خواند؛ کلید معاملاتی یا endpoint سفارش ندارد و معامله انجام نمی‌دهد.
- خروجی‌ها ابزار تحقیق و فهرست مراقبت‌اند، نه پیش‌بینی قطعی یا توصیه مالی. هنوز باید اجرای زنده و پاسخ endpointهای Toobit در GitHub آزمایش شود.
