# Bug Reports — Parts-Kronos5 (Web)

Версия: 1.1  
Проект: https://parts-kronos5.ru/  
Окружение по умолчанию: Chrome (desktop), OS: macOS; для SMS — iOS (Messages).

---

# BUG-001

**ID:** BUG-001  
**Title:** Search results: карточки товаров отображаются в один столбец вместо сетки (нарушение верстки)  
**Project:** Parts-Kronos5 Web  
**Component/Module:** Search  
**Environment:** Chrome (desktop), OS: macOS  
**URL/Page:** https://parts-kronos5.ru  
**Build/Date:** 2025-10-21  
**Severity:** Major  
**Priority:** P1  
**Reproducibility:** Always  

**Preconditions:**  
- Открыта главная страница сайта.

**Test Data:**  
- Query: `гайка`

**Steps to reproduce:**
1. В строке поиска ввести `гайка`.
2. Запустить поиск клавишей Enter или кликом по иконке «лупа».
3. Дождаться отображения результатов поиска.
4. Оценить расположение карточек товаров в выдаче.

**Actual result:**  
- Карточки товаров отображаются вертикально **в одну колонку**, без сетки/нескольких карточек в строке.

**Expected result:**  
- Карточки товаров отображаются в виде **сеточного списка** (несколько карточек в строке согласно desktop-верстке/адаптиву).

**Attachments:**  
- [BUG-001-search-page.png](assets-screenshots-bugs/BUG-001-search-page.png)

---

# BUG-002

**ID:** BUG-002  
**Title:** Delivery city selector: иконка закрытия перекрывает название страны в шапке окна выбора  
**Project:** Parts-Kronos5 Web  
**Component/Module:** Delivery  
**Environment:** Chrome (desktop), OS: macOS  
**URL/Page:** https://parts-kronos5.ru/ (страница товара, изменение города доставки)  
**Build/Date:** 2025-10-27  
**Severity:** Minor  
**Priority:** P3  
**Reproducibility:** Always  

**Preconditions:**  
- Открыта карточка товара.
- Доступно изменение города/страны доставки.

**Test Data:**  
- Страна: Казахстан  
- Город: Павлодар

**Steps to reproduce:**
1. На странице товара в блоке доставки нажать «Изменить».
2. Дождаться открытия окна/выпадающего списка выбора.
3. Проверить шапку окна («Выберите город | Казахстан») и позицию иконки закрытия.

**Actual result:**  
- Иконка закрытия (крестик) накладывается на название страны, текст перекрыт.

**Expected result:**  
- Иконка закрытия не перекрывает текст; название страны читаемо полностью на desktop.

**Attachments:**  
- [BUG-002-.png](assets-screenshots-bugs/BUG-002-.png)

---

# BUG-003

**ID:** BUG-003  
**Title:** Registration: SMS-код подтверждения приходит от отправителя «ReklaManiya» (риск недоверия/спама)  
**Project:** Parts-Kronos5 Web  
**Component/Module:** Auth / Registration  
**Environment:** iOS (Messages)  
**URL/Page:** https://parts-kronos5.ru/ (форма регистрации)  
**Build/Date:** 2025-10-27  
**Severity:** Major  
**Priority:** P1  
**Reproducibility:** Always  

**Preconditions:**  
- Пользователь инициирует регистрацию с подтверждением по SMS.
- Указан валидный номер телефона.

**Test Data:**  
- Phone: +7 915 *** ** ** (обезличено)

**Steps to reproduce:**
1. Открыть форму регистрации на сайте.
2. Ввести валидный номер телефона.
3. Нажать «Получить код».
4. Дождаться входящего SMS и проверить отправителя.

**Actual result:**  
- SMS приходит от отправителя «ReklaManiya» (не ассоциируется с сервисом/брендом магазина).

**Expected result:**  
- SMS приходит от брендированного отправителя (например, `PARTS-KRONOS`).

**Attachments:**  
- [BUG-003-.png](assets-screenshots-bugs/BUG-003-.png)

---

# BUG-004

**ID:** BUG-004  
**Title:** Checkout: обязательные незаполненные поля не подсвечиваются и уведомление не отражает все ошибки  
**Project:** Parts-Kronos5 Web  
**Component/Module:** Cart / Checkout  
**Environment:** Chrome (desktop), OS: macOS  
**URL/Page:** https://parts-kronos5.ru/cart_view/  
**Build/Date:** 2025-11-05  
**Severity:** Major  
**Priority:** P1  
**Reproducibility:** Always  

**Preconditions:**  
- Открыта страница корзины/оформления заказа.

**Test Data:**  
- Поля в блоке «Контакты» оставить пустыми: ФИО, телефон, email  
- Адрес доставки не заполнен

**Steps to reproduce:**
1. Перейти на страницу оформления заказа `/cart_view/`.
2. Оставить поля ФИО/телефон/email пустыми в блоке «Контакты».
3. Не вводить адрес доставки.
4. Нажать кнопку действия «Оплатить».

**Actual result:**  
- Появляется уведомление «Не все поля заполнены» и текст «Не введен адрес».  
- При этом другие обязательные поля (ФИО/телефон/email) не подсвечиваются явно и не перечислены как ошибки.

**Expected result:**  
- Все обязательные пустые/невалидные поля подсвечиваются (рамка/сообщение рядом с полем).  
- Уведомление отражает полный набор обязательных ошибок или корректно направляет пользователя к каждому проблемному полю (field-level validation).

**Attachments:**  
- [BUG-004-.png](assets-screenshots-bugs/BUG-004-.png)
