# Test Cases — Parts-Kronos5 (Web)

Версия: 1.1  
Окружение по умолчанию: Chrome (desktop), https://parts-kronos5.ru/

## Стандарт оформления
Порядок секций внутри тест-кейса:
1) Метаданные (US/Module/Type/Priority/Severity)  
2) Preconditions  
3) Test Data  
4) Steps  
5) Expected Result  
6) Postconditions  

---

## Suites

### 1) Smoke Suite — Auth
Минимальный набор для проверки работоспособности фичи авторизации.
- TC-AUTH-001
- TC-AUTH-002
- TC-AUTH-005
- TC-AUTH-006
- TC-AUTH-007
- TC-REC-001
- TC-REG-001
- TC-REG-011

### 2) Smoke Suite — Search
Минимальный набор для проверки работоспособности поиска.
- TC-SRCH-001
- TC-SRCH-002
- TC-SRCH-005
- TC-AI-001
- TC-AI-002
- TC-AI-007

---

### 3) Regression Suite — Auth
- TC-AUTH-001 … TC-AUTH-007
- TC-REC-001 … TC-REC-003
- TC-REG-001 … TC-REG-013

### 4) Regression Suite — Search
- TC-SRCH-001 … TC-SRCH-006
- TC-TAGS-001 … TC-TAGS-002
- TC-AI-001 … TC-AI-010

---

### 5) Validation Suite
- TC-AUTH-002
- TC-AUTH-003
- TC-AUTH-004
- TC-REC-002
- TC-REG-002
- TC-REG-003
- TC-REG-004
- TC-REG-005
- TC-REG-006
- TC-REG-007
- TC-REG-011
- TC-AI-002
- TC-AI-003
- TC-AI-004
- TC-AI-005
- TC-AI-006

### 6) Negative Suite
- TC-AUTH-005
- TC-REC-002
- TC-REG-010
- TC-REG-013
- TC-SRCH-003
- TC-AI-010

---

## Files

- `auth-login.md` — Login (Email only): TC-AUTH-001 … TC-AUTH-007  
- `auth-recovery.md` — Password recovery (Email only): TC-REC-001 … TC-REC-003  
- `auth-registration.md` — Registration (+7/+375 + SMS code): TC-REG-001 … TC-REG-013  
- `search-text.md` — Text search: TC-SRCH-001 … TC-SRCH-006  
- `search-tags.md` — Tags/уточнения: TC-TAGS-001 … TC-TAGS-002  
- `search-photo-ai.md` — AI Photo Search: TC-AI-001 … TC-AI-010  
