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
3. **[Веб-шрифты](#Веб-шрифты)**
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

### Лучшие практики

* [ ] **HTML5 Семантические теги:** ![Высокий][high_img] Семантические теги HTML5 используются правильно (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Страницы-ошибки:** ![Высокий][high_img] Страница с ошибкой 404 и 5xx существуют. Помните, что для страниц с ошибками 5xx стили CSS должны быть встроенными (без внешних вызовов на текущем сервере).

* [ ] **Noopener:** ![Средний][medium_img] В случаях, когда вы используете внешние ссылки с `target="_blank"`, они должны иметь атрибут `rel="noopener"`, предотвращающий возможные фишинг-атаки. Для старых версий Firefox используйте `rel="noopener noreferrer"`.

> * 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Удаление комментов:** ![Низкий][low_img] Ненужный код должен быть удален перед публикацией страницы.

### Тестирование HTML

* [ ] **W3C стандарты:** ![Высокий][high_img] Все страницы должны быть проверены на валидность стандартам W3C для определения возможных проблем в HTML коде.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![Высокий][high_img] Используйте инструменты для анализа HTML кода.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Проверка ссылок:** ![Высокий][high_img] На странице нет битых ссылок, удостовертесь, что нигде не выходит 404 ошибка.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Средний][medium_img] Ваш сайт должен корректно отображаться при включенном блокировщике рекламы (Вы также можете показать пользователю сообщение, призывающее отключить их блокировщик рекламы).



**[⬆ Вверх](#Содержание)**

---

## Веб-шрифты

> **Примечание:** При использовании веб-шрифтов могут появляться "вспышки" нестилизованного / невидимого текста. Удостоверьтесь в наличии резервных шрифтов и / или настройте загрузчик веб-шрифтов.

* [ ] **Формат веб-шрифтов:** ![Высокий][high_img] Форматы WOFF, WOFF2 и TTF поддерживаются всеми современными браузерами.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Размер веб-шрифтов:** ![Высокий][high_img] Размер веб-шрифта не превышает  2 Мб (все варианты включены).

* [ ] **Загрузчик веб-шрифтов:** ![Низкий][low_img] Контроль над загрузкой с помощью загрузчика веб-шрифтов.

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ Вверх](#Содержание)**

---

## CSS

> **Примечание:** Взгляните на [CSS guidelines](https://cssguidelin.es/) и [Sass Guidelines](https://sass-guidelin.es/) которым следует большинство фронтенд-разработчиков. Если у вас есть сомнения по поводу CSS-свойств, посетите [CSS Reference](http://cssreference.io/).

* [ ] **Отзывчивый веб-дизайн:** ![Высокий][high_img] На сайте используется отзывчивый веб-дизайн.
* [ ] **CSS для печати:** ![Средний][medium_img] Стили для печати присутствуют и корректны для каждой страницы.
* [ ] **Препроцессоры:** ![Низкий][low_img] Ваша страница использует CSS-препроцессор ([Sass](http://sass-lang.com/) предпочтителен).
* [ ] **Уникальные ID:** ![Высокий][high_img] Если в качестве селекторов используются ID, они являются уникальными на странице.
* [ ] **Сброс CSS:** ![Высокий][high_img] Сброс стилей (reset, normalize или reboot) используется и актуален. *(Если вы используете CSS-фреймворк типа Bootstrap или Foundation, Normalize уже включен в них.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS префикс:** ![Низкий][low_img] Все классы (или id- используемые в JavaScript-файлах) начинаются с **js-** и не стилизуются в CSS-файлах.

```html
<div id="js-slider" class="my-slider">
<!-- Или -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Встроенный или инлайновый CSS:** ![Высокий][high_img] Всеми силами избегайте включения CSS в тег `<style>` или использования инлайнового CSS: используйте их только по обоснованным причинам (например background-image для слайдера, критический CSS).
* [ ] **Вендорные префиксы:** ![Высокий][high_img] Вендорные префиксы CSS используются и сгенерированы в соответствии с вашей поддержкой версий браузеров.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Производительность

- [ ] **Конкатенация:** ![Высокий][high_img] CSS-файлы объединены в один файл. *(не для HTTP/2)*
- [ ] **Минификация:** ![Высокий][high_img] Все CSS-файлы минифицированы.
- [ ] **Non-blocking:** ![Средний][medium_img] CSS-файлы не должны блокировать загрузку страницы.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Неиспользуемый CSS:** ![Низкий][low_img] Неипользуемый CSS-код удален.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### Тестирование CSS 

* [ ] **Stylelint:** ![Высокий][high_img] Все CSS или SCSS-файлы без каких-либо ошибок.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Отзывчивый веб-дизайн:** ![Высокий][high_img] Все страницы протестированы на следующих разрешениях: 320px, 768px, 1024px (могут быть больше / отличаться в соответствии с вашей аналитикой).

* [ ] **CSS-валидатор:** ![Средний][medium_img] CSS-код протестирован и актуальные ошибки исправлены.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Десктопные браузеры:** ![Высокий][high_img] Все страницы протестированы во всех актуальных десктопных браузерах (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Мобильные браузеры:**  ![Высокий][high_img] Все страницы протестированы во всех актуальных мобильных браузерах (Native browser, Chrome, Safari...).
* [ ] **ОС:**  ![Высокий][high_img] Все страницы протестированы во всех актуальных операционных системах (Windows, Android, iOS, Mac...).

- [ ] **Pixel-perfect:** ![Высокий][high_img] Страницы близки к pixel-perfect. Вы можете быть не точны на 100%, но ваша страница должна быть близкой к макету.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Направление чтения:** ![Высокий][high_img] Все страницы должны быть протестированы на LTR и RTL языки, если таковые должны поддерживаться.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ Вверх](#Содержание)**

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
