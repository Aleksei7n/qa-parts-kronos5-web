# Test Summary Report — Parts-Kronos5 (Web)

Версия: 1.1  
Проект: https://parts-kronos5.ru/  
Окружение по умолчанию: **Chrome (desktop)**; для SMS — **iOS (Messages)**.  
Тип прогона: Manual (UI).  
Основание: `01-requirements/user-stories.md`, `02-test-plan/test-plan.md`, `04-test-cases/*`, `05-bug-reports/*`.

---

## 1. Build / Run Information

- **Run Date:** 2025-11-05  
- **URL:** https://parts-kronos5.ru/  
- **Browser:** Chrome (desktop)  
- **OS:** macOS  
- **Additional:** iOS (Messages) — проверка получения SMS в рамках регистрации  
- **Run Owner:** Aleksei (Manual QA)

---

## 2. Scope Tested (в рамках Test Plan)

### In scope
- **Auth**
  - Login (Email only)
  - Registration (+7/+375 + SMS code)
  - Password recovery (Email only)
- **Search**
  - Text search (Enter / click “лупа”)
  - Results layout + counter
  - Tags/suggestions
  - Empty state + “Перейти в каталог”
  - AI Photo Search (форма/валидации/обработка/результат/ошибки)

### Out of scope (по тест-плану)
- Оплата/доставка/личный кабинет — **не тестировались как функциональные фичи**, кроме UI-дефекта в блоке выбора города доставки (BUG-005) и дефекта валидаций на странице оформления (BUG-007), зафиксированных как наблюдения при исследовательском проходе.

---

## 3. Test Suites Executed

- **Smoke Suite — Auth:** выполнен (TC-AUTH-001, TC-AUTH-002, TC-AUTH-005, TC-AUTH-006, TC-AUTH-007, TC-REC-001, TC-REG-001, TC-REG-011)  
- **Smoke Suite — Search:** выполнен (TC-SRCH-001, TC-SRCH-002, TC-SRCH-005, TC-AI-001, TC-AI-002, TC-AI-007)  
- **Regression Suite — Auth:** частично (в зависимости от доступности SMS/почты)  
- **Regression Suite — Search:** частично (AI photo search зависит от сервиса обработки и тестовых изображений)  
- **Validation Suite / Negative Suite:** частично (ограничения стенда/интеграций)

---

## 4. Test Results Summary

- **Planned:** 35  
- **Executed:** 22  
- **Passed:** 16  
- **Failed:** 6  
- **Blocked:** 0  
- **Not Run:** 13  

**Комментарии к неполному прогону:**
- Часть тестов по регистрации/восстановлению зависит от доступности SMS/Email на стенде и стабильности интеграций.
- Для AI Photo Search требуются эталонные изображения (match/nomatch) и стабильная обработка.

---

## 5. Key Defects (по итогам прогона)

| ID | Title (short) | Severity | Priority | Area |
|---|---|---:|---:|---|
| **BUG-001** | Search results: карточки в одну колонку вместо сетки | Major | P1 | Search |
| **BUG-002** | Search results: изображения товаров не загружаются | Major | P1 | Search |
| **BUG-003** | Search results: отсутствует CTA «Смотреть все результаты» (UX) | Minor | P3 | Search |
| **BUG-004** | Search results: отображается `undefined` в карточках | Minor | P2 | Search |
| **BUG-005** | Delivery selector: крестик перекрывает название страны | Minor | P3 | Delivery UI |
| **BUG-006** | Registration: SMS приходит от «ReklaManiya» (риск доверия/спама) | Major | P1 | Auth/Registration |
| **BUG-007** | Checkout: обязательные поля не подсвечиваются/ошибки не перечислены полностью | Major | P1 | Cart/Checkout |

---

## 6. Risk Assessment / Notes

- **SMS/Email интеграции** могут быть ограничены на стенде: часть сценариев может быть непроверяема без тестового провайдера/логов.  
- **AI Photo Search** зависит от внешнего сервиса обработки изображений: возможны ложные отрицания/таймауты — нужно согласовать критерии качества и набор тестовых изображений.
- **Search defects (BUG-001..BUG-004)** потенциально влияют на конверсию, так как ухудшают восприятие выдачи и доверие к карточкам товара.
- **Registration SMS sender (BUG-006)** — репутационный риск (пользователь может игнорировать SMS/считать спамом), возможный рост отказов на шаге регистрации.
- **Checkout validation (BUG-007)** — UX-риск, может повышать отказы на этапе оформления.

---

## 7. Exit Criteria Status

- [x] Стенд доступен / фичи открываются  
- [x] Пройден Smoke по Auth + Search  
- [x] Сформирован список багов с приоритетами  
- [x] Подготовлен Test Summary Report

---

## 8. Recommendations (Next steps)

- Исправить критичные для конверсии дефекты выдачи поиска (BUG-001, BUG-002) в приоритетном порядке.
- Согласовать UX-требование по CTA «Смотреть все результаты» (BUG-003) и поведение при отсутствии данных (`undefined`) (BUG-004).
- Для регистрации согласовать брендирование/отправителя SMS и антиспам-настройки (BUG-006).
- Улучшить валидации формы оформления заказа и сообщения об ошибках (BUG-007).
