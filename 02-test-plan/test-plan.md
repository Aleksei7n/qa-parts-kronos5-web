# Test Plan (Light) — Parts-Kronos5 Web

## 0. Objective
Проверить готовность ключевых пользовательских сценариев Auth и Search для использования в production (функциональность, валидации, ошибки, базовая стабильность UI).

## 1. Scope
Тестируем:
- Auth: Login / Registration / Password recovery
- Search: поиск по строке, теги, empty state, поиск по фото (форма/валидации)

## 2. Test items
- Web UI (формы и модальные окна Auth)
- Страница/блок результатов поиска
- Интеграция UI с бэкендом на уровне пользовательских действий (без глубокого API-тестирования)

## 3. Test approach
- Smoke: проверка доступности основных форм и запуск ключевых сценариев
- Functional: позитивные/негативные проверки, валидации полей
- UI sanity: тексты ошибок/состояния кнопок/переходы
- Retest: повторная проверка исправленных дефектов

## 4. Test types
- Functional (positive/negative)
- UI/UX sanity (ошибки, подсказки, состояния кнопок)
- Basic navigation
- Basic security sanity (маски ввода, минимальные ограничения пароля)

## 5. Test environment
- Browser: Chrome (desktop)
- URL: https://parts-kronos5.ru/
- Test data: тестовые email/телефон (обезличено)

## 6. Entry / Exit criteria
Entry:
- Сайт доступен
- Фичи включены (формы/модальные окна открываются)

Exit:
- Пройден smoke по Auth + Search
- Выполнены запланированные тесты, заведены баги с severity/priority
- Сформирован Test Summary Report

## 7. Suspension / Resume criteria
- Тестирование приостанавливается при недоступности сайта или блокирующем дефекте (Blocker) без обходного пути.
- Возобновляется после восстановления сайта/фикса дефекта или при наличии workaround.

## 8. Deliverables
- Checklists / Test cases
- Bug reports
- Test Summary Report

## 9. Risks / Dependencies
- SMS/почта могут быть отключены (проверяем UI-валидации и сообщения вместо фактической доставки).
- Валидации и ответы могут зависеть от бэкенда (возможны 5xx/ошибки сервера).
