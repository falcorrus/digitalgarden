---
{"dg-publish":true,"permalink":"/FlutterFlow база знаний/Flutterflow/Тормозит WEB версия моего сайта на FF/","created":"2024-10-23T10:56:46.431-03:00","updated":"2024-10-23T10:56:46.431-03:00"}
---

Q: тормозит WEB версия моего сайта на FF. 
Что можно сделать для ускорения?

A: сама технология flutter не даст быстро загрузиться, но можно сделать:
(@skripov): 
1. Перенести проект на свой сервер, гугловые сервера очень долго отдают контент. Шрифты просто вечность грузятся.
2. Уменьшить размер картинки главной страницы. Поберегите своих пользователей, не все на оптоволоконном интернете сидят. Она тоже тормозит загрузку и окончательную отрисовку экрана.
3. Воспользуйтесь гугловым сервисом (https://pagespeed.web.dev/analysis/https-tour-bilet-kz/drd7ugejpc?form_factor=desktop) аналитики скорости загрузки сайта, там будут описаны основные проблемы -
4. (@brozaurus) вставьте прелоадер (https://community.flutterflow.io/community-tutorials/post/flutter-web-pre-loader-0Edur1azQqzYv48), чтоб крутился, пока грузится
