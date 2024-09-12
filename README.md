# katapostman
// 1. Регистрация

//Запрос: 
curl --location 'https://blog.kata.academy/api/users' \
--header 'Content-Type: application/json' \
--data-raw '{"user":{"username":"Kuchugurov","email":"Kuchugurov@mail.ru","password":"123qwe"}}'

//Ответ: 
{
    "user": {
        "username": "kuchugurov",
        "email": "kuchugurov@mail.ru",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY2ZTMzNGUwZWYwMzkxMWIwMGFlZmJlMCIsInVzZXJuYW1lIjoia3VjaHVndXJvdiIsImV4cCI6MTczMTM1MDI0MSwiaWF0IjoxNzI2MTY2MjQxfQ.cwqWqs9Qp7sgs5M-cq-7Mm6mBYTSo31wGv657xdYDno"
    }
}

// 2. Авторизация

//Запрос 
curl --location 'https://blog.kata.academy/api/users/login' \
--header 'Content-Type: application/json' \
--data-raw '{"user":{"email":"kuchugurov@mail.ru","password":"123qwe"}}'

//Ответ 
{
    "user": {
        "username": "kuchugurov",
        "email": "kuchugurov@mail.ru",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY2ZTMzNGUwZWYwMzkxMWIwMGFlZmJlMCIsInVzZXJuYW1lIjoia3VjaHVndXJvdiIsImV4cCI6MTczMTM1MDU4NiwiaWF0IjoxNzI2MTY2NTg2fQ.jeGJM_rYsSzmJayc3zdVttaTvRTXeOcZHDbs6yrOSS0"
    }
}

// 3. Данные
curl --location 'https://blog.kata.academy/api/user' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY2ZTMzNGUwZWYwMzkxMWIwMGFlZmJlMCIsInVzZXJuYW1lIjoia3VjaHVndXJvdiIsImV4cCI6MTczMTM1MDU4NiwiaWF0IjoxNzI2MTY2NTg2fQ.jeGJM_rYsSzmJayc3zdVttaTvRTXeOcZHDbs6yrOSS0'

Получаю на выходе:

{
    "user": {
        "username": "kuchugurov",
        "email": "kuchugurov@mail.ru",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY2ZTMzNGUwZWYwMzkxMWIwMGFlZmJlMCIsInVzZXJuYW1lIjoia3VjaHVndXJvdiIsImV4cCI6MTczMTM1MDcwOSwiaWF0IjoxNzI2MTY2NzA5fQ.Pwwig2b9j4Tnt3VGZicf6ZrTrqK-Bc8LPb-Egh6RgU8"
    }
}
