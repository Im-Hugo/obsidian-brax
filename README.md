این یک فایل `README.md` فوق‌العاده حرفه‌ای، دو زبانه (انگلیسی و فارسی) و طولانی هست. توی گیت‌هاب بسیار استاندارد و جذاب به نظر می‌رسه. 

محتوای زیر رو کپی کن و توی فایل `README.md` خودت پیست کن (دقت کن که فایل پسوند `.txt` نگیره، حتماً `README.md` باشه):

```markdown
<div align="center">

# 🚀 Brax

**The Ultimate HTML/JS Sandbox inside Obsidian**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Turn your Obsidian vault into a live web development environment. Build, preview, and interact with HTML, CSS, and JavaScript applications directly inside your notes.

[English](#english) | [فارسی](#فارسی)

</div>

---

<a id="english"></a>
## ✨ English Documentation

### Why Brax?
While Obsidian is incredible for writing Markdown, it lacks native support for rendering and interacting with live web applications. Standard HTML code blocks are static and lifeless. 

**Brax changes this by injecting a fully interactive, sandboxed browser environment directly into your workspace.** Unlike simple HTML viewers, Brax features a custom **Cookie Interception Engine**, meaning web apps that require state, sessions, or user logins can actually function properly inside your notes.

### 🎯 Key Features
*   **Live Preview Engine:** Write HTML/CSS/JS and see the results instantly in an isolated iframe.
*   **Cookie Persistence:** Brax intelligently intercepts `document.cookie` requests from inside the iframe, stores them locally in your markdown file, and re-injects them on the next load.
*   **Mobile-First Design:** Features a beautiful sliding bottom-sheet editor for mobile devices, complete with safe-area support for notched phones.
*   **Zero UI Clutter:** The interface remains completely clean. Control everything seamlessly via the Command Palette.
*   **Auto-Save:** Changes are automatically debounced and saved back to the underlying `.md` file.
*   **Highly Optimized:** Prevents iOS auto-zoom, handles cross-origin restrictions gracefully, and cleans up memory leaks perfectly when closed.

### 📖 Use Cases
- **Rapid Prototyping:** Quickly test UI components or CSS layouts without leaving Obsidian.
- **Interactive Widgets:** Create calculators, mini-dashboards, or interactive checklists.
- **Web Games:** Run simple HTML5/JS games directly inside your vault.
- **Educational Snippets:** Keep a library of interactive coding tutorials.
- **Stateful Web Apps:** Test web apps that rely on cookies or session states.

### 📦 Installation
**From Obsidian Community Plugins (Recommended):**
1. Go to **Settings** → **Community Plugins**.
2. Turn off **Safe Mode**.
3. Click **Browse**, search for `Brax`, install and enable it.

**Manual Installation:**
1. Download `main.js`, `styles.css`, and `manifest.json` from the [Releases Page](https://github.com/Im-Hugo/obsidian-brax/releases).
2. Create a folder named `brax` in your vault's `.obsidian/plugins/` directory.
3. Copy the files into that folder and restart Obsidian.

### 🛠️ How It Works
Brax uses a special Markdown format to separate your code from your data:
```markdown
---
brax-app: true
---

#cookies
{ "user_session": "abc123" }

#code
<!DOCTYPE html>
<html>
<body>
    <h1>Hello World!</h1>
    <script>document.cookie = "user_session=abc123";</script>
