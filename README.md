# Front-End Checklist-RU

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Front-End Checklist** - это исчерпывающий список всех элементов, которые вам нужно иметь / протестировать перед запуском вашего сайта / HTML-страницы в продакшн.

Список основан на многолетнем опыте фронтенд-разработчиков с дополнениями из различных опенсорсных чек-листов.

*Помочь проекту Front-End Checklist своим голосом и рекомендацией на Product Hunt*
[![](http://res.cloudinary.com/djnyaloac/image/upload/v1508896898/upvote-producthunt_vzys4c.jpg)](https://www.producthunt.com/posts/front-end-checklist)

## Содержание

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## Как использовать?

Все элементы **Front-End Checklist** рекомендуемы для большинства проектов, но некоторыми можно пренебречь, некоторые не являются существенными (например, вам не понадобится RSS-канал для веб-приложения, используемого для администрирования). Мы будем использовать 3 уровня важности:

* ![Низкий][low_img] означает, что элемент **рекомендуется**, но им можно пренебречь в некоторых частных случаях.
* ![Средний][medium_img] означает, что элемент **крайне рекомендуется**, но все-таки может быть не использован в некоторых очень частных случаях. Невключиение некоторых таких элементов может отрицательно повлиять на производительность и SEO.
* ![Высокий][high_img] означает, что элемент **не может быть пропущен** ни по какой причине. Вы можете нарушить работу страницы или вызвать проблемы с доступностью или SEO. Начинать тестирование необходимо с этих элементов.

У некоторых ресурсов есть иконка, соответсвтующая типу контента / помощи:

* 📖: документация или статья
* 🛠: онлайн-инструмент / инструмент тестирования
* 📹: медиа- или видео-контент

---

## Head

> **Примечание:** [Полный список](https://github.com/joshbuchea/HEAD) всего, что можно найти в теге `<head>`.

### Метатеги

* [ ] **Doctype:** ![Высокий][high_img] Doctype определен как HTML5 и находится вверху ваших HTML-страниц.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> * 📖 [Определение кодировки символов - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*Следующие 3 метатега (Charset, X-UA Compatible и Viewport) должны идти первыми в head.*

* [ ] **Charset:** ![Высокий][high_img] Кодировка (UTF-8) установлена верно.

```html
<!-- Установка кодировки документа -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Средний][medium_img] Метатег X-UA-Compatible установлен (Предназначен для указания версии Internet Explorer).

```html
<!-- Указание браузеру Internet Explorer использовать версию Edge -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> * 📖 [Определение устаревших режимов для веб-страницы (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![Высокий][high_img] Тег viewport установлен корректно.

```html
<!-- Viewport для адаптивного веб-дизайна -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![Высокий][high_img] Тег используется на всех страницах (SEO: Google высчитывает ширину символов, используемых в теге, оставляя первые 472-482 пикселя. В среднем тег ограничен длиной около 55 символов).

```html
<!-- Document Title -->
<title>Заголовок страницы менее 65 символов</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** ![Высокий][high_img] Метатег, отвечающий за описание, установлен, уникален и не более 150 символов.

```html
<!-- Meta Description -->
<meta name="description" content="Описание страницы менее 150 симолов">
```

> * 📖[Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** ![Средний][medium_img] Каждый фавикон установлен и выводится коректно. Если имеется только `favicon.ico`, расположите его в корне сайта. Обычно вам не надо будет использовать метку. Тем не менее до сих пор хорошей практикой является указание ссылки на фавикон, как в примере ниже. Сейчас, **рекомендуется использовать формат PNG** вместо формата `.ico` (разрешение: 32x32px).

```html
<!-- Стандартный фавикон -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Рекомендуемый формат фавикона -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Низкий][low_img] значок для Apple apple-mobile-web-app-capable установлен. *(Создавайте ваш Apple значок по крайней мере с разрешением 200x200px для поддержки всех разрешений, которые вам понадобятся)*

```html
<!-- Значок Apple -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> * 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Низкий][low_img] Windows-плитки установлены.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

Миниальные требования к xml-разметке для файла browserconfig.xml :

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

> * 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Средний][medium_img] Используйте `rel="canonical"`, чтобы избежать дублирования контента.

```html
<!-- Помогает избежать проблем с дублированием контента -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

> * 📖 [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [5 common mistakes with rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML теги

* [ ] **Атрибут языка:** ![Высокий][high_img] Атрибут `lang` на вашем сайте определен в соответствии с языком текущей страницы.

```html
<html lang="ru">
```

* [ ] **Атрибут направления:** ![Средний][medium_img] Направление текста определено в теге html (Для этого может использоваться еще один тег html).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Альтернативный язык:** ![Низкий][low_img] Язык вашего сайта определен и соответствует языку текущей страницы.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Комменты-условия:** ![Низкий][low_img] Комменты-условия для IE установлены, если есть необходимость.

> * 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS лента:** ![Низкий][low_img] Если ваш сайт является блогом или имеет статьи, RSS лента создана.

* [ ] **Критический CSS:** ![Средний][medium_img] CSS, который отвечает за отрисовку верхней части страницы и начинает загружаться сразу же одновременно с загрузкой страницы, называется критическим CSS. Он встраивается до вызова вашего основного CSS в тег  `<style></style>` в одну строку (минифицированый).
> * 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical) автоматизирует это

* [ ] **Порядок CSS:** ![Высокий][high_img] Все CSS-файлы загружаются до JavaScript-файлов в теге `<head>`. (За исключением некоторых случаев, когда JS-файлы загружаются асинхронно вверху вашей страницы).

### Социальные метатеги

***Facebook OG*** и ***Twitter Cards*** крайне рекомендуются на любом сайте. Метатеги остальных соцсетей могут быть добавлены, если вы целенаправленно собираетесь на них присутствовать.

* [ ] **Facebook Open Graph:** ![Низкий][low_img] Все метатеги Facebook Open Graph (OG) протестированы, и ни один не отсутствует или отражает некорректную информацию. Изобажения должны быть как минимум с разрешением 600 x 315 пикселей, 1200 x 630 пикселей рекомендуется.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Заголовок">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Описание">
<meta property="og:site_name" content="Название сайта">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Протестируйте ваш сайт с [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Низкий][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Протестируйте ваш сайт с [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ Вверх](#Содержание)**

---

## HTML

### Best practices

* [ ] **HTML5 Semantic Elements:** ![Высокий][high_img] HTML5 Semantic Elements are used appropriately (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** ![Высокий][high_img] Error 404 page and 5xx exist. Remember that the 5xx error pages need to have their CSS integrated (no external call on the current server).

* [ ] **Noopener:** ![Средний][medium_img] In case you are using external links with `target="_blank"`, your link should have a `rel="noopener"` attribute to prevent tab nabbing. If you need to support older versions of Firefox, use `rel="noopener noreferrer"`.

> * 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments:** ![Низкий][low_img] Unnecessary code needs to be removed before sending the page to production.

### HTML testing

* [ ] **W3C compliant:** ![Высокий][high_img] All pages need to be tested with the W3C validator to identify possible issues in the HTML code.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![Высокий][high_img] I use tools to help me analyze any issues I could have on my HTML code.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Link checker:** ![Высокий][high_img] There are no broken links in my page, verify that you don't have any 404 error.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Средний][medium_img] Your website shows your content correctly with adblockers enabled (You can provide a message encouraging people to disable their adblocker).



**[⬆ back to top](#table-of-contents)**

---

## Webfonts

* [ ] **Webfont format:** ![Высокий][high_img] WOFF, WOFF2 and TTF are supported by all modern browsers.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![Высокий][high_img] Webfont sizes don't exceed 2 MB (all variants included).

**[⬆ back to top](#table-of-contents)**

---

## CSS

> **Notes:** Take a look at [CSS guidelines](https://cssguidelin.es/) and [Sass Guidelines](https://sass-guidelin.es/) followed by most  Front-End developers. If you have a doubt about CSS properties, you can visit [CSS Reference](http://cssreference.io/).

* [ ] **Responsive Web Design:** ![Высокий][high_img] The website is using responsive web design.
* [ ] **CSS Print:** ![Средний][medium_img] A print stylesheet is provided and is correct on each page.
* [ ] **Preprocessors:** ![Низкий][low_img] Your page is using a CSS preprocessor ([Sass](http://sass-lang.com/) is preferred).
* [ ] **Unique ID:** ![Высокий][high_img] If IDs are used, they are unique to a page.
* [ ] **Reset CSS:** ![Высокий][high_img] A CSS reset (reset, normalize or reboot) is used and up to date. *(If you are using a CSS Framework like Bootstrap or Foundation, a Normalize is already included into it.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Низкий][low_img] All classes (or id- used in JavaScript files) begin with **js-** and are not styled into the CSS files.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Embedded or inline CSS:** ![Высокий][high_img] Avoid at all cost embeding CSS in `<style>` tags or using inline CSS: only use for valid reasons (e.g. background-image for slider, critical CSS).
* [ ] **Vendor prefixes:** ![Высокий][high_img] CSS vendor prefixes are used and are generated accordingly with your browser support compatibility.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performance

- [ ] **Concatenation:** ![Высокий][high_img] CSS files are concatenated in a single file. *(Not for HTTP/2)*
- [ ] **Minification:** ![Высокий][high_img] All CSS files are minified.
- [ ] **Non-blocking:** ![Средний][medium_img] CSS files need to be non-blocking to prevent the DOM from taking time to load.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Низкий][low_img] Remove unused CSS.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS testing

* [ ] **Stylelint:** ![Высокий][high_img] All CSS or SCSS files are without any errors.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![Высокий][high_img] All pages were tested at the folНизкийing breakpoints: 320px, 768px, 1024px (can be more / different according to your analytics).

* [ ] **CSS Validator:** ![Средний][medium_img] The CSS was tested and pertinent errors were corrected.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers:** ![Высокий][high_img] All pages were tested on all current desktop browsers (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Mobile Browsers:**  ![Высокий][high_img] All pages were tested on all current mobile browsers (Native browser, Chrome, Safari...).
* [ ] **OS:**  ![Высокий][high_img] All pages were tested on all current OS (Windows, Android, iOS, Mac...).

- [ ] **Pixel perfect:** ![Высокий][high_img] Pages are close to pixel perfect. Depending on the quality of the creatives, you may not be 100% accurate, but your page needs to be close to your template.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction:** ![Высокий][high_img] All pages need to be tested for LTR and RTL languages if they need to be supported.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## Images

> **Notes:** For a complete understanding of image optimization, check the free ebook **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### Best practices

* [ ] **Optimization:** ![Высокий][high_img] All images are optimized to be rendered in the browser. WebP format could be used for critical pages (like Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Picture/Srcset:** ![Средний][medium_img] You use picture/srcset to provide the most appropriate image for the current viewport of the user.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** ![Низкий][low_img] You provide layout images 2x or 3x, support retina display.
* [ ] **Sprite:** ![Средний][medium_img] Small images are in a sprite file (in the case of icons, they can be in an SVG sprite image).
* [ ] **Width and Height:** ![Высокий][high_img] Set `width` and `height` attributes on `<img>` if the final rendered image size is known (can be omitted for CSS sizing).
* [ ] **Alternative text:** ![Высокий][high_img] All `<img>` have an alternative text which describe the image visually.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** ![Средний][medium_img] Images are lazyloaded (A noscript fallback is always provided).

**[⬆ back to top](#table-of-contents)**

---

## JavaScript

### Best practices

* [ ] **JavaScript Inline:** ![Высокий][high_img] You don't have any JavaScript code inline (mixed with your HTML code).
* [ ] **Concatenation:** ![Высокий][high_img] JavaScript files are concatenated.
* [ ] **Minification:** ![Высокий][high_img] JavaScript files are minified (you can add the `.min` suffix).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **Non-blocking:** ![Средний][medium_img] JavaScript files are loaded asynchronously using `async` or deferred using `defer` attribute.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Низкий][low_img] If you need to target some specific features you can use a custom Modernizr to add classes in your `<html>` tag.

> * 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![Высокий][high_img] No errors are flagged by ESLint (based on your configuration or standards rules).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### Scan and check your web site

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Best practices

* [ ] **HTTPS:** ![Средний][medium_img] HTTPS is used on every pages and for all external content (plugins, images...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Средний][medium_img] The HTTP header is set to 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![Высокий][high_img] You ensure that requests made to your server-side are legitimate and originate from your website / app to prevent CSRF attacks.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![Высокий][high_img] Your page or website is free from XSS possible issues.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Средний][medium_img] Prevents Google Chrome and Internet Explorer from trying to mime-sniff the content-type of a response away from the one being declared by the server.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Средний][medium_img] Protects your visitors against clickjacking attacks.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### Best practices

- [ ] **Weight page:** ![Высокий][high_img] The weight of each page is between 0 and 500 KB.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Средний][medium_img] Your HTML is minified.
> * 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Средний][medium_img] Images, scripts and CSS need to be lazy loaded to improve the response time of the current page (See details in their respective sections).

* [ ] **Cookie size:** If you are using cookies be sure each cookie doesn't exceed 4096 bytes and your domain name doesn't have more than 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Third party components:** ![Средний][medium_img] Third party iframes or components relying on external JS (like sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping your users activity private.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Низкий][low_img] DNS of third-party services that may be needed are resolved in advance during idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Низкий][low_img] DNS lookup, TCP handshake and TLS negociation with services that will be needed soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Низкий][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Низкий][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`) in advance using `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![Высокий][high_img] All your pages were tested (not only the homepage) and have a score of at least 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **Notes:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Средний][medium_img] Major functionality like main navigation and search should work without JavaScript enabled.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Средний][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![Высокий][high_img] All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![Высокий][high_img] Headings should be used properly in the right order (H1 to H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![Высокий][high_img] `<header>` has `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` has `role="navigation"`.
- [ ] **Role main:** ![Высокий][high_img] `<main>` has `role="main"`.

> * 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semantics

- [ ] **Specific HTML5 input types are used:** ![Средний][medium_img] This is especially important for mobile devices that show customized keypads and widgets for different types.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![Высокий][high_img] A label is associated with each input form element. In case a label can't be displayed, use `aria-label` instead.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing

* [ ] **Accessibility standards testing:** ![Высокий][high_img] Use the WAVE tool to test if your page respects the accessibility standards.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![Высокий][high_img] Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Средний][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![Высокий][high_img] If the focus is disabled, it is replaced by visible state in CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![Высокий][high_img] Google Analytics is installed and correctly configured.
* [ ] **Headings logic:** ![Средний][medium_img] Heading text helps to understand the content in the current page.
* [ ] **sitemap.xml:** ![Высокий][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously Google Webmaster Tools).
* [ ] **robots.txt:** ![Высокий][high_img] The robots.txt is not blocking webpages.

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![Высокий][high_img] Pages using structured data are tested and are without errors. Structured data helps crawlers understand the content in the current page.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Heirarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Средний][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of your website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ back to top](#table-of-contents)**

---

## Translation

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)

---

## Front-End Checklist Badge

If you want to show you are following the rules of the Front-End Checklist, put this badge on your README file!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](http://frontendchecklist.com/) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

### Contributors

Check out all the super awesome [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Support

If you have any question or suggestion, don't hesitate to use Gitter or Twitter:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Twitter](https://twitter.com/thedaviddias)

## Authors

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
