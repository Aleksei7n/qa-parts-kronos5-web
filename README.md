# qa-parts-kronos5-web

QA case (Parts-Kronos5): **Auth (login/registration/recovery) + Search (text/tags/empty state) + AI Photo Search**.  
Репозиторий содержит артефакты тестирования: требования (user stories), тест-план, чек-листы, тест-кейсы, баг-репорты, отчёт о тестировании и матрицу покрытия.

**Project:** https://parts-kronos5.ru/  
**Default environment:** Chrome (desktop). Для SMS-сценариев — iOS (Messages).  
**Region:** RU/BY/KZ (телефоны +7 / +375)

---

## Quick navigation

- **Requirements:** `01-requirements/user-stories.md`
- **Test plan:** `02-test-plan/test-plan.md`
- **Checklists:** `03-checklists/`
- **Test cases:** `04-test-cases/README.md` (suites + ссылки на файлы)
- **Bug reports:** `05-bug-reports/README.md` + `05-bug-reports/bug-reports.md`
- **Test summary report:** `06-reports/test-summary-report.md`
- **Traceability matrix:** `07-traceability/traceability-matrix.md`

---

## Repository structure

### 01-requirements/
- `user-stories.md` — требования в формате **User Stories + AC (Acceptance Criteria)** и правила валидации.

### 02-test-plan/
- `test-plan.md` — **Test Plan (Light)**: scope, типы тестирования, окружение, критерии входа/выхода, риски.

### 03-checklists/
- `smoke-auth.md` — smoke-чек-лист по Auth (минимум для проверки работоспособности).
- `regression-search.md` — регрессионный чек-лист по Search (текстовый поиск, теги, empty state, фото).

### 04-test-cases/
- `README.md` — описание наборов тестов (Smoke/Regression/Validation/Negative) + списки ID.
- `auth-login.md` — тест-кейсы Login (Email only).
- `auth-recovery.md` — тест-кейсы Password recovery (Email only).
- `auth-registration.md` — тест-кейсы Registration (+7/+375 + SMS code).
- `search-text.md` — тест-кейсы Text search.
- `search-tags.md` — тест-кейсы Tags/suggestions.
- `search-photo-ai.md` — тест-кейсы AI Photo Search.

### 05-bug-reports/
- `README.md` — список багов с кратким описанием и ссылками на файлы/скриншоты.
- `bug-reports.md` — полный набор баг-репортов по стандарту.
- `assets-screenshots-bugs/` — доказательства (скриншоты), привязанные к BUG-ID.

### 06-reports/
- `test-summary-report.md` — результат тестирования (coverage, статистика, дефекты, риски/ограничения).

### 07-traceability/
- `traceability-matrix.md` — матрица покрытия **US → Test Cases** (и при необходимости **Bugs**).

---

## Conventions

- Идентификаторы:
  - **US-*** — user stories (requirements)
  - **TC-*** — test cases
  - **BUG-*** — bug reports
- **Priority (P0–P3)** и **Severity (Blocker–Trivial)** выставлены по e-commerce логике: влияние на конверсию, ключевой путь и воспроизводимость.
