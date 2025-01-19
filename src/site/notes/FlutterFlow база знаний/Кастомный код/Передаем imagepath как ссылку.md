---
{"dg-publish":true,"permalink":"/FlutterFlow база знаний/Кастомный код/Передаем imagepath как ссылку/","created":"2024-12-06T09:16:01.532-03:00","updated":"2024-12-06T13:50:58.638-03:00"}
---


**от [sabikrus](https://t.me/sabikrus)**
кастомная функция что бы передавать imagepath как ссылку

`String imageUrl(String imagePath) {`
  `/// MODIFY CODE ONLY BELOW THIS LINE`

  `List<String> parts = imagePath.split('/');`

  `for (int i = parts.length - 1; i >= 0; i--) {`
    `if (parts[i].startsWith('http://') || parts[i].startsWith('https://')) {`
      `return parts[i];`
    `}`
  `}`

  `return imagePath;`

  `/// MODIFY CODE ONLY ABOVE THIS LINE`
`}`