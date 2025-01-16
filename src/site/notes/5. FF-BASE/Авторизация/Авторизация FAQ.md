---
{"dg-publish":true,"permalink":"/5. FF-BASE/Авторизация/Авторизация FAQ/","created":"2024-10-23T10:54:34.395-03:00","updated":"2024-11-22T10:09:33.061-03:00"}
---


## [[5. FF-BASE/Авторизация/Аутентификация Telegram\|Аутентификация Telegram]]
## [[Авторизация по СМС, телефону\|Авторизация по СМС, телефону]]

## Настройка Login страницы
https://intercom.help/flutterflow/en/articles/6300011-custom-routing-when-a-user-logs-in 


Q: Приложение полностью построено на апи запросах, даже авторизация. Вопрос, как настроить, какой экран отображается при открытии приложения, если юзер уже авторизован?

A: (@ArtemPlayback): когда делаете апи запрос на авторизацию, если succeed, то обновляйте app state и делайте его == true. затем на authorization page (которое в настройках указано) on page load conditional action (условие по app state)

## Еще подборка видео об авторизации (https://www.youtube.com/playlist?list=PLsUp7t2vRqx_A7pMoGfXszGHBr9_-8s05)