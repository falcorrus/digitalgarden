---
{"dg-publish":true,"permalink":"/2. AREAS/Obsidian_online/Telegram_api_authentication/","created":"2024-10-22T12:08:45.306-03:00","updated":"2024-10-22T12:09:30.900-03:00"}
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

>   
> Теперь у нас есть личный кабинет, доступный по ссылке: [https://gateway.telegram.org/account](https://gateway.telegram.org/account)

  
Переходим в закладку API и копируем токен
![files/2024-10-20_Telegram Gateway.png](/img/user/2.%20AREAS/Obsidian_online/files/2024-10-20_Telegram%20Gateway.png)
### Шаг 2 (отправка верификационного кода)

Переходим в FlutterFlow и создаем новый API Call, тип POST  
**API URL:** https://gatewayapi.telegram.org/sendVerificationMessage  

**Headers:**

В первую строку: Authorization: Bearer `<token>`. Вместо `<token>` вставляем токен с шага 1.

Во вторую строку: _Content-Type: application/json_
![files/2 1.jpg](/img/user/2.%20AREAS/Obsidian_online/files/2%201.jpg)

  

В закладке _Variables_ создаем: **phone**_, тип String_

В раздел BODY выбираем JSON и вставляем:

{

 "phone_number": "<phone>",

 "code_length": "4"

}

>  "code_length": "4" - цифра может быть от 4 до 8, это длина отправляемого кода
![files/3.jpg](/img/user/2.%20AREAS/Obsidian_online/files/3.jpg)

> Строка c "code" не нужна. Она только для тестирования, когда мы хотим отправить свой собственный код. Помним, что в последней строке **не** нужна запятая.  
> Все возможные параметры для Body можно посмотреть [https://core.telegram.org/gateway/api](https://core.telegram.org/gateway/api), в разделе sendVerificationMessage

**Важно!** В закладке Advances settings **включаем** галочку Encode body as UTF-8 bytes

**Сохраняем** (жмем Save).

  

Тестируем в ФФ. Должен прийти Test Response похожий на:
![files/4.jpg](/img/user/2.%20AREAS/Obsidian_online/files/4.jpg)

  

Из ответа нам надо сохранить request_id в Page State (понадобится на следующем шаге для проверки кода.

### Шаг 3 (проверка кода)

По аналогии создаем API запрос, метод POST, называем его **checkVerificationStatus**

В закладке **Variables** создаем две переменные: _request_id_ и _code_

В закладке **Headers (**как в предыдущем шаге 2)**:**

В первую строку: Authorization: Bearer <token>. Вместо <token> вставляем токен с шага 1.

Во вторую строку: _Content-Type: application/json)_

В закладку **Body**, как на картинке
![files/5.jpg](/img/user/2.%20AREAS/Obsidian_online/files/5.jpg)

В _Request_id_ мы вставим значение из Page State, которое мы записали в конце шага 2. А в _code_ вставим значение, которое пользователь введёт в Text Field (мы её нарисуем в интерфейсе).

**Важно!** В закладке **Advances settings** **включаем** галочку Encode body as UTF-8 bytes

**Сохраняем** и тестируем (жмем **Test API Call**). Получаем Test response похожий на результат шага 2.

Для удобства задаём имя (нажимаем сюда)
![files/6-1.jpg](/img/user/2.%20AREAS/Obsidian_online/files/6-1.jpg)


и выше задаём имя, например **response**
![files/6.jpg](/img/user/2.%20AREAS/Obsidian_online/files/6.jpg)

задаём имя - response

В этом поле нам будет приходить или _code_invalid_ - тогда клиент ввёл неправильный код. Или _code_valid_ - тогда все ок и можно клиента пропускать дальше, телефон подтверждён.