</body>
</html>
```

### ⌨️ Available Commands
| Command | Description |
| :--- | :--- |
| **Brax: Create new Brax app** | Opens a modal to name and write a new HTML application. |
| **Brax: Edit current Brax app** | Opens a large modal to edit the HTML code. |
| **Brax: Toggle code editor** | Slides the inline code editor up from the bottom. |

### 📱 Mobile Experience
*   **Touch-Friendly:** Inputs set to `16px` to prevent iOS auto-zoom.
*   **Safe Areas:** Respects `env(safe-area-inset-*)` for notched phones.
*   **No Touch Hijacking:** Uses Command Palette toggle for a smooth mobile experience.
*   **Sliding Panels:** The code editor acts like a native bottom sheet.

### ⚙️ Technical Deep Dive: The Cookie Engine
Standard iframes block `document.cookie` due to `SameSite` policies. Brax solves this by dynamically rewriting your code. It overrides `document.cookie` using `Object.defineProperty`:
1.  **Get:** Returns locally stored cookies from the markdown file.
2.  **Set:** Intercepts the cookie and sends a secure `postMessage` to the parent window.
3.  **Save:** The parent window triggers a debounced save to the `.md` file.

---

<a id="فارسی"></a>
## ✨ مستندات فارسی

### چرا براکس (Brax)؟
با وجود اینکه ابسیدین برای نوشتن مارک‌داون فوق‌العاده است، اما از پردازش و تعامل با برنامه‌های وب زنده پشتیبانی نمی‌کند. بلوک‌های کد HTML در ابسیدین کاملاً ایستا و بی‌روح هستند.

**براکس با تزریق یک محیط مرورگر ایزوله، تعاملی و کاملاً سندباکس شده مستقیماً به فضای کار شما، این مشکل را حل می‌کند.** برخلاف نمایش‌دهنده‌های ساده HTML، براکس دارای یک **موتور اختصاصی رهگیری کوکی** است؛ به این معنی که برنامه‌های وبی که به وضعیت (State)، سشن یا لاگین نیاز دارند، می‌توانند به درستی داخل یادداشت‌های شما کار کنند.

### 🎯 ویژگی‌های کلیدی
*   **موتور پیش‌نمایش زنده:** کدهای HTML/CSS/JS را بنویسید و بلافاصله نتیجه را در یک iframe ایزوله ببینید.
*   **ماندگاری کوکی‌ها:** براکس به طرز هوشمندانه‌ای درخواست‌های `document.cookie` را از داخل فریم رهگیری می‌کند، آن‌ها را در فایل مارک‌داون شما ذخیره می‌کند و در بارگذاری بعدی دوباره تزریق می‌کند.
*   **طراحی اول-موبایل:** دارای یک ویرایشگر لغزان زیبا برای دستگاه‌های موبایل، با پشتیبانی کامل از نواحی امن (Safe Area) برای گوشی‌های بریده دار (Notch).
*   **بدون شلوغی رابط کاربری:** رابط کاربری کاملاً تمیز می‌ماند. همه چیز را به صورت یکپارچه از طریق پالت فرمان (Command Palette) کنترل کنید.
*   **ذخیره خودکار:** تغییرات به صورت خودکار (Debounced) در فایل `.md` ذخیره می‌شوند تا فشاری به سیستم وارد نشود.
*   **بهینه‌سازی شده:** از زوم خودکار در iOS جلوگیری می‌کند، محدودیت‌های Cross-origin را به زیبایی مدیریت می‌کند و نشت حافظه (Memory leak) را هنگام بسته شدن به طور کامل پاکسازی می‌کند.

### 📖 موارد استفاده
- **نمونه‌سازی سریع:** تست سریع کامپوننت‌های رابط کاربری یا طرح‌بندی‌های CSS بدون ترک ابسیدین.
- **ویجت‌های تعاملی:** ساخت ماشین‌حساب، داشبوردهای مینی یا چک‌لیست‌های تعاملی.
- **بازی‌های وب:** اجرای بازی‌های ساده HTML5/JS مستقیماً داخل خزانه‌ی شما.
- **قطعات آموزشی:** نگهداری کتابخانه‌ای از آموزش‌های کدنویسی تعاملی که دانش‌آموزان بتوانند با آن‌ها بازی کنند.
- **اپلیکیشن‌های دارای وضعیت:** تست اپلیکیشن‌های وبی که به کوکی‌ها یا وضعیت‌های سشن وابسته‌اند.

### 📦 نحوه نصب
**از طریق پلاگین‌های جامعه ابسیدین (توصیه می‌شود):**
1. به **Settings** (تنظیمات) → **Community Plugins** بروید.
2. حالت **Safe Mode** را خاموش کنید.
3. روی **Browse** کلیک کنید، `Brax` را جستجو کرده، نصب و فعال کنید.

**نصب دستی:**
1. فایل‌های `main.js`، `styles.css` و `manifest.json` را از [صفحه ریلیزها](https://github.com/Im-Hugo/obsidian-brax/releases) دانلود کنید.
2. یک پوشه به نام `brax` در مسیر `.obsidian/plugins/` خزانه‌ی خود بسازید.
3. فایل‌ها را در آن پوشه کپی کنید و ابسیدین را ری‌استارت کنید.

### 🛠️ نحوه کارکرد
براکس از یک فرمت مارک‌داون خاص برای جدا کردن کد شما از داده‌ها استفاده می‌کند:
```markdown
---
brax-app: true
---

