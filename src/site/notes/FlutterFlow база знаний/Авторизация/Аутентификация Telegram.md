---
{"dg-publish":true,"permalink":"/FlutterFlow база знаний/Авторизация/Аутентификация Telegram/","created":"2024-10-23T09:10:39.742-03:00","updated":"2025-01-19T15:24:50.460-03:00"}
---


[Brozaurus 🦕](https://t.me/Brozaurus)
https://telegra.ph/telegram-api-authentication-10-20

Инструкция по внедрению аутентификации по номеру телефона через API Telegram. Используем как замену СМС подтверждения номера телефона клиента.

> Важно! Работает, когда у клиента установлен Телеграм (в него приходит подтверждающий код и когда клиент разрешил делиться телефоном у себя в настройках.

**Вводная часть:**

Как выглядит результат, можем посмотреть [здесь](https://core.telegram.org/gateway).

**Плюсы**: быстро, дешево ($0.01), надёжно.  
Когда мы тестируем на собственном номере телефона, то и бесплатно.

### Шаг 1 (регистрация в telegram)
Логинимся/регистрируемся по ссылке [https://gateway.telegram.org/](https://gateway.telegram.org/) со своим номером телефона.

> Теперь у нас есть личный кабинет, доступный по ссылке: [https://gateway.telegram.org/account


Переходим в закладку API и копируем токен
![../temp/2024-10-20_Telegram Gateway.png](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/2024-10-20_Telegram%20Gateway.png)

### Шаг 2 (отправка верификационного кода)

Переходим в FlutterFlow и создаем новый API Call, тип POST  
**API URL:** https://gatewayapi.telegram.org/sendVerificationMessage  

**Headers:**

В первую строку: Authorization: Bearer `<token>`. Вместо `<token>` вставляем токен с шага 1.

Во вторую строку: _Content-Type: application/json
![../temp/2 1.jpg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/2%201.jpg)

В закладке _Variables_ создаем: **phone**_, тип String_

В раздел BODY выбираем JSON и вставляем:

`{`
 `"phone_number": "<phone>",`
 `"code_length": "4"`
`}`

> "code_length": "4" - цифра может быть от 4 до 8, это длина отправляемого кода
![../temp/3.jpg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/3.jpg)

> Строка c "code" c картинки не нужна. Она только для тестирования, когда мы хотим отправить свой собственный код. По умолчанию код генерируется автоматически. 
> ! Помним, что в последней строке **не** нужна запятая.  
> Все возможные параметры для Body можно посмотреть [https://core.telegram.org/gateway/api](https://core.telegram.org/gateway/api), в разделе sendVerificationMessage

**Важно!** В закладке Advances settings **включаем** галочку Encode body as UTF-8 bytes

**Сохраняем** (жмем Save).

Тестируем в ФФ. Должен прийти Test Response похожий на:
![../temp/4.jpg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/4.jpg)

Из ответа нам надо сохранить request_id в Page State (понадобится на следующем шаге для проверки кода.

### Шаг 3 (проверка кода)
По аналогии создаем API запрос, метод POST, называем его **checkVerificationStatus**

В закладке **Variables** создаем две переменные: _request_id_ и _code_

В закладке **Headers (**как в предыдущем шаге 2)**:**

В первую строку: Authorization: Bearer `<token>`. Вместо `<token>` вставляем токен с шага 1.

Во вторую строку: _Content-Type: application/json)_

В закладку **Body**, как на картинке
![../temp/5.jpg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/5.jpg)
В _Request_id_ мы вставим значение из Page State, которое мы записали в конце шага 2. А в _code_ вставим значение, которое пользователь введёт в Text Field (мы её нарисуем в интерфейсе).

**Важно!** В закладке **Advances settings** **включаем** галочку Encode body as UTF-8 bytes

**Сохраняем** и тестируем (жмем **Test API Call**). Получаем Test response похожий на результат шага 2.

Для удобства задаём имя (нажимаем сюда)
![../temp/6-1.jpg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/6-1.jpg)

и выше задаём имя, например **response**
![../temp/6.jpg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/6.jpg)

задаём имя - response

В этом поле нам будет приходить или _code_invalid_ - тогда клиент ввёл неправильный код. Или _code_valid_ - тогда все ок и можно клиента пропускать дальше, телефон подтверждён.
