---
{"dg-publish":true,"permalink":"/5. ONLINE/PUSH/Push FAQ/","created":"2024-10-22T17:08:22.670-03:00","updated":"2024-10-23T10:13:02.262-03:00"}
---


## OneSignal, Push для Supabase
https://community.flutterflow.io/discussions/post/onesignal-integration-for-notifications---notifications-for-supabase-yd2c5sa4jzoQr1W
Уже есть такая - https://community.flutterflow.io/discussions/post/onesignal-integration-for-notifications---notifications-for-supabase-yd2c5sa4jzoQr1W
[Realtime обновление базы](https://www.youtube.com/watch?v=3wvXtIgWUF4&t=391s)

## Подборка видео
1. Сделать чат и push (https://www.youtube.com/watch?v=jfkE4_frL_c)
2. push через onesignal (https://www.youtube.com/watch?v=DJaFai5hJn8&t=23s)
3. push с supabase auth (https://medium.com/@a.ayremlou/flutterflow-push-notifications-without-firebase-auth-low-code-e6456605af33)
4. push от Dimitar (https://www.youtube.com/watch?v=YcnKiZpo8ro)
5. push от Ali Ayremlou текстом (https://medium.com/@a.ayremlou/flutterflow-push-notifications-without-firebase-auth-low-code-e6456605af33)
6. Через oneSignal (https://www.youtube.com/watch?v=6QSAMaRT1a0)


Q: в какой момент и как делать этот запрос на refreshToken внутри flutterflow
A (от @anton_k8):
Нужно создать interception и в нем проверять актуальность accessToken, если не актуален то запрашивать новый с помощью refresh