# Test Cases — Search: AI Photo Search

Версия: 1.1  
Окружение по умолчанию: Chrome (desktop), https://parts-kronos5.ru/

---

# AI PHOTO SEARCH

**TC-AI-001**  
Title: Открытие формы “Найдите запчасти по фото” из выдачи  
US: US-SRCH-2, US-SRCH-5  
Module: AI Photo Search  
Type: UI  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта выдача результатов поиска (по любому запросу).

Test Data: —  

Steps:
1) На странице выдачи найти блок “Найдите запчасти по фото”.  
2) Нажать на блок/кнопку открытия формы.  
3) Проверить, что открылась форма/модальное окно загрузки фото.  

Expected Result:
- Форма/модальное окно загрузки фото открывается корректно.  

Postconditions: —  

---

**TC-AI-002**  
Title: Кнопка “Отправить” disabled без загруженного файла  
US: US-SRCH-5  
Module: AI Photo Search  
Type: Validation  
Priority: P0  
Severity: Major  

Preconditions:
- Открыта форма загрузки фото.

Test Data: —  

Steps:
1) Убедиться, что файл не выбран/не загружен.  
2) Проверить состояние кнопки “Отправить”.  
3) Попробовать нажать на кнопку (если UI позволяет).  

Expected Result:
- “Отправить” disabled, отправка не выполняется.  

Postconditions: —  

---

**TC-AI-003**  
Title: Валидный формат JPG/JPEG (≤10 МБ) принимается, отправка доступна  
US: US-SRCH-5  
Module: AI Photo Search  
Type: Validation  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта форма загрузки фото.

Test Data:
- File: `photo.jpg` (JPG/JPEG, размер ≤10 МБ)

Steps:
1) Нажать “Выбрать файл”/область загрузки.  
2) Выбрать файл `photo.jpg`.  
3) Убедиться, что файл отображается как выбранный/загруженный.  
4) Проверить, что кнопка “Отправить” стала активной.  

Expected Result:
- Файл принимается.  
- “Отправить” enabled.  

Postconditions: —  

---

**TC-AI-004**  
Title: Валидный формат PNG (≤10 МБ) принимается, отправка доступна  
US: US-SRCH-5  
Module: AI Photo Search  
Type: Validation  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта форма загрузки фото.

Test Data:
- File: `photo.png` (PNG, размер ≤10 МБ)

Steps:
1) Выбрать файл `photo.png`.  
2) Убедиться, что файл принят системой.  
3) Проверить доступность “Отправить”.  

Expected Result:
- Файл принимается.  
- “Отправить” enabled.  

Postconditions: —  

---

**TC-AI-005**  
Title: Неподдерживаемый формат (например PDF/GIF) отклоняется с ошибкой  
US: US-SRCH-5  
Module: AI Photo Search  
Type: Validation  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта форма загрузки фото.

Test Data:
- File: `doc.pdf` / `image.gif`

Steps:
1) Попытаться выбрать файл `doc.pdf` (или `image.gif`).  
2) Наблюдать реакцию UI: отклонение файла/сообщение об ошибке.  
3) Проверить состояние “Отправить”.  

Expected Result:
- Файл неподдерживаемого формата не принимается.  
- Появляется понятное сообщение о неподдерживаемом формате.  
- “Отправить” disabled.  

Postconditions: —  

---

**TC-AI-006**  
Title: Файл больше 10 МБ отклоняется с ошибкой по размеру  
US: US-SRCH-5  
Module: AI Photo Search  
Type: Validation  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта форма загрузки фото.

Test Data:
- File: `big.jpg` (размер >10 МБ)

Steps:
1) Выбрать файл `big.jpg` размером >10 МБ.  
2) Проверить наличие сообщения об ошибке по размеру.  
3) Проверить состояние “Отправить”.  

Expected Result:
- Появляется сообщение о превышении лимита размера.  
- “Отправить” disabled.  

Postconditions: —  

---

**TC-AI-007**  
Title: Во время обработки фото отображается loader, интерфейс не “зависает”  
US: US-SRCH-6  
Module: AI Photo Search  
Type: UI  
Priority: P2  
Severity: Minor  

Preconditions:
- В форме выбран валидный файл (JPG/PNG ≤10 МБ).

Test Data:
- File: `photo.jpg`

Steps:
1) Нажать “Отправить”.  
2) Сразу после отправки наблюдать UI: наличие loader/индикатора обработки.  
3) Дождаться завершения обработки.  

Expected Result:
- Во время обработки отображается loader/индикатор.  
- После завершения обработки loader исчезает и отображается результат/сообщение.  

Postconditions: —  

---

**TC-AI-008**  
Title: Успешная обработка — отображается выдача схожих запчастей (карточки товаров)  
US: US-SRCH-6  
Module: AI Photo Search  
Type: Functional  
Priority: P1  
Severity: Major  

Preconditions:
- Есть валидное фото, по которому ожидаются совпадения.

Test Data:
- File: `match.jpg` (JPG ≤10 МБ)

Steps:
1) Открыть форму поиска по фото.  
2) Загрузить файл `match.jpg`.  
3) Нажать “Отправить”.  
4) Дождаться завершения обработки.  
5) Проверить, что отображаются карточки товаров (аналогично обычной выдаче).  
6) Проверить, что на карточках есть минимум: название/изображение/цена.  

Expected Result:
- Отображается выдача похожих запчастей.  
- Карточки содержат минимум данных (название/изображение/цена).  

Postconditions: —  

---

**TC-AI-009**  
Title: Если совпадений нет — отображается empty state, пользователь может продолжить поиск  
US: US-SRCH-6  
Module: AI Photo Search  
Type: Functional  
Priority: P1  
Severity: Major  

Preconditions:
- Есть валидное фото без совпадений.

Test Data:
- File: `nomatch.jpg` (JPG ≤10 МБ)

Steps:
1) Открыть форму поиска по фото.  
2) Загрузить `nomatch.jpg`.  
3) Нажать “Отправить”.  
4) Дождаться завершения обработки.  
5) Проверить, что отображается сообщение об отсутствии результатов (empty state).  
6) Проверить, что пользователь может закрыть окно и вернуться к поиску/каталогу.  

Expected Result:
- Отображается empty state “Ничего не найдено” (или эквивалент в UI).  
- Интерфейс остается работоспособным, можно продолжить поиск.  

Postconditions: —  

---

**TC-AI-010**  
Title: Ошибка обработки фото (ИИ/сервер) — показывается сообщение об ошибке и доступна повторная попытка  
US: US-SRCH-6  
Module: AI Photo Search  
Type: Negative  
Priority: P1  
Severity: Major  

Preconditions:
- Возможна имитация ошибки обработки (таймаут/5xx/отключение сети) или наблюдение реальной ошибки.

Test Data:
- File: `photo.jpg` (валидный)

Steps:
1) Открыть форму поиска по фото.  
2) Загрузить валидный файл.  
3) Нажать “Отправить”.  
4) При возникновении ошибки обработки зафиксировать текст сообщения.  
5) Проверить, что доступна повторная попытка (повторно нажать “Отправить” и/или загрузить другое фото) без перезагрузки страницы.  

Expected Result:
- Отображается сообщение об ошибке обработки (смысл: “не удалось обработать, попробуйте позже/другое фото”).  
- Интерфейс не ломается; доступна повторная попытка.  

Postconditions: —  
