
---

# 🗂 چک‌لیست فرانت‌اند (Front-End Checklist)

چک‌لیست فرانت‌اند فهرستی جامع از تمام عناصری است که پیش از راه‌اندازی وب‌سایت یا صفحه HTML خود در محیط تولید (production) باید داشته باشید یا تست کنید.

**سایر چک‌لیست‌ها:**

- [🎮 چک‌لیست عملکرد فرانت‌اند](https://github.com/thedaviddias/Front-End-Performance-Checklist#---------front-end-performance-checklist-)
- [💎 چک‌لیست طراحی فرانت‌اند](https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist)

> [!TIP]
> ⭐️ الگوهای UX مناسب برای توسعه‌دهندگان که کاش زودتر می‌دانستید. 👉 [الگوهای UX برای توسعه‌دهندگان](https://uxpatterns.dev/fa) ⭐️

## 📚 فهرست مطالب

- [روش استفاده](#روش-استفاده)
- [Head](#head)
- [HTML](#html)
- [وب‌فونت‌ها](#وب‌فونت‌ها)
- [CSS](#css)
- [جاوااسکریپت](#جاوااسکریپت)
- [دسترسی‌پذیری](#دسترسی‌پذیری)

## روش استفاده؟

<!-- prettier-ignore-start -->
> [!IMPORTANT]
> **سلب مسئولیت:** این چک‌لیست بر اساس سال‌ها تجربه توسعه‌دهندگان فرانت‌اند و با اضافه شدن مواردی از سایر چک‌لیست‌های متن‌باز تهیه شده است.
<!-- prettier-ignore-end -->

تمامی موارد موجود در **چک‌لیست فرانت‌اند** برای اکثر پروژه‌ها الزامی هستند، اما برخی عناصر را می‌توان حذف کرد یا ضروری نیستند (مثلاً در یک برنامه وب مدیریتی، ممکن است به فید RSS نیاز نداشته باشید). ما استفاده از **۳ سطح انعطاف** را انتخاب کرده‌ایم:

- ![Low][low_img] نشان می‌دهد که آن آیتم توصیه می‌شود اما در شرایط خاصی قابل حذف است.
- ![Medium][medium_img] نشان می‌دهد که آن آیتم بسیار توصیه می‌شود اما ممکن است در موارد بسیار خاص قابل حذف باشد. با این حال، حذف این عناصر می‌تواند بر عملکرد یا سئو تأثیر منفی بگذارد.
- ![High][high_img] نشان می‌دهد که آن آیتم تحت هیچ شرایطی قابل حذف نیست. حذف این عناصر ممکن است منجر به اختلال در صفحه یا ایجاد مشکلات دسترسی‌پذیری و سئو شود. تست باید در درجه اول روی این عناصر متمرکز باشد.

برخی از منابع دارای شکلک‌هایی هستند که به شما کمک می‌کنند نوع محتوا یا کمکی را که ممکن است در چک‌لیست پیدا کنید، درک کنید:

- 📖: مستندات یا مقاله
- 🛠: ابزار آنلاین / ابزار تست
- 📹: رسانه یا محتوای ویدئویی

## Head

<!-- prettier-ignore-start -->
> [!NOTE]
> می‌توانید [فهرستی از همه چیزهایی](https://github.com/joshbuchea/HEAD) که ممکن است در `<head>` یک سند HTML یافت شود را پیدا کنید.
<!-- prettier-ignore-end -->

### متا تگ (Meta tag)

- [ ] **DOCTYPE:** ![High][high_img] نوع سند (Doctype) HTML5 است و در بالای تمام صفحات HTML شما قرار دارد.

<!-- prettier-ignore-start -->
```html
<!doctype html><!-- HTML5 -->
```
<!-- prettier-ignore-end -->

- 📖
  [تعیین رمزگذاری کاراکتر - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

_دو متا تگ بعدی (Charset و Viewport) باید ابتدا در head قرار گیرند._

- [ ] **Charset:** ![High][high_img] رمزگذاری کاراکتر (UTF-8) به درستی اعلام شده است.

<!-- prettier-ignore-start -->
```html
<!-- تنظیم رمزگذاری کاراکتر برای سند -->
<meta charset="utf-8">
```
<!-- prettier-ignore-end -->

- [ ] **Viewport:** ![High][high_img] ناحیه دید (viewport) به درستی اعلام شده است.

<!-- prettier-ignore-start -->
```html
<!-- Viewport برای طراحی وب واکنش‌گرا -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```
<!-- prettier-ignore-end -->

- [ ] **Title:** ![High][high_img] در همه صفحات از عنوان استفاده شده است (سئو: گوگل عرض پیکسلی کاراکترهای استفاده شده در عنوان را محاسبه می‌کند و آن را بین ۴۷۲ تا ۴۸۲ پیکسل قطع می‌کند. محدودیت کاراکتری متوسط حدود ۵۵ کاراکتر است).

```html
<!-- عنوان سند -->
<title>عنوان صفحه کمتر از 55 کاراکتر</title>
```

- 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
- 🛠 [تولیدگر قطعه SERP](https://www.sistrix.com/serp-snippet-generator/)

- [ ] **Description:** ![High][high_img] یک متا description ارائه شده است، منحصر به فرد است و بیش از ۱۵۰ کاراکتر ندارد.

<!-- prettier-ignore-start -->
```html
<!-- Meta Description -->
<meta name="description" content="توضیحات صفحه کمتر از 150 کاراکتر">
```
<!-- prettier-ignore-end -->

- 📖
  [Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

- [ ] **Favicons:** ![Medium][medium_img] هر favicon ایجاد شده و به درستی نمایش داده می‌شود. اگر فقط یک `favicon.ico` دارید، آن را در ریشه سایت خود قرار دهید. معمولاً نیازی به استفاده از هیچ نشانه‌گذاری ندارید. با این حال، همچنان یک روش خوب است که با استفاده از مثال زیر به آن لینک دهید. امروزه، **فرمت PNG نسبت به `.ico` توصیه می‌شود** (ابعاد: 32x32 پیکسل).

<!-- prettier-ignore-start -->
```html
<!-- Favicon استاندارد -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- فرمت favicon توصیه شده -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
<!-- فرمت مدرن favicon توصیه شده (برای مرورگرهای قدیمی توصیه نمی‌شود) -->
<link rel="icon" type="image/svg+xml" href="https://example.com/favicon.svg">
```
<!-- prettier-ignore-end -->

- 🛠 [تولیدگر Favicon](https://www.favicon-generator.org/)
- 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
- 📖 [برگه تقلب Favicon](https://github.com/audreyr/favicon-cheat-sheet)
- 📖 [Favicons، Touch Icons، Tile Icons و غیره. به کدام یک نیاز دارید؟ - CSS Tricks](https://css-tricks.com/favicon-quiz/)
- 📖 [Favicon های PNG - caniuse](https://caniuse.com/link-icon-png)

- [ ] **متا تگ برنامه وب اپل (Apple Web App Meta):** ![Low][low_img] متا تگ‌های اپل وجود دارند.

<!-- prettier-ignore-start -->
```html
<!-- Apple Touch Icon (حداقل 200x200 پیکسل) -->
<link rel="apple-touch-icon" href="/custom-icon.png">

<!-- برای اجرای برنامه وب در تمام صفحه -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- استایل نوار وضعیت (مقادیر موجود را در متا تگ‌های پشتیبانی شده در زیر ببینید) -->
<!-- بدون داشتن متا تگ قبلی تأثیری ندارد -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
```
<!-- prettier-ignore-end -->

- 📖 [پیکربندی برنامه‌های وب](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)
- 📖 [متا تگ‌های پشتیبانی شده](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

- [ ] **کاشی‌های ویندوز (Windows Tiles):** ![Low][low_img] کاشی‌های ویندوز وجود دارند و لینک شده‌اند.

<!-- prettier-ignore-start -->
```html
<!-- کاشی‌های مایکروسافت -->
<meta name="msapplication-config" content="browserconfig.xml">
```
<!-- prettier-ignore-end -->

حداقل نشانه‌گذاری xml مورد نیاز برای فایل `browserconfig.xml` به شرح زیر است:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

<!-- prettier-ignore-start -->
- 📖 [مرجع طرح پیکربندی مرورگر](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/dn320426(v=vs.85))
<!-- prettier-ignore-end -->

- [ ] **Canonical:** ![Medium][medium_img] از `rel="canonical"` برای جلوگیری از محتوای تکراری استفاده کنید.

<!-- prettier-ignore-start -->
```html
<!-- کمک به جلوگیری از مشکلات محتوای تکراری -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-read.html">
```
<!-- prettier-ignore-end -->

- 📖
  [استفاده از URL‌های متعارف - راهنمای کنسول جستجوی گوگل](https://support.google.com/webmasters/answer/139066?hl=en)
- 📖
  [۵ اشتباه رایج با rel=canonical - وبلاگ Google Webmaster](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### تگ‌های HTML

- [ ] **ویژگی زبان (Language attribute):** ![High][high_img] ویژگی `lang` وب‌سایت شما مشخص شده و به زبان صفحه فعلی مرتبط است.

```html
<html lang="fa"></html>
```

- [ ] **ویژگی جهت (Direction attribute):** ![Medium][medium_img] جهت خواندن روی تگ `html` مشخص شده است (می‌توان از آن روی تگ HTML دیگری نیز استفاده کرد).

```html
<html dir="rtl">
  <!-- ... -->
</html>
```

- 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

- [ ] **زبان جایگزین (Alternate language):** ![Low][low_img] تگ زبان وب‌سایت شما مشخص شده و به زبان صفحه فعلی مرتبط است.

<!-- prettier-ignore-start -->
```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```
<!-- prettier-ignore-end -->

- [ ] **x-default:** ![Low][low_img] تگ زبان وب‌سایت شما برای صفحات فرود بین‌المللی.

```html
<link rel="alternate" href="https://example.com/" hreflang="x-default" />
```

- 📖 [x-default - Google](https://webmasters.googleblog.com/2013/04/x-default-hreflang-for-international-pages.html)

- [ ] **نظرات شرطی (Conditional comments):** ![Low][low_img] در صورت نیاز، نظرات شرطی برای IE وجود دارند.

- 📖
  [درباره نظرات شرطی (اینترنت اکسپلورر) - MSDN - Microsoft](<https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx>)

- [ ] **فید RSS:** ![Low][low_img] اگر پروژه شما یک وبلاگ است یا دارای مقالاتی است، یک لینک RSS ارائه شده است.

- [ ] **CSS بحرانی (CSS Critical):** ![Medium][medium_img] CSS بحرانی (یا "بالای چین") تمام CSS های استفاده شده برای رندر کردن بخش قابل مشاهده صفحه را جمع‌آوری می‌کند. قبل از فراخوانی اصلی CSS شما و بین `<style></style>` در یک خط (کوچک‌سازی شده) تعبیه می‌شود.

- 🛠 [Critical توسط Addy Osmani در GitHub](https://github.com/addyosmani/critical) این کار را خودکار می‌کند.

- [ ] **ترتیب CSS:** ![High][high_img] همه فایل‌های CSS قبل از هر فایل جاوااسکریپتی در `<head>` بارگیری می‌شوند (به جز مواردی که گاهی اوقات فایل‌های JS به صورت ناهمزمان در بالای صفحه شما بارگیری می‌شوند).

### متا شبکه‌های اجتماعی (Social meta)

با استفاده از [Meta Tags](https://metatags.io/) متا تگ‌های شبکه‌های اجتماعی خود را به طور خودکار تجسم و تولید کنید.

**_Facebook OG_** و **_Twitter Cards_** برای هر وب‌سایتی بسیار توصیه می‌شوند. سایر تگ‌های رسانه‌های اجتماعی را می‌توان در نظر گرفت اگر حضور خاصی در آن‌ها هدف گذاری کرده‌اید و می‌خواهید از نمایش صحیح اطمینان حاصل کنید.

- [ ] **Facebook Open Graph:** ![Low][low_img] تمام Open Graph (OG) فیس‌بوک تست شده‌اند و هیچ کدام گم نشده یا دارای اطلاعات نادرست نیست. تصاویر باید حداقل ۶۰۰ در ۳۱۵ پیکسل باشند، اگرچه ۱۲۰۰ در ۶۳۰ پیکسل توصیه می‌شود.

<!-- prettier-ignore-start -->
> [!NOTE]
> استفاده از `og:image:width` و `og:image:height` ابعاد تصویر را به خزنده (crawler) مشخص می‌کند تا بتواند تصویر را فوراً بدون نیاز به دانلود ناهمزمان و پردازش آن، رندر کند.
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="عنوان محتوا">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="توضیحات اینجا" />
<meta property="og:site_name" content="نام سایت">
<meta property="og:locale" content="fa_IR">
<!-- تگ‌های بعدی اختیاری اما توصیه می‌شوند -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```
<!-- prettier-ignore-end -->

- 📖 [راهنمای اشتراک‌گذاری برای وب‌مسترها](https://developers.facebook.com/docs/sharing/webmasters/)
- 📖 [بهترین روش‌ها - اشتراک‌گذاری](https://developers.facebook.com/docs/sharing/best-practices/)
- 🛠 صفحه خود را با [تست‌کننده OG فیس‌بوک](https://developers.facebook.com/tools/debug/) تست کنید.

- [ ] **Twitter Card:** ![Low][low_img]

<!-- prettier-ignore-start -->
```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@account_site">
<meta name="twitter:creator" content="@account_individual">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="عنوان محتوا">
<meta name="twitter:description" content="توضیحات محتوا کمتر از 200 کاراکتر">
<meta name="twitter:image" content="https://example.com/image.jpg">
```
<!-- prettier-ignore-end -->

- 📖
  [شروع کار با کارت‌ها — توسعه‌دهندگان توییتر](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
- 🛠 صفحه خود را با [اعتبارسنج کارت توییتر](https://cards-dev.twitter.com/validator) تست کنید.

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## HTML

### بهترین روش‌ها (Best practices)

- [ ] **المان‌های معنایی HTML5:** ![High][high_img] المان‌های معنایی HTML5 به درستی استفاده شده‌اند (header، section، footer، main و...).

- 📖 [مرجع HTML](http://htmlreference.io/)

- [ ] **صفحات خطا:** ![High][high_img] صفحه خطای ۴۰۴ و ۵xx وجود دارند. به یاد داشته باشید که صفحات خطای ۵xx باید CSS خود را یکپارچه داشته باشند (بدون فراخوانی خارجی روی سرور فعلی).

- [ ] **Noopener:** ![Medium][medium_img] در صورت استفاده از لینک‌های خارجی با `target="_blank"`، لینک شما باید دارای ویژگی `rel="noopener"` باشد تا از حملات tab nabbing جلوگیری شود. اگر نیاز به پشتیبانی از نسخه‌های قدیمی فایرفاکس دارید، از `rel="noopener noreferrer"` استفاده کنید.

- 📖 [درباره rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

- [ ] **پاکسازی نظرات:** ![Low][low_img] کدهای غیر ضروری باید قبل از ارسال صفحه به محیط تولید حذف شوند.

### تست HTML

- [ ] **انطباق با W3C:** ![High][high_img] همه صفحات باید با اعتبارسنج W3C تست شوند تا مشکلات احتمالی در کد HTML شناسایی شوند.

- 🛠 [اعتبارسنج W3C](https://validator.w3.org/)

- [ ] **HTML Lint:** ![High][high_img] از ابزارهایی برای کمک به تجزیه و تحلیل مشکلات احتمالی در کد HTML خود استفاده کنید.

- 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/)
- 🛠 [webhint](https://webhint.io/)

- [ ] **بررسی لینک‌ها:** ![High][high_img] هیچ لینک شکسته‌ای در صفحه شما وجود ندارد، تأیید کنید که خطای ۴۰۴ ندارید.

- 🛠 [بررسی لینک W3C](https://validator.w3.org/checklink)

- [ ] **تست Adblockerها:** ![Medium][medium_img] وب‌سایت شما محتوای خود را با فعال بودن adblockerها به درستی نشان می‌دهد (می‌توانید پیامی برای تشویق افراد به غیرفعال کردن adblocker خود ارائه دهید).

- 📖
  [استفاده از AdBlocking در محیط توسعه خود](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## وب‌فونت‌ها (Webfonts)

> [!NOTE]
> استفاده از وب‌فونت‌ها ممکن است باعث Flash Of Unstyled Text/Flash Of Invisible Text شود - استفاده از فونت‌های جایگزین (fallback) و/یا استفاده از بارگیرنده‌های وب‌فونت (webfont loaders) را برای کنترل رفتار در نظر بگیرید.

- 📖 [ملاحظات فنی گوگل در مورد وب‌فونت‌ها](https://developers.google.com/fonts/docs/technical_considerations)

- [ ] **فرمت وب‌فونت:** ![High][high_img] فرمت‌های WOFF، WOFF2 و TTF توسط همه مرورگرهای مدرن پشتیبانی می‌شوند.

- 📖 [WOFF - قالب فونت وب باز - Caniuse](https://caniuse.com/woff).
- 📖 [WOFF 2.0 - قالب فونت وب باز - Caniuse](https://caniuse.com/woff2).
- 📖 [TTF/OTF - پشتیبانی فونت TrueType و OpenType](https://caniuse.com/ttf)
- 📖 [استفاده از @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

- [ ] **سایز وب‌فونت:** ![High][high_img] اندازه وب‌فونت‌ها از ۲ مگابایت تجاوز نمی‌کند (همه واریانت‌ها شامل می‌شوند).

- [ ] **بارگیرنده وب‌فونت:** ![Low][low_img] رفتار بارگیری را با یک بارگیرنده وب‌فونت کنترل کنید.

- 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## CSS

> **توجه:** به [راهنمای CSS](https://cssguidelin.es/) و [راهنمای Sass](https://sass-guidelin.es/) که توسط اکثر توسعه‌دهندگان فرانت‌اند دنبال می‌شود، نگاهی بیندازید. اگر در مورد ویژگی‌های CSS تردید دارید، می‌توانید از [مرجع CSS](http://cssreference.io/) بازدید کنید. همچنین یک [راهنمای کدنویسی](http://codeguide.co/) کوتاه برای سازگاری وجود دارد.

- [ ] **طراحی وب واکنش‌گرا:** ![High][high_img] وب‌سایت از طراحی وب واکنش‌گرا استفاده می‌کند.
- [ ] **CSS چاپ:** ![Medium][medium_img] یک استایل‌شیت چاپ ارائه شده است و در هر صفحه صحیح است.
- [ ] **پیش‌پردازنده‌ها:** ![Low][low_img] پروژه شما از یک پیش‌پردازنده CSS استفاده می‌کند (مانند [Sass](http://sass-lang.com/)، [Less](http://lesscss.org/)، [Stylus](http://stylus-lang.com/)).
- [ ] **شناسه منحصر به فرد:** ![High][high_img] اگر از IDها استفاده می‌شود، برای یک صفحه منحصر به فرد هستند.
- [ ] **Reset CSS:** ![High][high_img] از یک reset CSS (reset، normalize یا reboot) استفاده شده است و به روز است. _(اگر از یک فریمورک CSS مانند Bootstrap یا Foundation استفاده می‌کنید، یک Normalize از قبل در آن گنجانده شده است.)_

- 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
- 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
- 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

- [ ] **پیشوند JS:** ![Low][low_img] همه کلاس‌ها (یا idهایی که در فایل‌های جاوااسکریپت استفاده می‌شوند) با **js-** شروع می‌شوند و در فایل‌های CSS استایل دهی نشده‌اند.

```html
<div id="js-slider" class="my-slider">
  <!-- یا -->
  <div id="id-used-by-cms" class="js-slider my-slider"></div>
</div>
```

- [ ] **CSS توکار یا خطی:** ![High][high_img] به هیچ وجه از تعبیه CSS در تگ‌های `<style>` یا استفاده از CSS خطی (inline) خودداری کنید: فقط برای دلایل معتبر استفاده کنید (مثلاً تصویر پس زمینه برای اسلایدر، CSS بحرانی).
- [ ] **پیشوندهای فروشنده:** ![High][high_img] از پیشوندهای فروشنده CSS استفاده شده و بر اساس سازگاری مرورگر مورد پشتیبانی شما، به درستی تولید می‌شوند.

- 🛠 [Autoprefixer CSS آنلاین](https://autoprefixer.github.io/)

### عملکرد (Performance)

- [ ] **الحاق (Concatenation):** ![High][high_img] فایل‌های CSS در یک فایل واحد الحاق شده‌اند _(برای HTTP/2 نه)_.
- [ ] **کوچک‌سازی (Minification):** ![High][high_img] همه فایل‌های CSS کوچک‌سازی (minified) شده‌اند.
- [ ] **غیر مسدودکننده:** ![Medium][medium_img] فایل‌های CSS باید غیر مسدودکننده باشند تا از زمان بردن DOM برای بارگیری جلوگیری شود.

- 📖 [loadCSS توسط filament group](https://github.com/filamentgroup/loadCSS)
- 📖 [مثال preload CSS با استفاده از loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **CSS استفاده نشده:** ![Low][low_img] CSS های استفاده نشده را حذف کنید.

- 🛠 [UnCSS Online](https://uncss-online.com/)
- 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
- 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
- 🛠 [پوشش Chrome DevTools](https://developer.chrome.com/docs/devtools/coverage/)

### تست CSS

- [ ] **Stylelint:** ![High][high_img] همه فایل‌های CSS یا SCSS بدون هیچ خطایی هستند.

- 🛠 [stylelint، یک linter برای CSS](https://stylelint.io/)
- 📖 [راهنمای Sass](https://sass-guidelin.es/)

- [ ] **طراحی وب واکنش‌گرا:** ![High][high_img] همه صفحات در نقاط شکست (breakpoints) زیر تست شده‌اند: ۳۲۰px، ۷۶۸px، ۱۰۲۴px (با توجه به آنالیزهای شما می‌تواند بیشتر/متفاوت باشد). **بررسی کننده واکنش‌گرایی -**

  - 🛠 [Am I Responsive?](http://ami.responsivedesign.is/)
  - 🛠 [تست سازگاری با موبایل](https://search.google.com/test/mobile-friendly)
  - 🛠 [تست کننده طراحی وب‌سایت واکنش‌گرا](https://responsivedesignchecker.com/)

- [ ] **اعتبارسنج CSS:** ![Medium][medium_img] CSS تست شده و خطاهای مربوطه تصحیح شده‌اند.

- 🛠 [اعتبارسنج CSS](https://jigsaw.w3.org/css-validator/)

- [ ] **مرورگرهای دسکتاپ:** ![High][high_img] همه صفحات در تمام مرورگرهای دسکتاپ فعلی تست شده‌اند (سافاری، فایرفاکس، کروم، اینترنت اکسپلورر، اج...).
- [ ] **مرورگرهای موبایل:** ![High][high_img] همه صفحات در تمام مرورگرهای موبایل فعلی تست شده‌اند (مرورگر بومی، کروم، سافاری...).
- [ ] **سیستم عامل‌ها:** ![High][high_img] همه صفحات در تمام سیستم عامل‌های فعلی تست شده‌اند (ویندوز، اندروید، iOS، مک...).

- [ ] **وفاداری به طراحی:** ![Low][low_img] بسته به پروژه و کیفیت طرح‌های اولیه (creatives)، ممکن است از شما خواسته شود که به طراحی نزدیک باشید. می‌توانید از برخی ابزارها برای مقایسه طرح‌های اولیه با پیاده‌سازی کد خود و اطمینان از سازگاری استفاده کنید.

> [Pixel Perfect - افزونه کروم](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

- [ ] **جهت خواندن:** ![High][high_img] در صورت نیاز به پشتیبانی، همه صفحات برای زبان‌های LTR و RTL باید تست شوند.

- 📖
  [ساخت برنامه‌ها و وب‌سایت‌های آگاه از RTL: بخش ۱ - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
- 📖
  [ساخت برنامه‌ها و وب‌سایت‌های آگاه از RTL: بخش ۲ - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## تصاویر (Images)

> **توجه:** برای درک کامل بهینه‌سازی تصویر، کتاب الکترونیکی رایگان **[بهینه‌سازی ضروری تصویر](https://images.guide/)** از Addy Osmani را بررسی کنید.

### بهترین روش‌ها

- [ ] **بهینه‌سازی:** ![High][high_img] همه تصاویر برای رندر شدن در مرورگر بهینه‌سازی شده‌اند. می‌توان از فرمت WebP برای صفحات حیاتی (مانند صفحه اصلی) استفاده کرد.

- 🛠 [Imagemin](https://github.com/imagemin/imagemin)
- 🛠 از [ImageOptim](https://imageoptim.com/) برای بهینه‌سازی رایگان تصاویر خود استفاده کنید.
- 🛠 از [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing) برای بهینه‌سازی تصویر در زمان واقعی استفاده کنید.
- 🛠 [TinyPNG](https://tinypng.com/) تصاویر png، apng (png پویا) و jpg را با افت کیفیت بسیار کم بهینه می‌کند. نسخه رایگان و پولی موجود است.
- 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) فشرده‌سازی شبیه jpg برای تصاویر شفاف با استفاده از ماسک svg.
- 🛠 [SVGO](https://github.com/svg/svgo) یک ابزار مبتنی بر Nodejs برای بهینه‌سازی فایل‌های گرافیکی برداری SVG.
- 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) یک نسخه رابط کاربر گرافیکی مبتنی بر وب از SVGO برای بهینه‌سازی svgهای شما به صورت آنلاین.

- [ ] **Picture/Srcset:** ![Medium][medium_img] از picture/srcset برای ارائه مناسب‌ترین تصویر برای نمایشگر فعلی کاربر استفاده می‌کنید.

- 📖 [چگونه تصاویر واکنش‌گرا با srcset بسازیم](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

- [ ] **Retina:** ![Low][low_img] تصاویر طرح‌بندی 2x یا 3x را ارائه می‌دهید، از نمایشگر retina پشتیبانی می‌کنید.
- [ ] **Sprite:** ![Medium][medium_img] تصاویر کوچک در یک فایل sprite قرار دارند (در مورد آیکون‌ها، می‌توانند در یک تصویر SVG sprite باشند).
- [ ] **ویژگی‌های Width و Height:** ![High][high_img] اگر اندازه نهایی تصویر رندر شده مشخص است، ویژگی‌های `width` و `height` را روی `<img>` تنظیم کنید (برای اندازه‌گذاری CSS قابل حذف است).
- [ ] **متن جایگزین (Alternative text):** ![High][high_img] همه `<img>` دارای یک متن جایگزین (alt) هستند که تصویر را از نظر بصری描述 می‌دهد.

- 📖 [متن‌های جایگزین: راهنمای نهایی](https://axesslab.com/alt-texts/)

- [ ] **بارگذاری تنبل (Lazy loading):** ![Medium][medium_img] تصاویر به صورت تنبل (lazy) بارگذاری می‌شوند (یک fallback با `<noscript>` همیشه ارائه می‌شود).
  - 🛠 [polyfill بارگذاری تنبل بومی](https://github.com/mfranzke/loading-attribute-polyfill/)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## جاوااسکریپت (JavaScript)

### بهترین روش‌ها

- [ ] **جاوااسکریپت توکار (Inline):** ![High][high_img] هیچ کد جاوااسکریپتی به صورت توکار (مخلوط با کد HTML شما) ندارید.
- [ ] **الحاق (Concatenation):** ![High][high_img] فایل‌های جاوااسکریپت الحاق شده‌اند.
- [ ] **کوچک‌سازی (Minification):** ![High][high_img] فایل‌های جاوااسکریپت کوچک‌سازی شده‌اند (می‌توانید پسوند `.min` را اضافه کنید).

- 📖 [کوچک‌سازی منابع (HTML، CSS و جاوااسکریپت)](https://developers.google.com/speed/docs/insights/MinifyResources)

- [ ] **امنیت جاوااسکریپت:** ![High][high_img]

- 📖
  [دستورالعمل‌هایی برای توسعه برنامه‌های امن با استفاده از جاوااسکریپت](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

- [ ] **تگ `noscript`:** ![Medium][medium_img] اگر نوع اسکریپت در صفحه پشتیبانی نمی‌شود یا اگر اسکریپت در مرورگر در حال حاضر خاموش است، از تگ `<noscript>` در بدنه HTML استفاده کنید. این در برنامه‌های سنگین رندر سمت کلاینت مانند React.js مفید خواهد بود، [نمونه‌ها](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498) را ببینید.

```html
<noscript> برای اجرای این برنامه باید جاوااسکریپت را فعال کنید. </noscript>
```

- [ ] **غیر مسدودکننده:** ![Medium][medium_img] فایل‌های جاوااسکریپت با استفاده از `async` یا با استفاده از ویژگی `defer` به صورت ناهمزمان بارگیری می‌شوند.

- 📖 [حذف جاوااسکریپت مسدودکننده رندر](https://developers.google.com/speed/docs/insights/BlockingJS)

- [ ] **کتابخانه‌های JS بهینه و به روز شده:** ![Medium][medium_img] تمام کتابخانه‌های جاوااسکریپت استفاده شده در پروژه شما ضروری هستند (برای عملکردهای ساده، جاوااسکریپت ساده (Vanilla Javascript) را ترجیح دهید)، به آخرین نسخه خود به روز شده‌اند و جاوااسکریپت شما را با روش‌های غیر ضروری سنگین نمی‌کنند.

- 📖 [ممکن است به jQuery نیاز نداشته باشید](http://youmightnotneedjquery.com/)
- 📖 [جاوااسکریپت ساده (Vanilla JavaScript) برای ساخت برنامه‌های وب قدرتمند](https://plainjs.com/)

- [ ] **Modernizr:** ![Low][low_img] اگر نیاز به هدف قرار دادن برخی ویژگی‌های خاص دارید، می‌توانید از یک Modernizr سفارشی برای اضافه کردن کلاس‌ها در تگ `<html>` خود استفاده کنید.

- 🛠 [Modernizr خود را سفارشی کنید](https://modernizr.com/download?setclasses)

### تست جاوااسکریپت

- [ ] **ESLint:** ![High][high_img] هیچ خطایی توسط ESLint پرچم گذاری نمی‌شود (بر اساس پیکربندی یا قوانین استاندارد شما).

- 📖 [ESLint - ابزار linting قابل پلاگین برای جاوااسکریپت و JSX](https://eslint.org/)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## امنیت (Security)

### اسکن و بررسی وب‌سایت خود

- [securityheaders.io](https://securityheaders.io/)
- [رصدخانه توسط موزیلا](https://observatory.mozilla.org/)

### بهترین روش‌ها

- [ ] **HTTPS:** ![High][high_img] HTTPS در هر صفحه و برای تمام محتوای خارجی (پلاگین‌ها، تصاویر...) استفاده می‌شود.

- 🛠 [Let's Encrypt - گواهینامه‌های رایگان SSL/TLS](https://letsencrypt.org/)
- 🛠 [تست سرور SSL رایگان](https://www.ssllabs.com/ssltest/index.html)
- 📖 [امنیت انتقال سختگیرانه (HSTS)](http://caniuse.com/#feat=stricttransportsecurity)

- [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] هدر HTTP روی 'Strict-Transport-Security' تنظیم شده است.

- 🛠 [وضعیت و صلاحیت preload HSTS را بررسی کنید](https://hstspreload.org/)
- 📖
  [برگه تقلب امنیت انتقال سختگیرانه HTTP - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
- 📖
  [برگه تقلب محافظت از لایه حمل و نقل - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)

- [ ] **جعل درخواست بین سایتی (CSRF):** ![High][high_img] اطمینان حاصل می‌کنید که درخواست‌های انجام شده به سمت سرور شما مشروع هستند و از وب‌سایت/برنامه شما سرچشمه می‌گیرند تا از حملات CSRF جلوگیری شود.

- 📖
  [برگه تقلب جلوگیری از جعل درخواست بین سایتی (CSRF) - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)

- [ ] **اسکریپت بین سایتی (XSS):** ![High][high_img] صفحه یا وب‌سایت شما از مشکلات احتمالی XSS عاری است.

- 📖
  [برگه تقلب جلوگیری از XSS (اسکریپت بین سایتی) - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
- 📖
  [برگه تقلب جلوگیری از XSS مبتنی بر DOM - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)

- [ ] **گزینه‌های نوع محتوا (Content Type Options):** ![Medium][medium_img] از تلاش گوگل کروم و اینترنت اکسپلورر برای sniffing mime نوع محتوای پاسخ دور از چیزی که توسط سرور اعلام می‌شود، جلوگیری می‌کند.

- 📖
  [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

- [ ] **X-Frame-Options (XFO):** ![Medium][medium_img] از بازدیدکنندگان شما در برابر حملات clickjacking محافظت می‌کند.

- 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
- 📖 [RFC7034 - هدر فیلد HTTP X-Frame-Options](https://tools.ietf.org/html/rfc7034)

- [ ] **سیاست امنیت محتوا (Content Security Policy):** ![Medium][medium_img] نحوه بارگیری محتوا در سایت شما و مجوز بارگیری آن از کجا را تعریف می‌کند. همچنین می‌تواند برای محافظت در برابر حملات clickjacking استفاده شود.

- 📖
  [سیاست امنیت محتوا - مقدمه - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
- 📖 [برگه تقلب CSP - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
- 📖 [برگه تقلب CSP - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
- 📖 [مرجع سیاست امنیت محتوا](https://content-security-policy.com/)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## عملکرد (Performance)

### بهترین روش‌ها

- [ ] **اهدافی که باید به دست آیند:** ![Medium][medium_img] صفحات شما باید به این اهداف برسند:

  - اولین نقاشی معنی‌دار (First Meaningful Paint) زیر ۱ ثانیه
  - زمان تعامل (Time To Interactive) زیر ۵ ثانیه برای پیکربندی "متوسط" (یک اندروید ۲۰۰ دلاری در شبکه 3G کند با RTT 400ms و سرعت انتقال 400kbps) و زیر ۲ ثانیه برای بازدیدهای تکراری
  - اندازه فایل بحرانی زیر ۱۷۰ کیلوبایت gzipped

- 🛠 [تجزیه و تحلیل صفحه وب](https://tools.pingdom.com)
- 🛠 [WebPageTest](https://www.webpagetest.org/)
- 📖 [محدودیت اندازه: وب را سبک‌تر کنید](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **HTML کوچک‌سازی شده:** ![Medium][medium_img] HTML شما کوچک‌سازی (minified) شده است.

- [ ] **بارگذاری تنبل:** ![Medium][medium_img] تصاویر، اسکریپت‌ها و CSS باید به صورت تنبل (lazy) بارگذاری شوند تا زمان پاسخگویی صفحه فعلی بهبود یابد (جزییات را در بخش‌های مربوطه ببینید).

- [ ] **اندازه کوکی:** ![Medium][medium_img] اگر از کوکی‌ها استفاده می‌کنید، مطمئن شوید هر کوکی از ۴۰۹۶ بایت تجاوز نمی‌کند و نام دامنه شما بیش از ۲۰ کوکی ندارد.

- 📖 [مشخصات کوکی: RFC 6265](https://tools.ietf.org/html/rfc6265)
- 📖 [کوکی‌ها](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- 🛠 [محدودیت‌های کوکی مرورگر](http://browsercookielimits.squawky.net/)

- [ ] **اجزای شخص ثالث:** ![Medium][medium_img] iframeهای شخص ثالث یا اجزایی که به JS خارجی متکی هستند (مانند دکمه‌های اشتراک‌گذاری) در صورت امکان با اجزای استاتیک جایگزین می‌شوند، بنابراین تماس با APIهای خارجی را محدود کرده و فعالیت کاربر شما را خصوصی نگه می‌دارند.

- 🛠 [سازنده دکمه‌های اشتراک‌گذاری ساده](https://simplesharingbuttons.com/)

### آماده‌سازی برای درخواست‌های آینده

- 📖 [توضیح تکنیک‌های زیر](https://css-tricks.com/prefetching-preloading-prebrowsing/)

- [ ] **حل DNS:** ![Low][low_img] DNS سرویس‌های شخص ثالث که ممکن است مورد نیاز باشند، در زمان بیکاری با استفاده از `dns-prefetch` از قبل حل می‌شوند.

```html
<link rel="dns-prefetch" href="https://example.com" />
```

- [ ] **پیش‌اتصال (Preconnection):** ![Low][low_img] جستجوی DNS، دست دادن TCP و مذاکره TLS با سرویس‌هایی که به زودی مورد نیاز خواهند بود، در زمان بیکاری با استفاده از `preconnect` از قبل انجام می‌شود.

```html
<link rel="preconnect" href="https://example.com" />
```

- [ ] **پیش‌واکشی (Prefetching):** ![Low][low_img] منابعی که به زودی مورد نیاز خواهند بود (مانند تصاویر بارگذاری تنبل) در زمان بیکاری با استفاده از `prefetch` از قبل درخواست می‌شوند.

```html
<link rel="prefetch" href="image.png" />
```

- [ ] **پیش‌بارگیری (Preloading):** ![Low][low_img] منابع مورد نیاز در صفحه فعلی (مانند اسکریپت‌های قرار گرفته در انتهای `<body>`) از قبل با استفاده از `preload` بارگیری می‌شوند.

```html
<link rel="preload" href="app.js" />
```

- 📖
  [تفاوت بین prefetch و preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### تست عملکرد

- [ ] **Google PageSpeed:** ![High][high_img] همه صفحات شما تست شده‌اند (نه فقط صفحه اصلی) و امتیاز حداقل ۹۰ از ۱۰۰ را دارند.

- 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
- 🛠 [سرعت موبایل خود را با گوگل تست کنید](https://testmysite.withgoogle.com)
- 🛠 [WebPagetest - تست عملکرد و بهینه‌سازی وب‌سایت](https://www.webpagetest.org/)
- 🛠 [GTmetrix - بهینه‌سازی سرعت و عملکرد وب‌سایت](https://gtmetrix.com/)
- 🛠 [Speedrank - عملکرد وب‌سایت خود را بهبود بخشید](https://speedrank.app/)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## دسترسی‌پذیری (Accessibility)

> **توجه:** می‌توانید لیست پخش [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) را تماشا کنید. 📹

### بهترین روش‌ها

- [ ] **بهبود تدریجی (Progressive enhancement):** ![Medium][medium_img] عملکردهای اصلی مانند ناوبری اصلی و جستجو باید بدون فعال بودن جاوااسکریپت کار کنند.

- 📖 [فعال/غیرفعال کردن جاوااسکریپت در ابزارهای توسعه‌دهنده کروم](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **کنتراست رنگ:** ![Medium][medium_img] کنتراست رنگ باید حداقل WCAG AA (و برای موبایل AAA) را پاس کند.

- 🛠 [نسبت کنتراست](https://www.siegemedia.com/contrast-ratio)

#### سرعنوان‌ها (Headings)

- [ ] **H1:** ![High][high_img] همه صفحات دارای یک H1 هستند که عنوان وب‌سایت نیست.
- [ ] **سرعنوان‌ها:** ![High][high_img] سرعنوان‌ها باید به درستی و به ترتیب صحیح استفاده شوند (H1 تا H6).

- 📹
  [چرا سرعنوان‌ها و نشانه‌ها (landmarks) اینقدر مهم هستند -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### معنا (Semantics)

- [ ] **از انواع ورودی خاص HTML5 استفاده شده است:** ![Medium][medium_img] این امر به ویژه برای دستگاه‌های موبایل که صفحه کلیدها و ویجت‌های سفارشی شده برای انواع مختلف را نشان می‌دهند، مهم است.

- 📖 [انواع ورودی موبایل](http://mobileinputtypes.com/)

### فرم (Form)

- [ ] **برچسب (Label):** ![High][high_img] یک برچسب (label) با هر المان ورودی فرم مرتبط است. در صورتی که نمی‌توان برچسب را نمایش داد، به جای آن از `aria-label` استفاده کنید.

- 📖
  [استفاده از ویژگی aria-label - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### تست دسترسی‌پذیری

- [ ] **تست استانداردهای دسترسی‌پذیری:** ![High][high_img] از ابزار WAVE برای تست اینکه آیا صفحه شما استانداردهای دسترسی‌پذیری را رعایت می‌کند، استفاده کنید.

- 🛠 [تست Wave](http://wave.webaim.org/)

- [ ] **ناوبری با صفحه کلید:** ![High][high_img] وب‌سایت خود را تنها با استفاده از صفحه کلید خود در یک مرتبه قابل پیش‌بینی تست کنید. همه عناصر تعاملی قابل دسترسی و استفاده هستند.
- [ ] **خواننده صفحه (Screen-reader):** ![Medium][medium_img] همه صفحات با یک خواننده صفحه (VoiceOver، ChromeVox، NVDA یا Lynx) تست شده‌اند.
- [ ] **استایل فوکوس:** ![High][high_img] اگر فوکوس غیرفعال است، با یک وضعیت قابل مشاهده در CSS جایگزین می‌شود.

- 📹
  [مدیریت فوکوس - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## سئو (SEO)

- [ ] **Google Analytics:** ![Low][low_img] گوگل آنالیتیکس نصب شده و به درستی پیکربندی شده است.

- 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
- 🛠 [GA Checker (و دیگران)](http://www.gachecker.com/)

- [ ] **کنسول جستجو (Search Console):** ![Low][low_img] کنسول جستجو نصب شده و به درستی پیکربندی شده است. این یک سرویس رایگان ارائه شده توسط گوگل است که به شما کمک می کند حضور سایت خود را در نتایج جستجوی گوگل نظارت، حفظ و عیب‌یابی کنید.

- 🛠 [کنسول جستجو](https://search.google.com/search-console/about)

- [ ] **منطق سرعنوان‌ها:** ![Medium][medium_img] متن سرعنوان به درک محتوا در صفحه فعلی کمک می‌کند.

- 🛠 [Tota11y، تب Headings](http://khan.github.io/tota11y/#Try-it)

- [ ] **sitemap.xml:** ![High][high_img] یک فایل `sitemap.xml` وجود دارد و به کنسول جستجوی گوگل (قبلاً ابزارهای وب‌مستر گوگل) ارسال شده است.

- 🛠 [تولید کننده Sitemap](https://websiteseochecker.com/html-sitemap-generator/)

- [ ] **robots.txt:** ![High][high_img] فایل `robots.txt` صفحات را مسدود نمی‌کند.

- 🛠 robots.txt خود را با [ابزار تست robots گوگل](https://www.google.com/webmasters/tools/robots-testing-tool) تست کنید.

- [ ] **داده‌های ساختیافته (Structured Data):** ![High][high_img] صفحاتی که از داده‌های ساختیافته استفاده می‌کنند تست شده‌اند و بدون خطا هستند. داده‌های ساختیافته به خزنده‌ها کمک می‌کند محتوای صفحه فعلی را درک کنند.

- 📖
  [مقدمه‌ای بر داده‌های ساختیافته - جستجو - توسعه‌دهندگان گوگل](https://developers.google.com/search/docs/guides/intro-structured-data)
- 📖 [JSON-LD](https://json-ld.org/)
- 📖 [Microdata](https://www.w3.org/TR/microdata/)
- 🛠 صفحه خود را با [تست نتایج غنی (Rich Results Test)](https://search.google.com/test/rich-results) تست کنید.
- 🛠 فهرست کامل واژگانی که می‌توانند به عنوان داده ساختاریافته استفاده شوند. [سلسله مراتب کامل Schema.org](http://schema.org/docs/full.html)

- [ ] **Sitemap HTML:** ![Medium][medium_img] یک sitemap HTML ارائه شده است و از طریق یک لینک در فوتر وب‌سایت شما قابل دسترسی است.

- 📖 [دستورالعمل‌های Sitemap - پشتیبانی گوگل](https://support.google.com/webmasters/answer/183668?hl=en)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

---

## ترجمه‌ها (Translations)

چک‌لیست فرانت‌اند به زبان‌های دیگر نیز موجود است. با تشکر از همه مترجمان و کار فوق العاده آنها!

- 🇯🇵 ژاپنی: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
- 🇪🇸 اسپانیایی: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
- 🇨🇳 چینی: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
- 🇰🇷 کره‌ای: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
- 🇧🇷 پرتغالی: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
- 🇻🇳 ویتنامی: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
- 🇹🇼 چینی سنتی: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
- 🇫🇷 فرانسوی: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)
- 🇷🇺 روسی: [ungear/Front-End-Checklist](https://github.com/ungear/Front-End-Checklist)
- 🇹🇷 ترکی استانبولی: [eraycetinay/Front-End-Checklist](https://github.com/eraycetinay/Front-End-Checklist)
- 🇩🇪 آلمانی: [xfuture603/Front-End-Checklist](https://github.com/xFuture603/Front-End-Checklist)
- 🇵🇱 لهستانی: [mbiesiad/Front-End-Checklist](https://github.com/mbiesiad/Front-End-Checklist)
- 🇮🇩 اندونزیایی: [nniinnoo/Front-End-Checklist](https://github.com/nniinnoo/Front-End-Checklist)

## پشتیبانی (Support)

اگر سوال یا پیشنهادی دارید، در کمال تعجب با من در X تماس بگیرید:

- [X (formerly Twitter)](https://ddias.link/x)
- [گفتگو در Discord](https://ddias.link/discord)

## مشارکت‌کنندگان (Contributors)

این پروژه به لطف همه افرادی که مشارکت می‌کنند وجود دارد. ([مشارکت](https://github.com/thedaviddias/Front-End-Checklist/blob/main/CONTRIBUTING.md)).
<a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors"><img src="https://opencollective.com/front-end-checklist/contributors.svg?width=890" alt="Contributors" /></a>

## پشتیبانان (Backers)

از همه پشتیبانان ما سپاسگزاریم! 🙏 [[پشتیبان شوید](https://opencollective.com/front-end-checklist#backer)]

<a href="https://opencollective.com/front-end-checklist#backers" target="_blank"><img src="https://opencollective.com/front-end-checklist/backers.svg?width=890" alt="Backers" /></a>

## اسپانسرها (Sponsors)

با اسپانسر شدن از این پروژه حمایت کنید. لوگوی شما با لینک به وب‌سایتتان در اینجا نمایش داده می‌شود.
[[اسپانسر شوید](https://opencollective.com/front-end-checklist#sponsor)]

<a href="https://opencollective.com/front-end-checklist" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/1/avatar.svg" alt="Sponsors" /></a>

## مجوز (License)

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ بازگشت به بالا](#-فهرست-مطالب)**

[low_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/low.svg
[medium_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/medium.svg
[high_img]: https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/refs/heads/main/data/images/priority/high.svg

---
