# Traceability Matrix — Parts-Kronos5 (Web)

Версия: 1.1  
Проект: https://parts-kronos5.ru/  
Цель: обеспечить трассируемость **Requirements (User Stories)** → **Test Cases** → **Defects**.  
Окружение по умолчанию: Chrome (desktop); для SMS — iOS (Messages).

> Примечание: список дефектов привязан к функциональным областям и тестам, где они проявляются. Нумерация дефектов соответствует папке `05-bug-reports/`.

---

## Матрица трассируемости (US → Test Cases)

| User Story | Covered by Test Cases (IDs) | Notes / Related Defects |
|---|---|---|
| **US-LOGIN-1 — Вход (Login, Email only)** | TC-AUTH-001, TC-AUTH-002, TC-AUTH-003, TC-AUTH-004, TC-AUTH-005, TC-AUTH-006, TC-AUTH-007 | — |
| **US-LOGIN-2 — Восстановление пароля (Email only)** | TC-REC-001, TC-REC-002, TC-REC-003 | — |
| **US-REG-1 — Регистрация (+7/+375 + SMS code)** | TC-REG-001, TC-REG-002, TC-REG-003, TC-REG-004, TC-REG-006, TC-REG-007, TC-REG-008, TC-REG-009, TC-REG-010, TC-REG-011, TC-REG-012 | BUG-006 (репутационный риск отправителя SMS) |
| **US-REG-2 — Сообщения об ошибках / ошибки сервера** | TC-REG-005, TC-REG-013 | — |
| **US-SRCH-1 — Поиск по строке** | TC-SRCH-001, TC-SRCH-002, TC-SRCH-003 | BUG-001..BUG-004 (визуальная/данные выдачи в результатах поиска) |
| **US-SRCH-2 — Выдача результатов + блок поиска по фото** | TC-SRCH-004, TC-AI-001 | BUG-001..BUG-004 (выдача/карточки), BUG-003 (отсутствие CTA при выдаче — как UX-ожидание) |
| **US-SRCH-3 — Теги/подсказки уточнения** | TC-TAGS-001, TC-TAGS-002 | — |
| **US-SRCH-4 — Пустая выдача** | TC-SRCH-005, TC-SRCH-006 | — |
| **US-SRCH-5 — Поиск по фото: форма и валидации** | TC-AI-002, TC-AI-003, TC-AI-004, TC-AI-005, TC-AI-006 | — |
| **US-SRCH-6 — Поиск по фото: успешная обработка/результат** | TC-AI-007, TC-AI-008, TC-AI-009, TC-AI-010 | — |

---

## Coverage Summary (кратко)

- **Auth (Login/Recovery/Registration):** покрыто тестами TC-AUTH-001..TC-AUTH-007, TC-REC-001..TC-REC-003, TC-REG-001..TC-REG-013  
- **Search (Text/Tags/Empty):** покрыто тестами TC-SRCH-001..TC-SRCH-006, TC-TAGS-001..TC-TAGS-002  
- **AI Photo Search:** покрыто тестами TC-AI-001..TC-AI-010
