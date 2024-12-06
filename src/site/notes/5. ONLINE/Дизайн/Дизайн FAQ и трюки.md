---
{"dg-publish":true,"permalink":"/5. ONLINE/Дизайн/Дизайн FAQ и трюки/","tags":["telegram"],"created":"2024-11-30T23:09:05.026-03:00","updated":"2024-12-06T09:15:00.568-03:00"}
---

### убрать синий Шейп при скроле
Дата:  2024-11-26
**Forwarded from [jrUstick](https://t.me/jrustick)**

![photo_159194550_3 - 20241126090418009.jpg](/img/user/Telegram/photos/photo_159194550_3%20-%2020241126090418009.jpg)
![photo_159194550_4 - 20241126090417755.jpg](/img/user/Telegram/photos/photo_159194550_4%20-%2020241126090417755.jpg)

Вопрос-ответ: 
Как убрать синий Шейп при скроле в android приложении ❓

- Theme settings 
- - Design system 

Листаете в самый низ, и нажимаете на галочку "Use Material 3 Theme" 
Все, у вас оттягивание на скрол вместо синего шейпа
-=-=-=



### Выделение не только рамки, но и фона текстового поля
[FlutterFlow Tip #4 : Focused TextFields in FlutterFlow - YouTube](https://www.youtube.com/watch?v=1kajWNgw2vQ)
![../files/img_textField.jpg](/img/user/5.%20ONLINE/files/img_textField.jpg)


### улучшение Лоадера для таблиц
[FlutterFlow Tip #5: Custom Skeleton Loading States in FlutterFlow - YouTube, создание скелета](https://www.youtube.com/watch?v=FmbogF7TzIs)

### Обводка

![[documents/обводка - 20241206.txt]]
![documents/2024-10-27_15-41-09 - 20241206.png](/img/user/Telegram/documents/2024-10-27_15-41-09%20-%2020241206.png)
![documents/2024-10-27_15-41-36 - 20241206.png](/img/user/Telegram/documents/2024-10-27_15-41-36%20-%2020241206.png)
![documents/2024-10-27_15-42-10 - 20241206.png](/img/user/Telegram/documents/2024-10-27_15-42-10%20-%2020241206.png)

Работая над новым проектом, потребовались новые виджеты, поэтому делюсь с вами: виджет Обводка в виде градиента, в чаилд передаете компонент любой и исходя из размера чаилда обводка будет рисоваться. в кастомный виджет передавайте размер 100х100 или любой другой он всеравно будет игнорится. Пример на третей фотографии нужен был плавный переход обводки из прозрачного в белый.

