# Test Cases — Search: Text Search

Версия: 1.1  
Окружение по умолчанию: Chrome (desktop), https://parts-kronos5.ru/

---

# SEARCH

## Text search

**TC-SRCH-001**  
Title: Поиск по строке запускается по Enter и показывает выдачу  
US: US-SRCH-1  
Module: Search  
Type: Functional  
Priority: P0  
Severity: Critical  

Preconditions:
- Открыта главная страница.

Test Data:
- Query: `фильтр`

Steps:
1) Найти поле поиска в шапке сайта.  
2) Ввести текст `фильтр`.  
3) Нажать Enter.  
4) Дождаться отображения результатов.  

Expected Result:
- Отображается выдача по запросу.  
- В выдаче присутствуют релевантные товары (если такие есть в каталоге).  

Postconditions: —  

---

**TC-SRCH-002**  
Title: Поиск по строке запускается по клику на “лупу”  
US: US-SRCH-1  
Module: Search  
Type: Functional  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта главная страница.

Test Data:
- Query: `масло`

Steps:
1) Ввести `масло` в поле поиска.  
2) Нажать на кнопку/иконку “лупа”.  
3) Дождаться выдачи.  

Expected Result:
- Отображается выдача по запросу.  

Postconditions: —  

---

**TC-SRCH-003**  
Title: Пустой запрос — поиск не выполняется  
US: US-SRCH-1  
Module: Search  
Type: Negative  
Priority: P2  
Severity: Minor  

Preconditions:
- Открыта главная страница.

Test Data: —  

Steps:
1) Очистить поле поиска, чтобы оно было пустым.  
2) Нажать Enter.  
3) Нажать “лупу” (если кликабельна при пустом поле).  

Expected Result:
- Поиск не выполняется (выдача не открывается/не меняется).  
- Сообщение “Ничего не найдено” для пустого запроса не отображается, если это не оговорено требованиями.  

Postconditions: —  

---

**TC-SRCH-004**  
Title: В выдаче отображается счетчик “Найдено товаров: X”  
US: US-SRCH-2  
Module: Search  
Type: UI  
Priority: P3  
Severity: Minor  

Preconditions:
- Выполнен поиск с результатами.

Test Data: —  

Steps:
1) На странице выдачи найти счетчик результатов.  
2) Проверить, что текст содержит “Найдено товаров:” и числовое значение X.  

Expected Result:
- Счетчик отображается и содержит число результатов.  

Postconditions: —  

---

**TC-SRCH-005**  
Title: При 0 результатов отображается “Ничего не найдено” и кнопка “Перейти в каталог”  
US: US-SRCH-4  
Module: Search  
Type: Functional  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта главная страница.

Test Data:
- Query: `qwertyqwertyqwerty`

Steps:
1) Ввести `qwertyqwertyqwerty` в поле поиска.  
2) Запустить поиск (Enter/лупа).  
3) Дождаться результата.  
4) Проверить наличие сообщения “Ничего не найдено”.  
5) Проверить наличие кнопки “Перейти в каталог”.  

Expected Result:
- Отображается empty state “Ничего не найдено”.  
- Кнопка “Перейти в каталог” присутствует и доступна.  

Postconditions: —  

---

**TC-SRCH-006**  
Title: Кнопка “Перейти в каталог” переводит пользователя в каталог  
US: US-SRCH-4  
Module: Search  
Type: Functional  
Priority: P2  
Severity: Minor  

Preconditions:
- Открыт empty state по результатам поиска.

Test Data: —  

Steps:
1) Нажать “Перейти в каталог”.  
2) Дождаться перехода.  
3) Проверить, что отображается каталог (URL/заголовок/карточки товаров).  

Expected Result:
- Происходит переход в каталог.  
- Каталог отображается корректно.  

Postconditions: —  
