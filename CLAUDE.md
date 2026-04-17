# EDYGE DECOR — Landing site

Құлсары қаласындағы «EDYGE DECOR» компаниясы үшін жасалған лендинг сайт. Компания үйдің сыртын полифасад және термопанельмен қаптау қызметін ұсынады.

## Стек

- Таза **HTML + CSS + JS** (фреймворксіз, билд қажет емес)
- Барлығы `index.html` файлында жиналған (inline CSS/JS)
- Сыртқы тәуелділіктер: тек Google Fonts (Inter, Manrope)
- Build қадамы жоқ — `index.html` файлын браузерде ашу жеткілікті

## Құрылымы

```
index.html          — бүкіл сайт (markup + styles + script)
img/                — барлық суреттер
  logo.png          — компания логотипі
  design-1..12.png  — дизайн галереясы (12 фото)
  result-1..3.png   — орындалған жұмыстар
  stone-1..8.png    — тас түрлері (6 жоқ, 7 файл бар)
.gitignore
```

## Маңызды ерекшеліктер

- **3 тіл:** KZ (default) / RU / EN. Аудармалар `index.html` ішіндегі `T` объектісінде. Элементтер `data-i18n` (мәтін) және `data-i18n-ph` (placeholder) арқылы белгіленеді. Таңдалған тіл `localStorage`-де сақталады.
- **Бренд түстері** логотиптен алынған:
  - `--slate: #3d4d5c`, `--slate-light: #5a7087`, `--accent: #6b8aa8`
  - `--bg-dark: #0f1419`, `--cream: #f5f2ec`
- **Галерея / нәтиже / тастар** DOM-ға JS арқылы `designs`, `results`, `stoneFiles` массивтерінен динамикалық жасалады.
- **Scroll reveal** — `IntersectionObserver` + `.reveal` кластары арқылы.
- **Форма** — өтінім WhatsApp-қа `wa.me/77029892022` сілтемесі арқылы жіберіледі (backend жоқ).

## Байланыс / контент

- Телефон: `+7 702 989 20 22` (WhatsApp та сол нөмір)
- Мекен-жай: Құлсары қ., Сариев к-сі, 84
- Жұмыс уақыты: 09:00–18:00
- Instagram: https://www.instagram.com/edyge_decor_kulsary
- 2GIS: https://2gis.kz/atyrau/geo/70030076572417971/54.004580,46.946612

## Deploy

- **GitHub repo:** https://github.com/garifollaarsen5-create/edyge-decor-kulsary (branch `main`)
- **Netlify:** GitHub repo-ға байланған. Тегін жаңарту үшін `main`-ге пуш жасау жеткілікті.

## Жиі өзгертетін жерлер

| Не керек | Қайда | Қалай |
|---|---|---|
| Байланыс номерін өзгерту | `index.html` | `77029892022` және `+7 702 989 20 22` мәтіндерін ауыстыру |
| Мекен-жайды өзгерту | `index.html` | `T.{kk,ru,en}['con.addrVal']` |
| Жаңа дизайн фото | `img/` + `index.html` | `img/design-N.png` қосып, `designs` массивіне қосу |
| Жаңа тас түрі | `img/` + `index.html` | `img/stone-N.png` қосып, `stoneFiles` массивіне `{src,name,size}` қосу |
| Жаңа тіл | `index.html` | `T` объектісіне жаңа ключ, `.lang-switch`-қа жаңа батырма |
| Жұмыс уақытын өзгерту | `index.html` | `T.*.['hero.badge']` және контакт блогындағы `09:00 – 18:00` |

## Жасамайтын нәрселер

- Файл атауларын кириллицаға қайтармау — Netlify/хостинг URL-кодтауда қателік беруі мүмкін, сондықтан барлық ассеттер ASCII-мен.
- Build tool (webpack / vite) қоспау — сайт әдейі «plain HTML» түрінде жасалған, зеро-конфиг деплой үшін.
