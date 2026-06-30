<div align="center">

# 🧩 Brax

**Run HTML · CSS · JS apps right inside Obsidian**

[![Obsidian Downloads](https://img.shields.io/badge/dynamic/json?logo=obsidian&color=%23483699&label=downloads&query=%24%5B%22brax%22%5D.downloads&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugin-stats.json)](https://obsidian.md/plugins?id=brax)
[![Latest Version](https://img.shields.io/badge/dynamic/json?logo=github&color=green&label=version&query=%24%5B%22brax%22%5D.version&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugins.json)](https://github.com/Im-Hugo/obsidian-brax/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

---

> 🇬🇧 [English](#english) · 🇮🇷 [فارسی](#فارسی)

---

<a name="english"></a>

## 🇬🇧 English

### What is Brax?

Brax is an [Obsidian](https://obsidian.md) plugin that lets you build, edit, and run self-contained **HTML / CSS / JavaScript** applications directly inside your vault — no browser tab needed, no external server, no setup.

Whether you want a personal tool, an interactive widget, a mini dashboard, a game, or a data visualization — if it runs in a browser, it runs in Brax.

---

### ✨ Features

- **`.brax` file type** — dedicated file format that opens in Brax's custom view
- **Live preview** — your app re-renders automatically as you type (300 ms debounce)
- **Split edit / preview modes** — toggle between a full-screen code editor and a full-screen rendered preview with a single click or keyboard shortcut
- **Built-in code editor** — monospace textarea with line numbers and synchronized scrolling, no external dependency
- **Tab key support** — inserts two spaces instead of switching focus
- **Ctrl/Cmd + S to save** — familiar shortcut with a confirmation notice
- **Sandboxed iframes** — each app runs in an isolated `<iframe>` with `allow-scripts allow-same-origin allow-forms allow-modals allow-popups`; sandbox mode can be toggled in settings
- **Touch forwarding** — touch events from inside the iframe are forwarded to the parent window, making apps work correctly on mobile and tablet
- **Markdown code block renderer** — embed a `brax` fenced code block in any note and it renders live inline, with a toggleable source view
- **Ribbon icon & commands** — create a new app from the sidebar icon, command palette, or keyboard shortcut
- **Starter template** — new `.brax` files are pre-filled with a gradient hero layout so you start with something that already looks good

---

### 📦 Installation

#### From the Obsidian Community Plugins browser (recommended)

1. Open **Settings → Community plugins**
2. Disable **Safe mode** if prompted
3. Click **Browse** and search for `Brax`
4. Click **Install**, then **Enable**

#### Manual installation

1. Download `main.js`, `styles.css`, and `manifest.json` from the [latest release](https://github.com/Im-Hugo/obsidian-brax/releases)
2. Copy them into `.obsidian/plugins/brax/` inside your vault
3. Reload Obsidian and enable the plugin under **Settings → Community plugins**

---

### 🚀 Getting Started

#### Create a new Brax app

Three ways to create a new `.brax` file:

| Method | How |
|---|---|
| Ribbon icon | Click the `</>` icon in the left sidebar |
| Command palette | `Ctrl/Cmd + P` → *Create new Brax App* |
| Keyboard shortcut | Assign one in **Settings → Hotkeys** |

A modal will ask for a name. Brax sanitizes the name and creates a `.brax` file in your vault root, then opens it immediately.

#### Edit / Preview toggle

- Click the **pencil icon** (✏️) in the view header to enter edit mode
- Click the **eye icon** (👁) to return to preview mode
- Or use the command palette: *Toggle Brax edit mode*

#### Embed in a Markdown note

Use a fenced code block with the `brax` language tag:

````markdown
```brax
<!DOCTYPE html>
<html>
<body>
  <h1 style="color: coral;">Hello from a note!</h1>
</body>
</html>
```
````

The block renders an interactive iframe inline in reading view, with a "Show source / Hide source" toggle below it.

---

### ⌨️ Commands

| Command | Description |
|---|---|
| `brax: Create new Brax App` | Opens name modal and creates a `.brax` file |
| `brax: Insert Brax code block` | Inserts a starter `brax` fenced block at cursor |
| `brax: Toggle Brax edit mode` | Switches between edit and preview in the active Brax view |

---

### ⚙️ Settings

| Setting | Default | Description |
|---|---|---|
| Sandbox iframes | `true` | Isolates apps from Obsidian internals. Recommended to keep enabled. |

---

### 💡 Tips & Use Cases

- **Personal dashboards** — build a daily dashboard with weather, tasks, or timers using vanilla JS
- **Interactive notes** — embed calculators, converters, or quizzes directly in your notes
- **Prototyping** — quickly prototype UI ideas without leaving Obsidian
- **Games & experiments** — write canvas-based games or CSS art and see them live
- **Learning** — practice HTML/CSS/JS with instant visual feedback
- **Presentations** — create animated slides or demos that live alongside your notes

---

### 🔒 Security

Brax runs your HTML inside a sandboxed `<iframe>` using the `srcdoc` attribute. The sandbox flags allow scripts and same-origin access (required for most interactive apps) but the iframe is still isolated from Obsidian's own DOM and file system. Touch events are forwarded via `postMessage` with a `__braxTouch` sentinel to prevent collision with other messages.

If you need stricter isolation, disable **Sandbox iframes** in settings — note that this removes `allow-same-origin`, which may break some browser APIs.

---

### 🛠️ Development

```bash
git clone https://github.com/Im-Hugo/obsidian-brax.git
cd obsidian-brax
npm install
npm run dev      # watch mode
npm run build    # production bundle
```

Copy the output (`main.js`, `styles.css`, `manifest.json`) into your vault's `.obsidian/plugins/brax/` folder and reload Obsidian.

---

### 🤝 Contributing

Bug reports, feature requests, and pull requests are welcome. Please open an issue first to discuss larger changes.

---

### 📄 License

MIT © [Im-Hugo](https://github.com/Im-Hugo)

---
---

<a name="فارسی"></a>

## 🇮🇷 فارسی

### Brax چیست؟

Brax یک افزونه برای [Obsidian](https://obsidian.md) است که به شما اجازه می‌دهد اپلیکیشن‌های **HTML / CSS / JavaScript** را مستقیماً داخل vault خود بسازید، ویرایش کنید و اجرا کنید — بدون نیاز به تب مرورگر، سرور خارجی، یا هیچ تنظیم اضافه‌ای.

هر چیزی که در مرورگر اجرا می‌شود — ابزار شخصی، ویجت تعاملی، داشبورد مینیمال، بازی، یا نمودار داده — در Brax هم اجرا می‌شود.

---

### ✨ قابلیت‌ها

- **فرمت فایل `.brax`** — فرمت اختصاصی که در ویوی سفارشی Brax باز می‌شود
- **پیش‌نمایش زنده** — اپ با هر تغییر در کد، به‌صورت خودکار رندر می‌شود (تأخیر ۳۰۰ میلی‌ثانیه)
- **دو حالت ویرایش / پیش‌نمایش** — با یک کلیک یا میانبر کیبورد بین ادیتور تمام‌صفحه و پیش‌نمایش تمام‌صفحه جابه‌جا شوید
- **ادیتور کد داخلی** — textarea مونواسپیس با شماره خطوط و اسکرول هماهنگ، بدون وابستگی خارجی
- **پشتیبانی از کلید Tab** — دو فاصله درج می‌کند به‌جای اینکه فوکوس را جابه‌جا کند
- **Ctrl/Cmd + S برای ذخیره** — میانبر آشنا با نوتیفیکیشن تأیید
- **iframe ایزوله (Sandboxed)** — هر اپ در یک `<iframe>` جداگانه با مجوزهای کنترل‌شده اجرا می‌شود؛ این حالت از تنظیمات قابل تغییر است
- **فوروارد رویدادهای لمسی** — رویدادهای touch از داخل iframe به پنجره اصلی منتقل می‌شوند تا اپ‌ها روی موبایل و تبلت هم درست کار کنند
- **رندر در بلاک کد Markdown** — یک بلاک کد `brax` را در هر نوشته‌ای قرار دهید تا inline رندر شود، با دکمه نمایش/پنهان کردن سورس
- **آیکون نوار کناری و دستورات** — ساخت اپ جدید از آیکون sidebar، پالت دستورات، یا میانبر کیبورد
- **قالب آغازین** — فایل‌های `.brax` جدید با یک طرح gradient آماده پر می‌شوند

---

### 📦 نصب

#### از طریق Community Plugins اوبسیدین (توصیه‌شده)

1. وارد **Settings → Community plugins** شوید
2. در صورت نمایش، **Safe mode** را غیرفعال کنید
3. روی **Browse** کلیک کنید و `Brax` را جستجو کنید
4. روی **Install** و سپس **Enable** کلیک کنید

#### نصب دستی

1. فایل‌های `main.js`، `styles.css` و `manifest.json` را از [آخرین نسخه](https://github.com/Im-Hugo/obsidian-brax/releases) دانلود کنید
2. آن‌ها را در مسیر `.obsidian/plugins/brax/` داخل vault خود کپی کنید
3. Obsidian را مجدداً بارگذاری کرده و افزونه را از **Settings → Community plugins** فعال کنید

---

### 🚀 شروع کار

#### ساخت اپ Brax جدید

سه روش برای ساخت فایل `.brax` جدید وجود دارد:

| روش | نحوه دسترسی |
|---|---|
| آیکون نوار کناری | کلیک روی آیکون `</>` در سایدبار چپ |
| پالت دستورات | `Ctrl/Cmd + P` ← *Create new Brax App* |
| میانبر کیبورد | از **Settings → Hotkeys** تعیین کنید |

یک modal نام اپ را می‌پرسد. Brax نام را پاک‌سازی می‌کند، یک فایل `.brax` در root vault می‌سازد و بلافاصله آن را باز می‌کند.

#### جابه‌جایی بین ویرایش و پیش‌نمایش

- روی **آیکون مداد** (✏️) در هدر ویو کلیک کنید تا وارد حالت ویرایش شوید
- روی **آیکون چشم** (👁) کلیک کنید تا به پیش‌نمایش برگردید
- یا از پالت دستورات: *Toggle Brax edit mode*

#### جاسازی در نوشته Markdown

از یک بلاک کد fenced با تگ زبان `brax` استفاده کنید:

````markdown
```brax
<!DOCTYPE html>
<html>
<body>
  <h1 style="color: coral;">سلام از داخل نوشته!</h1>
</body>
</html>
```
````

این بلاک در حالت reading view به‌صورت یک iframe تعاملی inline رندر می‌شود، با دکمه «نمایش سورس / پنهان سورس» در زیر آن.

---

### ⌨️ دستورات

| دستور | توضیح |
|---|---|
| `brax: Create new Brax App` | modal نام را باز می‌کند و فایل `.brax` می‌سازد |
| `brax: Insert Brax code block` | یک بلاک کد `brax` آغازین در موقعیت مکان‌نما درج می‌کند |
| `brax: Toggle Brax edit mode` | بین حالت ویرایش و پیش‌نمایش در ویوی فعال جابه‌جا می‌شود |

---

### ⚙️ تنظیمات

| تنظیم | پیش‌فرض | توضیح |
|---|---|---|
| Sandbox iframes | `true` | اپ‌ها را از ساختار داخلی Obsidian ایزوله می‌کند. توصیه می‌شود فعال بماند. |

---

### 💡 ایده‌ها و موارد استفاده

- **داشبورد شخصی** — یک داشبورد روزانه با وضعیت آب‌وهوا، وظایف، یا تایمر با vanilla JS بسازید
- **نوشته‌های تعاملی** — ماشین‌حساب، مبدل واحد، یا آزمون را مستقیم داخل نوشته جاسازی کنید
- **پروتوتایپ سریع** — ایده‌های رابط کاربری را بدون خروج از Obsidian آزمایش کنید
- **بازی و تجربه** — بازی‌های canvas-based یا CSS art بنویسید و نتیجه را فوری ببینید
- **یادگیری** — HTML/CSS/JS را با بازخورد بصری آنی تمرین کنید
- **ارائه** — اسلایدهای انیمیشن‌دار یا دموهایی بسازید که کنار نوشته‌هایتان زندگی می‌کنند

---

### 🔒 امنیت

Brax کد HTML شما را داخل یک `<iframe>` sandboxed از طریق ویژگی `srcdoc` اجرا می‌کند. فلگ‌های sandbox اجازه اجرای اسکریپت و دسترسی same-origin را می‌دهند (برای اکثر اپ‌های تعاملی لازم است)، اما iframe همچنان از DOM و فایل‌سیستم Obsidian جدا است. رویدادهای لمسی از طریق `postMessage` با کلید sentinel مخصوص `__braxTouch` فوروارد می‌شوند تا با پیام‌های دیگر تداخل نداشته باشند.

---

### 🛠️ توسعه

```bash
git clone https://github.com/Im-Hugo/obsidian-brax.git
cd obsidian-brax
npm install
npm run dev      # حالت watch
npm run build    # بسته تولید
```

فایل‌های خروجی (`main.js`، `styles.css`، `manifest.json`) را در مسیر `.obsidian/plugins/brax/` داخل vault خود کپی کنید و Obsidian را مجدداً بارگذاری کنید.

---

### 🤝 مشارکت

گزارش باگ، درخواست قابلیت جدید، و pull request استقبال می‌شود. برای تغییرات بزرگ‌تر لطفاً ابتدا یک issue باز کنید.

---

### 📄 مجوز

MIT © [Im-Hugo](https://github.com/Im-Hugo)
