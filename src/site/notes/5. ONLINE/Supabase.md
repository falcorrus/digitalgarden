---
{"dg-publish":true,"permalink":"/5. ONLINE/Supabase/","created":"2024-10-04T16:57:07.858-03:00","updated":"2024-10-22T16:40:55.385-03:00"}
---


## Общее все упаковано
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

[Селфхостинг на DigitalOcean](https://www.youtube.com/watch?v=dDhy6pk282U)

[Универсальный триггер на обновление Supa](https://youtu.be/PhAI000IbBU?si=vOTz6VRoGEyqFE_6)




## Права в Supa
### дать админский доступ определённому ID (666..)
((( SELECT auth.uid() AS uid) = id) OR (auth.uid() = '666408b4-1566-447b-a36c-0e36c9ebc96d'::uuid))
### Доступ, если совпадает столбец в двух таблицах
// myShopN в таблице users и shopIDRef в таблице productos
(EXISTS ( SELECT 1
FROM (users u
JOIN productos p ON ((u."myShopN" = p."shopIDRef")))
WHERE (u.id = auth.uid())))
## Поиск в Supa
[Поиск через API, решена проблема пустого вывода, с 54:00](https://www.youtube.com/watch?v=QikTDU4DDAU)
[Поиск по всей таблице от Digital Pro, c 22:51 в одно API](https://www.youtube.com/watch?v=gb7aKhDuZ4w)

https://t.me/flutterflow_rus/12427/34747
[Поиск по смыслу в Supa - technique3](https://www.youtube.com/watch?v=-l3iRV1WlEM)
[Поиск в Supabase через API](https://www.youtube.com/watch?v=1n4UGyNDAis) примерно 1ч30мин
[Пуши в Supa, без FB](https://www.youtube.com/watch?v=jfkE4_frL_c)

[FlutterFlow and like filtering using Supabase](https://medium.com/@thomas.mcneill_82427/flutterflow-and-filtering-queries-using-supabase-cfc35936ac3f)
[Короткое видео про SimpleSearch от человека](https://www.loom.com/share/fcbe0ef5c01e488f95b49b52bf9d1700) и [второе](https://www.loom.com/share/c80819672668420495bf3f531fc4a8ae)

Пример строки API в Supa для поиска и фильтрации по нескольким параметрам
```
https://nvodtxeehqnreyjuijsl.supabase.co/rest/v1/productos?&select=*&isAvailable=true&name=[name]&shopIDRef=eq.[shop]&order=myIndex.asc
```

Поиск в нескольких столбцах Supa
Ищет в таблица Services, во всех трёх столбцах: serviceName, dopName, description 
https://nvodtxeehqnreyjuijsl.supabase.co/rest/v1/services?or=(serviceName.[name],dopName.[name],description.[name])
[name сделать как ниже]
а лучше в photos "supabase"
[[Supabase_поиск — средний размер.jpeg]]


## chatGPT в Supa
[спрашиваешь в свободной форме о данных в твоей таблице, workflow2](https://www.youtube.com/watch?v=Q1M1e7FpuuU)


## OneSignal, Push для Supabase
https://community.flutterflow.io/discussions/post/onesignal-integration-for-notifications---notifications-for-supabase-yd2c5sa4jzoQr1W
Уже есть такая - https://community.flutterflow.io/discussions/post/onesignal-integration-for-notifications---notifications-for-supabase-yd2c5sa4jzoQr1W
[Realtime обновление базы](https://www.youtube.com/watch?v=3wvXtIgWUF4&t=391s)

## Как подключить Google к supabase
https://www.youtube.com/watch?v=_XM9ziOzWk4&t=1s
