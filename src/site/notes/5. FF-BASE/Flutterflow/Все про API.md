---
{"dg-publish":true,"permalink":"/5. FF-BASE/Flutterflow/Все про API/","created":"2024-12-05T14:11:31.210-03:00","updated":"2024-12-09T15:29:50.586-03:00"}
---

# Обучение
[17. API Development | Part 1 | FlutterFlow University Expert Training - YouTube](https://www.youtube.com/watch?v=4XDappFZeqk)

# Вопросы и ответы
## как использовать API, в котором query parameters могут использоваться все, а могут только частями.
Q: как использовать API, в котором query parameters могут использоваться все, а могут только частями.

A (от @kirilkindn): например есть 3 параметра 
- colour, 
- usage, 
- type.
Например, нужно выводить только 2 параметра из 3. 
URL будет примерно такой:
/resources?type=jacket&usage=casual (colour нет).  

1. Создаём API call URL.com/resources?[typeParam][usageParam][colourParam]

2. Создаём 3 переменных типа srting typeParam, usageParam, colourParam

3. В UI с помощью conditional and text combine передаем параметры: 
А) если параметр не используется, то передаем только символ &
Б) если используется, то в переменную вставляем text combine:
- название параметра, например colour= (обязательно знак равно)
- значение из какой-то переменной (например, widget state -> choice chips)
- & (на конце обязательно! Не забыть!)


## API Interseptors
[FlutterFlow's MOST INNOVATIVE Features of 2024 - Feature 6](https://www.youtube.com/watch?v=aLg-sQ83Cqg)
