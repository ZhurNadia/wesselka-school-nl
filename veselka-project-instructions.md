# ПРОЄКТ: Сайт школи «Веселка» (oekraienseschool.nl)

Українська суботня школа, Voorburg, Нідерланди. Односторінковий самодостатній
HTML/CSS/vanilla JS сайт, ~372 KB, без зовнішніх бібліотек.

Актуальний файл: `veselka-school.html` — завантажений у Project Knowledge.
Перед будь-якими змінами звіряйся з ним (view), а не з пам'яттю.

## СТЕК
HTML5 / CSS3 / vanilla JS. Google Fonts (Playfair Display + Nunito).
Google Maps Embed (без API key). Google Forms Embed. Зображення — WebP,
вбудовані як base64. Ніяких зовнішніх бібліотек.

## КОЛЬОРИ
```
--blu:  #1B4FBE
--blu2: #0f3490
--yel:  #F5C842
--hon:  #E8A020
--pch:  #FDE8CC
--crm:  #FFFBF4
```

## СТРУКТУРА (10 секцій, з ID-якорями)
nav · #home (hero + oval-карусель) · #about (2 розкривні картки) ·
#schedule (2 локації, розклад, календар субот 2026) · #events (картки + модалка) ·
#register (ціни + вбудована Google Form) · #gallery · #faq (акордеон) ·
#contact (карта перемикається кліком по картці) · footer

## КЛЮЧОВІ ФУНКЦІЇ (JS)
- `i18n` — об'єкт наприкінці `<script>`, ключі `uk/nl/en`, керується `setLang(lang)`
- `switchMap('fr')` / `switchMap('co')` — перемикання карти по кліку на картку локації (не вкладки)
- `ovalGo(n)`, `ovalAuto()` — oval-карусель у hero, 5 слайдів, автопрокрутка
- `toggleCard()` — розкривні картки "Про нас"
- Scroll reveal: клас `.fu` + `.vis` через IntersectionObserver
- Мобільне меню: `.mob-menu`, повноекранний overlay, бургер-анімація

## КОНТЕНТНІ ДАНІ (не вигадувати, брати звідси)
**Локації:**
- Fransstraat 16, 2274 AX Voorburg — заняття 11:20–14:20
- Van Tuyll van Serooskerkenstraat 2, 2273 CB Voorburg (Corbulo College) — 11:00–14:00

**Контакти:** +31 6 33 65 26 84 · oekraienseschool@gmail.com / info@oekraienseschool.nl ·
Facebook/Instagram (ua.school.wesselka)/YouTube

**Ціни/субота:** €18 (постійні резиденти) · €14 (Малятко, Зернятко) · €10 (тимчасовий захист)

**Форма реєстрації:** iframe, `https://docs.google.com/forms/d/e/1FAIpQLSeWM9Y8k8p1vt7oekHgyD0Qhr1wPzguv5mA2KEG5E1joQfTaQ/viewform?embedded=true`,
запасне посилання `forms.gle/y5wt8CvtMnz4p5Rq5`

**Розклад субот 2026:** повний список з канікулами/святами — див. окремо в чатах
(⬜ навчання · 🟠 канікули · 🔵 свята/вихідні · 🟡 особливі події, напр. 06/06 — 15 років школі)

## ПРАВИЛА РОБОТИ
- Зміни в HTML вносити через Python `re.sub` по всьому файлу, не переписувати вручну шматками
- Перед записом — перевірка контрольними echo/assert (файл закінчується `</html>`, ключові класи присутні)
- Логотип і фото — base64, для заміни перестискати через Python + PIL
- Не додавати Google Maps API key без явного запиту (зараз embed без ключа)

## НЕЗАВЕРШЕНО
- [ ] Хостинг (рекомендовано Netlify, drag-and-drop)
- [ ] Google Maps API ключ (опційно, для кращого відображення)
- [ ] Реальні фото в галерею замість emoji-плейсхолдерів
- [ ] Форма реєстрації на заходи (модалка) — поки без реальної відправки, треба Formspree або Google Form
- [ ] Оновлення карток подій — вручну в HTML, CMS не підключена

---
*Востаннє оновлено: 21 липня 2026. Розробка: Claude + Serhii.*
