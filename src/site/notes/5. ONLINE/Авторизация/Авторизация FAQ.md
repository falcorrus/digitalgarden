---
{"dg-publish":true,"permalink":"/5. ONLINE/Авторизация/Авторизация FAQ/","created":"2024-10-23T10:54:34.395-03:00","updated":"2024-10-23T10:54:34.395-03:00"}
---


## [[5. ONLINE/Авторизация/Аутентификация Telegram\|Аутентификация Telegram]]
## Как сделать авторизацию по СМС

A (@Dmitry_Anikin_the_One): я не делал, но видел несколько сообщений в группах про авторизацию по SMS в Российских реалиях.
1) Сервис для Push Notifications, Email, SMS & In-App.
https://onesignal.com/
The market leading self-serve customer engagement solution for Push Notifications, Email, SMS & In-App
2) Вот здесь Danil рассказывает, какие есть варианты подключения SMS уведомлений:
https://t.me/flutterflow_rus/16663
3) А вот еще другой Danil писал такой пост про SMS
https://t.me/flutterflow_rus/12437/14431
Рекомендованные сервисы (через них SMS приходят лучше, чем FB). Например, @meta_dara советует Kazinfotech.
Я слышал про несколько сервисов:
https://www.mcommunicator.ru
https://smsaero.ru/ - Российский
4)  от @alexlisg есть сервисы flashcall. Он гораздо дешевле обычных смс
## Авторизация по телефону и смс
Хороший сервис http://mcn.ru
СМС стабильно доходит, стоит 2 рубля

Можно сделать связку Flash Call или Password Call + Sms и удешевить стоимость авторизации.
коллы не всегда доходят, поэтому если пользователь не получил звонок, следом отправить смс. 

Flash Call и Password Call стоят по 0,7 рублей

## Phone Authentication using FlutterFlow & Firebase
https://blog.flutterflow.io/phone-authentication-using-flutterflow/
Проблема: https://intercom.help/flutterflow/en/articles/6283519-google-sign-in-troubleshooting

## Настройка Login страницы
https://intercom.help/flutterflow/en/articles/6300011-custom-routing-when-a-user-logs-in 


Q: Приложение полностью построено на апи запросах, даже авторизация. Вопрос, как настроить, какой экран отображается при открытии приложения, если юзер уже авторизован?

A: (@ArtemPlayback): когда делаете апи запрос на авторизацию, если succeed, то обновляйте app state и делайте его == true. затем на authorization page (которое в настройках указано) on page load conditional action (условие по app state)

## Еще подборка видео об авторизации (https://www.youtube.com/playlist?list=PLsUp7t2vRqx_A7pMoGfXszGHBr9_-8s05)