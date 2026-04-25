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

## Проверка после деплоя

- [ ] https://easypay.thenextgen.store — открывается, hero видна
- [ ] Секция «Кто мы» — био Андрея отображается
- [ ] CTA-кнопки ведут на @easypay_onboarding_bot
