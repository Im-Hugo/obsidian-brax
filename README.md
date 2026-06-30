# Brax — Live Mini App Runner for Obsidian

[![Obsidian Downloads](https://img.shields.io/badge/dynamic/json?logo=obsidian&color=%23483699&label=downloads&query=%24%5B%22brax%22%5D.downloads&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugin-stats.json)](https://obsidian.md/plugins?id=brax)
[![Latest Version](https://img.shields.io/badge/dynamic/json?logo=github&color=green&label=version&query=%24%5B%22brax%22%5D.version&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugins.json)](https://github.com/Im-Hugo/obsidian-brax/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **English** | [فارسی](#فارسی)

---

## English

### What is Brax?

Brax is an Obsidian plugin that lets you build HTML/CSS/JS mini apps and run them directly inside your vault. Write code, see the result instantly — no separate browser or external tool needed.

---

### Features

- **Live execution** — app reloads automatically 300ms after every keystroke
- **Full-screen editor** — code editor overlays the preview, with line numbers and Tab support
- **Inline rename** — rename the mini app from within the editor; the file is renamed too
- **`.brax` files** — each mini app is a standalone file with the `.brax` extension
- **Code blocks** — use ` ```brax ` inside any note to render an app inline
- **Keyboard save** — `Ctrl+S` / `Cmd+S` saves the file from inside the editor
- **Sandbox** — apps are isolated from Obsidian internals

---

### Installation (Manual)

```bash
# 1. Create the plugin folder
mkdir -p YOUR_VAULT/.obsidian/plugins/brax

# 2. Copy the files
cp main.js manifest.json styles.css YOUR_VAULT/.obsidian/plugins/brax/

# 3. Or as a single command
rm -rf YOUR_VAULT/.obsidian/plugins/brax && \
mkdir -p YOUR_VAULT/.obsidian/plugins/brax && \
cp ~/brax/{main.js,manifest.json,styles.css} YOUR_VAULT/.obsidian/plugins/brax/
```

Then in Obsidian:
1. Open **Settings → Community Plugins**
2. Disable **Safe Mode**
3. Enable **Brax**

---

### Build from Source

```bash
# Install dependencies
npm install

# Build once
npm run build

# Build with watch (rebuilds on every file change)
npm run dev
```

Requirements: **Node.js 16+**

---

### Usage

#### Create a new Mini App

- Click the `</>` icon in the sidebar ribbon
- Or use Command Palette: `Brax: Create new Brax App`

#### Editor Shortcuts

| Key | Action |
|-----|--------|
| `Ctrl+S` / `Cmd+S` | Save file |
| `Tab` | Insert 2-space indent |
| `Enter` in name field | Confirm rename |

#### Code Block inside a Note

````markdown
```brax
<!DOCTYPE html>
<html>
<head>
  <style>
    body { font-family: sans-serif; padding: 1rem; }
    button { padding: .5rem 1rem; cursor: pointer; }
  </style>
</head>
<body>
  <h2>Hello from Brax!</h2>
  <button onclick="this.textContent = '🎉 Clicked!'">Click me</button>
</body>
</html>
```
````

---

### File Structure

```
brax/
├── main.js          ← compiled plugin code
├── manifest.json    ← plugin metadata
├── styles.css       ← styles
├── src/
│   └── main.ts      ← TypeScript source
├── package.json
├── tsconfig.json
└── README.md
```

---

### Settings

Under **Settings → Brax**:

| Setting | Description | Default |
|---------|-------------|---------|
| Sandbox iframes | Isolates apps from Obsidian internals | Enabled |

---

### Notes

- The `.brax` extension is hidden in the header — only the app name is shown
- Renaming is only possible from inside the editor toolbar
- If rename fails, make sure no other file with the same name exists in the same folder

---

### License

MIT © [Im-Hugo](https://github.com/Im-Hugo)

---

---

## فارسی

[![Obsidian Downloads](https://img.shields.io/badge/dynamic/json?logo=obsidian&color=%23483699&label=downloads&query=%24%5B%22brax%22%5D.downloads&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugin-stats.json)](https://obsidian.md/plugins?id=brax)
[![Latest Version](https://img.shields.io/badge/dynamic/json?logo=github&color=green&label=version&query=%24%5B%22brax%22%5D.version&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugins.json)](https://github.com/Im-Hugo/obsidian-brax/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

### Brax چیست؟

Brax یک افزونه برای Obsidian است که به شما اجازه می‌دهد مینی‌اپ‌های HTML/CSS/JS بسازید و آن‌ها را مستقیماً داخل vault خود اجرا کنید. کد می‌نویسید، بلافاصله نتیجه را می‌بینید — بدون نیاز به مرورگر جداگانه یا ابزار خارجی.

---

### ویژگی‌ها

- **اجرای زنده** — هر بار که تایپ می‌کنید، اپ بعد از ۳۰۰ میلی‌ثانیه به‌صورت خودکار reload می‌شود
- **ادیتور تمام‌صفحه** — ادیتور کد روی پیش‌نمایش می‌آید، با شماره خط و پشتیبانی از Tab
- **تغییر نام** — اسم مینی‌اپ را مستقیم از داخل ادیتور تغییر دهید؛ فایل هم rename می‌شود
- **فایل `.brax`** — هر مینی‌اپ یک فایل مستقل با پسوند `.brax` است
- **Code block** — با نوشتن ` ```brax ` داخل هر نوت، اپ مستقیم در آن رندر می‌شود
- **ذخیره با کیبورد** — `Ctrl+S` / `Cmd+S` داخل ادیتور فایل را ذخیره می‌کند
- **Sandbox** — اپ‌ها از Obsidian ایزوله هستند

---

### نصب (دستی)

```bash
# ۱. پوشه افزونه را بساز
mkdir -p YOUR_VAULT/.obsidian/plugins/brax

# ۲. فایل‌ها را کپی کن
cp main.js manifest.json styles.css YOUR_VAULT/.obsidian/plugins/brax/

# ۳. یا با یک دستور
rm -rf YOUR_VAULT/.obsidian/plugins/brax && \
mkdir -p YOUR_VAULT/.obsidian/plugins/brax && \
cp ~/brax/{main.js,manifest.json,styles.css} YOUR_VAULT/.obsidian/plugins/brax/
```

سپس در Obsidian:
1. **Settings → Community Plugins** را باز کن
2. **Safe Mode** را خاموش کن
3. افزونه **Brax** را فعال کن

---

### بیلد از سورس

```bash
# نصب dependencies
npm install

# بیلد یک‌بار
npm run build

# بیلد با watch (هر بار که فایل تغییر کند)
npm run dev
```

نیازمندی‌ها: **Node.js 16+**

---

### استفاده

#### ساخت مینی‌اپ جدید

- روی آیکون `</>` در نوار کناری کلیک کن
- یا از Command Palette: `Brax: Create new Brax App`

#### کلیدهای میانبر ادیتور

| کلید | عملکرد |
|------|---------|
| `Ctrl+S` / `Cmd+S` | ذخیره فایل |
| `Tab` | ۲ فاصله indent |
| `Enter` در فیلد نام | تأیید تغییر نام |

#### Code Block داخل نوت

````markdown
```brax
<!DOCTYPE html>
<html>
<head>
  <style>
    body { font-family: sans-serif; padding: 1rem; }
    button { padding: .5rem 1rem; cursor: pointer; }
  </style>
</head>
<body>
  <h2>Hello from Brax!</h2>
  <button onclick="this.textContent = '🎉 Clicked!'">Click me</button>
</body>
</html>
```
````

---

### ساختار فایل‌ها

```
brax/
├── main.js          ← کد اصلی افزونه (compiled)
├── manifest.json    ← اطلاعات افزونه
├── styles.css       ← استایل‌ها
├── src/
│   └── main.ts      ← سورس TypeScript
├── package.json
├── tsconfig.json
└── README.md
```

---

### تنظیمات

در **Settings → Brax**:

| تنظیم | توضیح | پیش‌فرض |
|-------|-------|---------|
| Sandbox iframes | ایزوله‌سازی اپ‌ها از Obsidian | فعال |

---

### نکات مهم

- پسوند `.brax` در هدر نشان داده نمی‌شود — فقط نام فایل
- تغییر نام فقط از داخل ادیتور (toolbar بالا) ممکن است
- اگر rename انجام نشد، مطمئن شو فایل دیگری با همان نام وجود ندارد

---

### لایسنس

MIT © [Im-Hugo](https://github.com/Im-Hugo)
