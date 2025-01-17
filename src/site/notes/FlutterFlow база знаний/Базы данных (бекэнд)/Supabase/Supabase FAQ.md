---
{"dg-publish":true,"permalink":"/FlutterFlow база знаний/Базы данных (бекэнд)/Supabase/Supabase FAQ/","created":"2024-11-28T11:07:26.619-03:00","updated":"2025-01-19T15:24:50.463-03:00"}
---

## Обучение
[[FlutterFlow база знаний/Flutterflow/Обучение и блогеры\|Обучение и блогеры]]
[16. Databases Part 2: SQLite & Supabase | Обучающее видео](https://www.youtube.com/watch?v=f7bAWV6S32E)
[Общее и создание VIEW](https://www.youtube.com/watch?v=1dLSWYD2lso)


## Цены
Актуальные цены смотрим тут:
https://supabase.com/pricing
![../../temp/PricingFeesSupabase.jpeg](/img/user/FlutterFlow%20%D0%B1%D0%B0%D0%B7%D0%B0%20%D0%B7%D0%BD%D0%B0%D0%BD%D0%B8%D0%B9/temp/PricingFeesSupabase.jpeg)

## Развернуть (deploy) Supabase на свой сервер
[[../Установка Supabase на свой сервер 1\|../Установка Supabase на свой сервер 1]]

## Общее, все упаковано
[[FlutterFlow база знаний/Другие инструменты/Бекэнды backends\|Что такое бэкэнд и с чем его едят]]
[База знаний от FF](https://community.flutterflow.io/knowledge-base)
[find the index of a product by its ID in appstate-Как найти индекс](https://community.flutterflow.io/discussions/post/update-item-index-app-state-CY5XvdriZpnEHEY)

[Проверка, что даты брони не внутри предыдущей брони - techn#2](https://www.youtube.com/watch?v=-l3iRV1WlEM)

[Геообъекты в радиусе от точки - technique4](https://www.youtube.com/watch?v=-l3iRV1WlEM)
[Как настроить Component Callback](https://www.youtube.com/watch?v=kzlnU6M6-9g)
[Как Callback (внятно)](https://www.youtube.com/watch?v=Z-MDcSer5As)

[Как сделать онлайн трекинг по картам Google](https://blog.flutterflow.io/live-tracking-google-maps-driver/)
[Как сделать таймлайн](https://www.youtube.com/watch?v=A6c_bvYQqSM)
[Flutterflow - Custom Functions To Simplify Locations](https://www.youtube.com/watch?v=23NM9JyRjQg)
[FlutterFlow | Google Maps Search and Nearby Places - из текста показывает LatLong](https://www.youtube.com/watch?v=29Oz0LI8j68)
[Сделать как в Trello](https://www.youtube.com/watch?v=pmqZAkZv-to)
[как решить проблему с CORS в firebase и FF](https://docs.flutterflow.io/actions/actions/utilities/upload-data#web-access-for-pdfs-and-other-files)
Компоненты и списки:
[Dynamic Selections in FlutterFlow: Create Your Custom Multi-Item Picker Component](https://www.youtube.com/watch?v=FV5Xw8LnpJE)
[Сделать интервал для календаря, удобно для фильтрации свободной недвиж, 4 способа, action на вызов диапазона дат](https://www.youtube.com/watch?v=kHUq8dIMy34)
[Как сохранить из API в пользовательский тип данных, техника2](https://www.youtube.com/watch?v=AzYHCgJrwmY)
[How to manually construct a Dynamic Link URL](https://www.youtube.com/watch?v=68yRbGtrWaE)
[Magic Link Authentication in FlutterFlow](https://www.youtube.com/watch?v=dc3aX52kpiE)
[Как в Suparbase подключить загрузку фото в busket](https://www.youtube.com/watch?v=jM7OfHD8J6E)
[как в кастом коде получить доступ к локал стореджу](https://community.flutterflow.io/widgets-and-design/post/custom-widget-and-ffappstate-KEqkOSuiJE6B7W7)
[Суммировать значения в списке в AppState (action)](https://rapidmvp.co/how-to-sum-values-of-flutterflow-variables/)
[Суммировать значения в списке в AppState (видео)](https://www.youtube.com/watch?v=VYC5vwnIpzQ)

[Универсальный триггер на обновление Supa](https://youtu.be/PhAI000IbBU?si=vOTz6VRoGEyqFE_6)

[Сохранение версий изменения ячеек в Supa, техника4](https://www.youtube.com/watch?v=YnjOl4sYYaY)




## Права в Supa
Надо прописывать в **policies** к каждой таблице
### дать админский доступ определённому ID (666..)
((( SELECT auth.uid() AS uid) = id) OR (auth.uid() = '666408b4-1566-447b-a36c-0e36c9ebc96d'::uuid))
### Доступ, если совпадает столбец в двух таблицах
// myShopN в таблице users и shopIDRef в таблице productos
(EXISTS ( SELECT 1
FROM (users u
JOIN productos p ON ((u."myShopN" = p."shopIDRef")))
WHERE (u.id = auth.uid())))

## chatGPT в Supa
[спрашиваешь в свободной форме о данных в твоей таблице, workflow2](https://www.youtube.com/watch?v=Q1M1e7FpuuU)


## Как подключить Google к supabase
https://www.youtube.com/watch?v=_XM9ziOzWk4&t=1s