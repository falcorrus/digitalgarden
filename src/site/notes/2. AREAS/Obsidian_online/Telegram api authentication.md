---
{"dg-publish":true,"permalink":"/2. AREAS/Obsidian_online/Telegram api authentication/","created":"2024-10-22T13:24:29.128-03:00","updated":"2024-10-22T13:28:44.955-03:00"}
---


[Brozaurus 🦕](https://t.me/Brozaurus)
https://telegra.ph/telegram-api-authentication-10-20

Инструкция по внедрению аутентификации по номеру телефона через API Telegram. Используем как замену СМС подтверждения номера телефона клиента.

> Важно! Работает, когда у клиента установлен Телеграм (в него приходит подтверждающий код и когда клиент разрешил делиться телефоном у себя в настройках.

**Вводная часть:**

Как выглядит результат, можем посмотреть [здесь](https://core.telegram.org/gateway).

**Плюсы**: быстро, дешево ($0.01), надёжно.  
Когда мы тестируем на собственном номере телефона, то и бесплатно.

### Шаг 1
Логинимся/регистрируемся по ссылке [https://gateway.telegram.org/](https://gateway.telegram.org/) со своим номером телефона.

> Теперь у нас есть личный кабинет, доступный по ссылке: [https://gateway.telegram.org/account


Переходим в закладку API и копируем токен
![files/2024-10-20_Telegram Gateway.png](/img/user/2.%20AREAS/Obsidian_online/files/2024-10-20_Telegram%20Gateway.png)

### Шаг 2 (отправка верификационного кода)

Переходим в FlutterFlow и создаем новый API Call, тип POST  
**API URL:** https://gatewayapi.telegram.org/sendVerificationMessage  

**Headers:**

В первую строку: Authorization: Bearer `<token>`. Вместо `<token>` вставляем токен с шага 1.

Во вторую строку: _Content-Type: application/json
![files/2 1.jpg](/img/user/2.%20AREAS/Obsidian_online/files/2%201.jpg)

