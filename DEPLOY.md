# Deploy

## Структура проекта

| Компонент | Тип | Путь | Репозиторий |
|-----------|-----|------|-------------|
| easypay-landing | root repo | `/` | github.com/vanger-cat/easypay-landing |

## Автодеплой (при push в main)

| Приложение | Платформа | URL | Источник |
|------------|-----------|-----|----------|
| EasyPay Landing | GitHub Pages | https://easypay.thenextgen.store | `index.html` в корне |

CNAME → `easypay.thenextgen.store`. GitHub Pages раздаёт `index.html` напрямую из main.

## Agent readiness

- `robots.txt` и `sitemap.xml` лежат в корне репозитория и публикуются GitHub Pages как статические файлы.
- `index.md` — markdown-версия главной страницы для агентов; в HTML добавлен `rel="alternate"` на неё.
- Текущий прод отвечает заголовком `server: GitHub.com`, поэтому `Link` response headers и content negotiation по `Accept: text/markdown` нельзя включить только правками в этом репозитории.
- Чтобы закрыть эти два пункта анализатора, нужен edge-слой перед GitHub Pages: Cloudflare Worker, Cloudflare Snippet/Transform Rule с кастомными заголовками и переписыванием ответа, либо перенос на хостинг с управляемыми заголовками.

## Проверка после деплоя

- [ ] https://easypay.thenextgen.store — открывается, hero видна
- [ ] Секция «Кто мы» — био Андрея отображается
- [ ] CTA-кнопки ведут на @easypay_onboarding_bot
- [ ] https://easypay.thenextgen.store/robots.txt — `200 OK`
- [ ] https://easypay.thenextgen.store/sitemap.xml — `200 OK`
- [ ] https://easypay.thenextgen.store/index.md — `200 OK`