#cookies
{ "user_session": "abc123" }

#code
<!DOCTYPE html>
<html>
<body>
    <h1>سلام دنیا!</h1>
    <script>document.cookie = "user_session=abc123";</script>
</body>
</html>
```

### ⌨️ دستورات موجود
دسترسی از طریق پالت فرمان (`Ctrl+P` یا `Cmd+P`):

| دستور | توضیحات |
| :--- | :--- |
| **Brax: Create new Brax app** | یک مودال برای نام‌گذاری و نوشتن یک اپلیکیشن HTML جدید باز می‌کند. |
| **Brax: Edit current Brax app** | یک مودال بزرگ برای ویرایش کدهای HTML اپلیکیشن فعلی باز می‌کند. |
| **Brax: Toggle code editor** | ویرایشگر کد را از پایین صفحه به بالا می‌لغزاند (مناسب برای موبایل). |

### 📱 تجربه موبایل
*   **دوست‌دار لمس:** فیلدهای ورودی روی `16px` تنظیم شده‌اند تا از زوم خودکار آزاردهنده در iOS جلوگیری شود.
*   **نواحی امن:** از `env(safe-area-inset-*)` برای گوشی‌های دارای بریدگی (Dynamic Island) پیروی می‌کند.
*   **بدون اختلال در لمس:** به دلیل دزدیدن رویدادهای لمسی توسط موبایل در iframe، براکس به طور عمدی از سوایپ روی موبایل استفاده نکرده و فقط از طریق Command Palette کار می‌کند تا تجربه‌ای نرم داشته باشید.
*   **پنل‌های لغزان:** ویرایشگر کد در موبایل مانند یک برگه پایینی (Bottom Sheet) بومی با انیمیشن‌های نرم عمل می‌کند.

### ⚙️ نگاه فنی: موتور کوکی
فریم‌های استاندارد به دلیل سیاست‌های `SameSite` دسترسی به `document.cookie` را مسدود می‌کنند. براکس این مشکل را با بازنویسی پویای کد شما قبل از تزریق به فریم حل می‌کند. با استفاده از `Object.defineProperty` ویژگی `document.cookie` را دور می‌زند:
1.  **دریافت (Get):** کوکی‌های ذخیره شده محلی را از فایل مارک‌داون برمی‌گرداند.
2.  **تنظیم (Set):** کوکی را رهگیری کرده و یک `postMessage` امن به پنجره اصلی (ابسیدین) می‌فرستد.
3.  **ذخیره (Save):** پنجره اصلی وضعیت را به‌روزرسانی کرده و یک ذخیره خودکار با تاخیر (Debounced) را در فایل `.md` انجام می‌دهد.

---

<div align="center">

## 🛠️ Development & Contributing | توسعه و مشارکت

Want to contribute? It's built with TypeScript and ESBuild. 
Check the [Issues page](https://github.com/Im-Hugo/obsidian-brax/issues) to start.

## 📜 License | لایسنس
This project is licensed under the MIT License.
این پروژه تحت لایسنس MIT منتشر شده است.

**Made with ❤️ for the Obsidian Community**
**ساخته شده با ❤️ برای جامعه ابسیدین**

</div>
```

بعد از ذخیره کردن این فایل با نام `README.md` می‌تونی بری سراغ آپلود کردنش توی گیت‌هاب! (همون مرحله ۳ که گفتم). این فایل به شدت تو چشم تیم بررسی‌کننده آبسیدین می‌چرخه چون هم استاندارد جهانی داره و هم به کاربرای ایرانی اهمیت میده! 🌟
