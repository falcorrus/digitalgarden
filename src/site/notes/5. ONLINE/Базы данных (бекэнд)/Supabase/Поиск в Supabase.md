---
{"dg-publish":true,"permalink":"/5. ONLINE/Базы данных (бекэнд)/Supabase/Поиск в Supabase/","created":"2024-10-23T10:18:09.218-03:00","updated":"2024-12-09T16:56:06.434-03:00"}
---

## Подборка
1. Simple search (можно прочить подробно в документации)
2. когда нужен поиск по одному полю) - API (https://www.youtube.com/watch?v=yExwJg1Kz0s&list=PLsGKm9PeeQyIHA00PFyuh7-VEZHLNl_Jo)
3. Algolia (быстрый и бесплатный поиск (до 1000 позиций)
4. Поиск по всей таблице (https://www.youtube.com/watch?v=gb7aKhDuZ4w) Supabase
4. поиск по примерному описанию/по смыслу (смотреть технику №3 (https://www.youtube.com/watch?v=-l3iRV1WlEM) )
5. [Поиск в Supabase через API](https://www.youtube.com/watch?v=1n4UGyNDAis) примерно 1ч30мин


[Поиск через API, решена проблема пустого вывода, с 54:00](https://www.youtube.com/watch?v=QikTDU4DDAU)
[Поиск по всей таблице от Digital Pro, c 22:51 в одно API](https://www.youtube.com/watch?v=gb7aKhDuZ4w)

https://t.me/flutterflow_rus/12427/34747



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
[[../../../3. РЕСУРСЫ/IT/FlutterFlow все/images/Supabase_поиск — средний размер.jpeg]]

## Для запросов используется [[5. ONLINE/Базы данных (бекэнд)/SQL\|SQL]]