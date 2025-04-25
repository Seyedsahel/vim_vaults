

فایل پیکربندی Vim با نام `.vimrc` در مسیر Home کاربر قرار داره (`~/.vimrc`).  
از طریق این فایل می‌تونی تنظیمات دلخواهت رو برای شخصی‌سازی Vim اعمال کنی.

---

## 🛠 1. Key Mapping (تغییر و تعریف میانبرهای شخصی)

با استفاده از دستور `map` یا `nmap`، می‌تونی کلیدهای خاصی رو دوباره تعریف کنی:

| دستور | توضیح |
|-------|--------|
| `nmap <key> <command>` | تعریف میانبر در حالت Normal |
| `imap <key> <command>` | در حالت Insert |
| `vmap <key> <command>` | در حالت Visual |

### مثال‌ها:
```vim
nmap <F5> :w<CR>:!gcc % -o output && ./output<CR>
imap jj <Esc>
```

در مثال بالا:

- F5 فایل فعلی رو کامپایل و اجرا می‌کنه (برای C)
    
- تایپ `jj` در Insert Mode معادل Esc عمل می‌کنه

---

## 🔍 2. Ignore Case هنگام جستجو

برای اینکه موقع جستجو (`/` یا `?`) حساسیت به بزرگی/کوچکی حروف نداشته باشه:

`set ignorecase`

و اگر بخوای فقط وقتی حساس نباشه که همه حروف کوچک باشن:

`set smartcase`

> یعنی:
> 
> - `/hello` → هم `Hello` رو پیدا می‌کنه هم `HELLO`
>     
> - ولی `/HELLO` → فقط `HELLO` رو پیدا می‌کنه

----
## ⚡️ 3. Auto-complete و پیشنهاد کد برای زبان خاص

Vim به‌صورت پیش‌فرض قابلیت ساده‌ای از Auto-complete داره (`Ctrl+n` یا `Ctrl+p` در Insert Mode)،  
ولی برای پشتیبانی پیشرفته از زبان‌های برنامه‌نویسی باید از پلاگین استفاده کنی.

### بهترین روش: استفاده از پلاگین `coc.nvim`

`coc.nvim` (Conquer of Completion) پلاگینی بسیار قدرتمند و شبیه IntelliSense هست که با LSP (Language Server Protocol) کار می‌کنه.

### مراحل راه‌اندازی:

#### 1. نصب پلاگین منیجر (مثلاً `vim-plug`):

در فایل `.vimrc`:

```
call plug#begin('~/.vim/plugged')
Plug 'neoclide/coc.nvim', {'branch': 'release'}
call plug#end()
```

بعد از ذخیره، داخل Vim بزن:

```
:PlugInstall
```

2. نصب LSP مخصوص زبان دلخواه:
3. داخل Vim بزن:
```
:CocInstall coc-python
```

> اینا باعث می‌شن برای اون زبان خاص پیشنهاد کد، پرش به تعریف، تشخیص خطا و ... فعال بشه.

#### 3. استفاده:

در Insert Mode فقط بنویس، خودش پیشنهاد می‌ده.  
با `Tab` یا `Enter` می‌تونی پیشنهاد رو انتخاب کنی.

---
### ✨ چند تنظیم کاربردی دیگر در `.vimrc`

```

syntax on             " فعال کردن هایلایت سینتکس
set number            " نمایش شماره خطوط
set relativenumber    " نمایش شماره خطوط نسبی (برای حرکت سریع‌تر)
set tabstop=4         " اندازه تب برابر ۴ فاصله
set expandtab         " جایگزینی تب با فاصله
set shiftwidth=4      " میزان تورفتگی هنگام indent
set autoindent        " حفظ تورفتگی خط قبل
set mouse=a           " فعال کردن پشتیبانی از ماوس

```


[[history of vim]]
