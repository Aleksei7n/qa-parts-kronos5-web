# Test Cases — Auth: Password Recovery (Email only)

Версия: 1.1  
Окружение по умолчанию: Chrome (desktop), https://parts-kronos5.ru/

---

# AUTH

## Password recovery (Email only)

**TC-REC-001**  
Title: Открытие формы восстановления пароля из формы входа  
US: US-LOGIN-2  
Module: Auth  
Type: UI  
Priority: P1  
Severity: Major  

Preconditions:
- Пользователь не авторизован.
- Открыта модалка “Войти”.

Test Data: —  

Steps:
1) Нажать “Забыли пароль? Восстановить”.  
2) Убедиться, что открылась форма восстановления пароля.  
3) Проверить наличие поля Email и кнопки отправки запроса.  

Expected Result:
- Форма восстановления открыта.  
- Поле Email присутствует и доступно для ввода.  
- Доступна кнопка отправки (возможна зависимость от валидации Email).  

Postconditions: —  

---

**TC-REC-002**  
Title: Восстановление пароля — невалидный Email не отправляется, отображается ошибка  
US: US-LOGIN-2  
Module: Auth  
Type: Validation  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта форма восстановления пароля.

Test Data:
- Email: `test@`

Steps:
1) Ввести `test@` в поле Email.  
2) Нажать кнопку отправки/восстановления.  
3) Наблюдать отображение сообщения об ошибке.  

Expected Result:
- Отображается сообщение о некорректном формате Email.  
- Запрос не отправляется (нет подтверждения об успешной отправке).  

Postconditions: —  

---

**TC-REC-003**  
Title: Восстановление пароля — валидный Email отправляется, пользователь видит подтверждение  
US: US-LOGIN-2  
Module: Auth  
Type: Functional  
Priority: P1  
Severity: Major  

Preconditions:
- Открыта форма восстановления пароля.
- Существует тестовый пользователь с Email `valid@test.com`.

Test Data:
- Email: `valid@test.com`

Steps:
1) Ввести Email `valid@test.com`.  
2) Нажать кнопку отправки.  
3) Дождаться ответа системы.  
4) Проверить наличие подтверждения/инструкций на экране.  

Expected Result:
- Запрос восстановления отправлен.  
- Пользователь видит подтверждение об отправке и дальнейшие инструкции (в пределах UI).  

Postconditions: —  
