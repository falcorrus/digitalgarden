---
{"dg-publish":true,"permalink":"/FlutterFlow база знаний/Как.../Как обращаться к конкретным файлам из media assets/","created":"2024-11-04T16:43:29.957-03:00","updated":"2025-01-17T16:31:08.618-03:00"}
---

ц
Q: Как обращаться к конкретным файлам из media assets?

A: @Valery_V_Parfenov
Например так
 
`import 'package:flutter/services.dart';`

`Future<FFUploadedFile> assetsFunction() async {`
  `// Add your function code here!`
`// Загружаем изображение из ассетов в Uint8List`
  `ByteData byteData =`
      `await rootBundle.load('assets/images/__2024-10-12__16.33.22.png');`
  `Uint8List imageBytes = byteData.buffer.asUint8List();`

  `// Устанавливаем параметры изображения`
  `double height = 200.0; // замените на актуальную высоту изображения`
  `double width = 200.0; // замените на актуальную ширину изображения`

  `// Создаем FFUploadedFile с параметрами`
  `FFUploadedFile file = FFUploadedFile(`
    `name: '__2024-10-12__16.33.22.png',`
    `bytes: imageBytes,`
    `height: height,`
    `width: width,`
  `);`

  `return (file);`
`}`
