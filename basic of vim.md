#### different modes and switching



یکی از مهم‌ترین مفاهیم در Vim، **modal editing** است. یعنی بر خلاف سایر ویرایشگرها (مثل VS Code یا Notepad++) که همیشه در حالت ویرایش هستن، در Vim چندین حالت (mode) مختلف وجود داره و هرکدوم کار خاصی انجام می‌ده.

## حالت‌های اصلی در Vim:

### 1. Normal Mode (حالت عادی)
- حالت پیش‌فرض در Vim.
- برای حرکت بین خطوط، حذف، کپی، جستجو و اجرای فرمان‌ها استفاده می‌شه.
- وقتی فایل باز می‌کنی، اولش در همین حالت هستی.
- در این حالت نمی‌تونی مستقیم تایپ کنی؛ باید اول وارد حالت insert بشی.

**مثال‌هایی از دستورات در حالت Normal:**
- `dd` حذف یک خط
- `yy` کپی یک خط
- `p` چسباندن (paste)
- `u` undo
- `/` جستجو

### 2. Insert Mode (حالت درج)
- برای تایپ متن استفاده می‌شه (مثل بقیه ویرایشگرها).
- برای ورود به این حالت، از یکی از این کلیدها استفاده کن:
  - `i` → درج در مکان فعلی
  - `I` → درج در ابتدای خط
  - `a` → درج بعد از مکان فعلی
  - `A` → درج در انتهای خط
  - `o` → باز کردن خط جدید زیر
  - `O` → باز کردن خط جدید بالا

برای **خروج از Insert Mode** و برگشت به Normal Mode:
```
<Esc>
```

### 3. Visual Mode (حالت انتخاب)

- برای انتخاب بخشی از متن استفاده می‌شه (مثل کشیدن موس در بقیه ویرایشگرها)
    
- وارد این حالت شو تا بتونی کپی/حذف/تغییر روی ناحیه انجام بدی.
    

ورود به Visual Mode:

- `v` → انتخاب کاراکتر به کاراکتر
    
- `V` → انتخاب خطی
    
- `Ctrl+v` → انتخاب بلوکی (blockwise)
    

### 4. Command-Line Mode (حالت دستور)

- برای اجرای فرمان‌هایی مثل ذخیره، خروج، جستجوی پیشرفته و... استفاده می‌شه.
    

ورود به این حالت:

- `:` → برای اجرای دستورات مثل `:w`, `:q`, `:wq`
    
- `/` → برای جستجو
    
- `?` → برای جستجوی رو به بالا
    

### 5. Replace Mode (حالت جایگزینی)

- مشابه insert mode، با این تفاوت که حروف جدید جایگزین قبلی‌ها می‌شن.
    
- با زدن `R` وارد این حالت می‌شی.
    
- برای خروج: `<Esc>`

![[Pasted image 20250425140009.png]]


```
:help mode
:help visual-mode
:help insert-mode
:help replace-mode

```

[[Moving around]]

